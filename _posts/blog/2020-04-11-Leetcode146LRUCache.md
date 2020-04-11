---
layout: post
title: Leetcode146 LRU Cache
categories: Blog Leetcode C#
description: Introduce basic C# data structures.
keywords: blog, C#, leetcode
---

Design and implement a data structure for Least Recently Used(LRU) cache.  
It should support the following operations: get and put

```C#
get(key) - Get the value (will always be positive) of the key if the key exists in the cache, otherwise return -1.
put(key, value) - Set or insert the value if the key is not already present.
                    When the cache reached its capacity, it should invalidate the
                    least recently used item before inserting a new item.
```

The cache is initialized with a positive capacity.  
**Follow up:**
Could you do both operations in O(1) time complexity?

**Example:**

```C#
LRUCache cache = new LRUCache( 2 /* capacity */ );

cache.put(1, 1);
cache.put(2, 2);
cache.get(1);       // returns 1
cache.put(3, 3);    // evicts key 2
cache.get(2);       // returns -1 (not found)
cache.put(4, 4);    // evicts key 1
cache.get(1);       // returns -1 (not found)
cache.get(3);       // returns 3
cache.get(4);       // returns 4
```

First of all, what is Least Recently Used(LRU) cache?

From the wiki, discards the least recently used items first. This algorithm requires keeping track of what was used when, which is expensive if one wants to make sure the algorithm always discards the least recently used item.

Secondly, let's see what is the interface for the LRU data structure.

```C#
public interface ILRUCache
{
    int Get(int key);

    void Put(int key, int value);
}
```

Third, here we use a dictionary and a double linked list to implement the functions.

```C#
/// <summary>
/// Model class for the double linked list
/// </summary>
public class DoubleLinkedNode{
    public int key{get;set;}
    public int value{get;set;}
    public DoubleLinkedNode pre{get;set;}
    public DoubleLinkedNode post{get;set;}
}
```

The handler class implements the operation of DoubleLinkedNode

```C#
/// <summary>
/// DoubleLinkedNode handler
/// </summary>
public class DoubleLinkedNodeHandler{

    private DoubleLinkedNode head, tail;

    public DoubleLinkedNodeHandler(DoubleLinkedNode head, DoubleLinkedNode tail){
        this.head = head;
        this.tail = tail;
    }

    /// <summary>
    /// Add the new node right after head
    /// </summary>
    /// <param name="node"></param>
    public void AddNode(DoubleLinkedNode node){
        node.pre = this.head;
        node.post = this.head.post;

        this.head.post.pre = node;
        this.head.post = node;
    }

    /// <summary>
    /// Remove an existing node from the linked list.
    /// </summary>
    /// <param name="node"></param>
    public void RemoveNode(DoubleLinkedNode node){
        DoubleLinkedNode pre = node.pre;
        DoubleLinkedNode post = node.post;

        pre.post = post;
        post.pre = pre;
    }

    /// <summary>
    /// Move certain node in between to the head
    /// </summary>
    /// <param name="node"></param>
    public void MoveToHead(DoubleLinkedNode node){
        this.RemoveNode(node);
        this.AddNode(node);
    }

/// <summary>
/// pop the current tail node
/// </summary>
/// <returns></returns>
    public DoubleLinkedNode PopTail()
    {
        DoubleLinkedNode res = tail.pre;
        this.RemoveNode(res);
        return res;
    }
}
```

The last part is to implement the LRU class

```C#
public class LRUCache : ILRUCache {

    private readonly int Capacity;
    private int count;

    private DoubleLinkedNode head, tail;
    private Dictionary<int, DoubleLinkedNode> cache
        = new Dictionary<int, DoubleLinkedNode>();
    private DoubleLinkedNodeHandler handler;

    public LRUCache(int capacity) {
        this.count = 0;
        this.Capacity = capacity;

        head = new DoubleLinkedNode();
        head.pre = null;

        tail = new DoubleLinkedNode();
        tail.post = null;

        head.post = tail;
        tail.pre = head;
        this.handler = new DoubleLinkedNodeHandler(head, tail);
    }

    public int Get(int key) {
        //raise exception here
        if(!cache.ContainsKey(key)){
            return -1;
        }
        var node = cache[key];

        //move the accessed node to the head;
        //most recent used.
        handler.MoveToHead(node);

        return node.value;

    }

    //put the value into the cache
    public void Put(int key, int value) {

        if(!cache.TryGetValue(key, out DoubleLinkedNode node))
        {
            node = default;
        }

        if(node == null){
            DoubleLinkedNode
                newNode = new DoubleLinkedNode();
            newNode.key = key;
            newNode.value = value;

            this.cache.Add(key, newNode);
            handler.AddNode(newNode);

            ++count;

            if(count > Capacity){
                DoubleLinkedNode tail = handler.PopTail();
                this.cache.Remove(tail.key);
                --count;
            }
        }else{
            // update the value
            node.value = value;
            handler.MoveToHead(node);
        }

    }
}

```
