Programmet skal køres individuelt i to terminaler.
## Consumer kode
```c
// Program implementing a consumer.
// The producer also creates the shared memory.

#include <pthread.h>
#include <semaphore.h>

#include <stdio.h>
#include <fcntl.h>
#include <sys/shm.h>
#include <sys/stat.h>
#include <sys/mman.h>
#include <unistd.h>

#define BUFFER_SIZE (5)
#define FILESIZE (BUFFER_SIZE * sizeof(int))

int main()
{
  // name of shared memory object
  const char* name = "BUFFER";

  // shared memory file descriptor
  int shm_fd;

  // pointer to shared memory object
  int* buffer_ptr;

  // create object
  shm_fd = shm_open(name, O_RDONLY, 0666);

  // memory map of the shared memory object
  buffer_ptr = mmap(0, FILESIZE, PROT_READ, MAP_SHARED, shm_fd, 0);

  // Get semaphores
  sem_t *mutex;
  mutex = sem_open("SEM_MUTEX", O_CREAT, 0666, 1);
  
  sem_t *empty;
  empty = sem_open("SEM_EMPTY", O_CREAT, 0666, BUFFER_SIZE);
  
  sem_t *full;
  full = sem_open("SEM_FULL", O_CREAT, 0666, 0);

  int out = 0;
  int next_consumed = 0;
  for(;;){ //Betyder bare while
	
	//
    sem_wait(full);
    sem_wait(mutex);
    next_consumed = buffer_ptr[out];
    printf("Consumed: %d\n", next_consumed);
    out = (out+1)%BUFFER_SIZE;
    
    //sem_post er det samme som signal. Se slides
    sem_post(mutex);
    sem_post(empty);
    sleep(1);
  }

  return 0;
}

```


## Producer kode

```c

// Program implementing a producer.
// The producer also creates the shared memory.

#include <pthread.h>
#include <semaphore.h>

#include <stdio.h>
#include <fcntl.h>
#include <sys/shm.h>
#include <sys/stat.h>
#include <sys/mman.h>
#include <unistd.h>
#include <stdlib.h>

#define BUFFER_SIZE (5)
#define FILESIZE (BUFFER_SIZE * sizeof(int))

int main()
{
  // name of shared memory object
  const char* name = "BUFFER";

  // shared memory file descriptor
  int shm_fd;

  // pointer to shared memory object
  int* buffer_ptr;

  // create object
  shm_fd = shm_open(name, O_CREAT | O_RDWR, 0666);

  // configure size
  ftruncate(shm_fd, FILESIZE);

  // memory map of the shared memory object
  buffer_ptr = mmap(0, FILESIZE, PROT_WRITE, MAP_SHARED, shm_fd, 0);

  // write to the shared memory object
  // initialise
  for (int i = 0; i < 5; ++i)
  {
    buffer_ptr[i] = 0;
    
    printf("%d\n", buffer_ptr[i]);
  }

  // Create semaphores
  printf("creating semaphores\n");
  sem_unlink("SEM_MUTEX");
  sem_t *mutex;
  mutex = sem_open("SEM_MUTEX", O_CREAT, 0666, 1);
  
  sem_unlink("SEM_EMPTY");
  sem_t *empty;
  empty = sem_open("SEM_EMPTY", O_CREAT, 0666, BUFFER_SIZE);
  
  sem_unlink("SEM_FULL");
  sem_t *full;
  full = sem_open("SEM_FULL", O_CREAT, 0666, 0);

  printf("produce\n");

  int next_produced = 0; 
  int out = 0; 

  for(;;){
    next_produced = rand()%100;
    sem_wait(empty);
    sem_wait(mutex);
    printf("Produced: %d\n", next_produced);
    buffer_ptr[out] = next_produced;
    out = (out + 1)%BUFFER_SIZE;
    sem_post(mutex);
    sem_post(full);
    sleep(1);
  }

return 0;
}


```