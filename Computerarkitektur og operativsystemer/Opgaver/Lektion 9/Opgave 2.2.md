
Vi kan starte produceren og starte så flere consumers. Vi følger følgende:
![[Pasted image 20261110214917.png]]

## Producer 
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

#define FILESIZE (sizeof(int))

int main()
{
  
  // name of shared memory object
  const char* name1 = "BUFFER";
  const char* name2 = "READ_COUNT";

  // shared memory file descriptor
  int shm_fd;
  int shm_fd2;

  // pointer to shared memory object
  int* buffer_ptr;
  
  // create object
  shm_fd = shm_open(name1, O_RDONLY, 0666);
  shm_fd2 = shm_open(name2, O_CREAT | O_RDWR, 0666);
  ftruncate(shm_fd2, FILESIZE);
  

  // memory map of the shared memory object
  buffer_ptr = mmap(0, FILESIZE, PROT_READ, MAP_SHARED, shm_fd, 0);

  // Get semaphores
  sem_t *mutex;
  mutex = sem_open("SEM_MUTEX", O_CREAT, 0666, 1);
  
  sem_t *rw_mutex;
  rw_mutex = sem_open("RW_MUTEX", O_CREAT, 0666, 1);
  
  int *read_count;
  read_count = mmap(0, FILESIZE, PROT_READ | PROT_WRITE, MAP_SHARED, shm_fd2, 0);
  
  int next_consumed = 0;
  for(;;){

    sem_wait(mutex);
    
    *read_count = *read_count + 1;

    if(*read_count == 1){
      sem_wait(rw_mutex);
    }
    sem_post(mutex);
    next_consumed = buffer_ptr[0];
    printf("Consumed: %d\n", next_consumed);
    sem_wait(mutex);
    *read_count = *read_count - 1;
    if(*read_count == 0){
      sem_post(rw_mutex);
    }
    sem_post(mutex);
    sleep(1);
  }

  return 0;
}

```

```c


``` 