![[Pasted image 20261006145822.png]]
![[Pasted image 20261006150455.png]]

```cpp

#include <iostream>
#include "cache.h"
#include <string>
#include <vector>


int main() {
    std::vector<int> Tag = {255, 24, 2, 2345, 1, 3432, 5423}; //Tags i cache, ved forskellige "Lines"
    cache myCache(Tag);

    //Tag 0 og Line 0
    std::string address1 = "00001001001010010000000001100000"; // 32 bit address
    std::string address2 = "00000000111111110000000000000000"; // 32 bit address
    std::string address3 = "00000000000000000000000000000000"; // 32 bit address

    std::cout << "Vores cache har følgende TAGs: " << std::endl;
    for(int i = 0; i < Tag.size(); i++){
        std::cout << "Line " << i << ": " << Tag[i] << std::endl;
    }

    std::cout << "Addresse 00001001001010010000000001100000, med TAG 2345 og line 3: " << std::endl; 
    myCache.hitOrMiss(address1);
    std::cout << "Addresse 00000000111111110000000000000000, med TAG 255 og line 1: " << std::endl;
    myCache.hitOrMiss(address2);
    std::cout << "Addresse 00000000000000000000000000000000, med TAG 2 og line 2: " << std::endl;
    myCache.hitOrMiss(address3);
    return 0;
}

```


```cpp

#include "cache.h"

cache::cache(std::vector<int> Tag) : Tag(Tag){
}

int cache::binToInt(std::string binear){
    int decimal = 0;

    for (char c : binear){
        decimal *= 2;

        if (c == '1'){
            decimal += 1;
        }
    }

    return decimal;
}

void cache::setAdressLine(std::string addresse){
    std::string binearLine = addresse.substr(16,11); // Line ligger fra 16 til 27 bit i addressen
    
    int line = binToInt(binearLine);
    addressLine = line; 
}

void cache::setAdressTag(std::string addresse){
    std::string binearTag = addresse.substr(0,16); //TAG ligger i de første 16 bit 
    
    int tag = binToInt(binearTag);
    addressTag = tag; 
}

void cache::hitOrMiss(std::string addresse){
    setAdressLine(addresse);
    setAdressTag(addresse);
    if(Tag[addressLine] == addressTag){
        std::cout << "HIT" << std::endl;
    }
    else{
        std::cout << "MISS" << std::endl;
    }
}


```

```cpp

#include <iostream>
#include <vector>
#include <string>

#ifndef CACHE_H
#define CACHE_H

class cache {
    public:
        cache(std::vector<int>);
        virtual ~cache() = default;
        int binToInt(std::string binaerTal);
        void hitOrMiss(std::string binearTal);
        void setAdressLine(std::string addresse);
        void setAdressTag(std::string addresse);

    private: 
        int addressLine = 0;
        int addressTag = 0;
        std::vector<int> Tag;
        
};
#endif

```
