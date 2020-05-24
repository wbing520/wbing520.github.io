---
layout: post
title: size() vs length vs length() in Java
categories: Blog Java
description: Java data structure. 
keywords: blog, java, Data Structures
---

## What is the difference between size and length in Java

- size(): is a method specified in java.util.Collection, which is then inherited by every data structure in the standard library.
- length: is a field on any array (arrarys are objects), which is constant and is used to find out the array storing capacity not the number of  elements in the array, like the int [], double [], String []..
- length(): is a method on java.lang.String, which is just a thin wrapper on a char[] array.

Notes: by design, Strings are immutable, and all of the top level Collection subclasses are mutable. So where you see "length" you know that's constant, and where you see "size" it isn't.
