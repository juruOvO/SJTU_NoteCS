SIMD
缓存算法：FIFO LRU LFU
FIFO:
```C++
#include <queue>

#include <unordered_map>

  

class FIFOCache {

int capacity;

std::queue<int> keys;

std::unordered_map<int, int> cache;

  

public:

FIFOCache(int cap) : capacity(cap) {}

  

int get(int key) {

if (cache.find(key) != cache.end()) {

return cache[key];

}

return -1;

}

  

void put(int key, int value) {

if (cache.size() == capacity) {

int oldest = keys.front();

keys.pop();

cache.erase(oldest);

}

keys.push(key);

cache[key] = value;

}

};
```
LRU:
