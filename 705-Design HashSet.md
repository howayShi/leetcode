##笔记

v.resize(n,t)    n是数量，t是初始值
---
## 答案  
```
class MyHashSet {
public:
    vector<bool> hashset; //建立一个bool类型的hash表
    MyHashSet() {
    hashset.resize(1000001,false);
    }
    
    void add(int key) {
    hashset[key]=true;
    }
    
    void remove(int key) {
    hashset[key]=false;
    }
    
    bool contains(int key) {
    return hashset[key];
    }
};

/**
 * Your MyHashSet object will be instantiated and called as such:
 * MyHashSet* obj = new MyHashSet();
 * obj->add(key);
 * obj->remove(key);
 * bool param_3 = obj->contains(key);
 */
```