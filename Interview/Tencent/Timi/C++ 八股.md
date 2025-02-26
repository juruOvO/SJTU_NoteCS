SIMD
缓存算法：FIFO LRU LFU
https://blog.csdn.net/saxon_li/article/details/123974696?spm=1001.2014.3001.5501
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
```C++
#include <unordered_map>

#include <list>

  

struct Node {

int key, value, freq;

Node(int k, int v, int f) : key(k), value(v), freq(f) {}

};

  

class LFUCache {

int capacity, minFreq;

std::unordered_map<int, Node*> keyTable;

std::unordered_map<int, std::list<Node*>> freqTable;

  

public:

LFUCache(int cap) : capacity(cap), minFreq(0) {}

  

int get(int key) {

if (keyTable.find(key) == keyTable.end()) return -1;

Node* node = keyTable[key];

freqTable[node->freq].remove(node);

if (freqTable[node->freq].empty() && node->freq == minFreq) minFreq++;

node->freq++;

freqTable[node->freq].push_front(node);

return node->value;

}

  

void put(int key, int value) {

if (capacity == 0) return;

if (keyTable.find(key) != keyTable.end()) {

keyTable[key]->value = value;

get(key);

} else {

if (keyTable.size() == capacity) {

Node* node = freqTable[minFreq].back();

freqTable[minFreq].pop_back();

keyTable.erase(node->key);

delete node;

}

Node* newNode = new Node(key, value, 1);

keyTable[key] = newNode;

freqTable[1].push_front(newNode);

minFreq = 1;

}

}

};
```

constexpr
[C++11关键字constexpr看这篇就够了-CSDN博客](https://blog.csdn.net/yao_hou/article/details/109301290)

raii
[c++经验之谈一：RAII原理介绍 - 知乎](https://zhuanlan.zhihu.com/p/34660259)

shared_ptr unique_ptr

lambda

public/private/protected

拷贝构造函数必须要传引用：
- 


