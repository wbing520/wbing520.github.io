---
layout: post
title: PriorityQueue in Java 
categories: Blog Java
description: PriorityQueue - Java data structure. 
keywords: blog, java, Data Structures
---

## PriorityQueue in Java

Priority queue is a queue follows First-In-First-Out rule. The elements of PriorityQueue are ordered by the natural ordering or by a Comparator on which constructor used.

### Comparator note  

``` Java
//order logs array in ascending order
Integer [] persons;
Collections.sort(persons, (lp1, rp2) ->{
    return lp1 - rp2;
    // Comparator
    // return 1; if rp2 should be before lp1
    // return -1 if lp1 should be before rp2
    // return 0; // keep the same order
});
// NOTE:
// It's similar to (in terms of the sign of the number)
// lp1 - rp2
// sorted in ascending order: from smallest to the largest number.
```
