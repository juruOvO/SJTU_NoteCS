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
```C++
#include <list>

#include <unordered_map>

  

class LRUCache {

int capacity;

std::list<int> keys;

std::unordered_map<int, std::pair<int, std::list<int>::iterator>> cache;

  

public:

LRUCache(int cap) : capacity(cap) {}

  

int get(int key) {

if (cache.find(key) != cache.end()) {

keys.erase(cache[key].second);

keys.push_front(key);

cache[key].second = keys.begin();

return cache[key].first;

}

return -1;

}

  

void put(int key, int value) {

if (cache.find(key) != cache.end()) {

keys.erase(cache[key].second);

} else if (cache.size() == capacity) {

int oldest = keys.back();

keys.pop_back();

cache.erase(oldest);

}

keys.push_front(key);

cache[key] = {value, keys.begin()};

}

};
```
LFU:
