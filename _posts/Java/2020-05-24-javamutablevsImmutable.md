---
layout: post
title: Mutable vs immutable in Java
categories: Blog Java
description: Java data structure. 
keywords: blog, java, Data Structures
---

## Mutable vs Immutable in Java

- Mutable: have fields that can be changed.
- Immutable: Object's state cannot be altered after created, for example String

``` java
String str = "abc";
str += "abc"; //a new object of string is created and assigned to str
```

Use immuable classes:

- Immutable objects are simple
- These objects require no synchronization and are inherently thread-safe
- Immutable objects make good building blocks for other objects.

---------------------------------
``` Java
//mutable class
// 1. provide a method to modify the field values
// 2. Getter and setter method
public class mutableExample {
    private String coursename;
    
    public mutableExample(String coursename) {
        this.coursename = coursename;
    }

    public String getName() {
        return coursename;
    }

    public void setName(String coursename) {
        this.coursename = coursename;
    }

    public static void main(String[] args) {
        example obj = new example("Machine Learning");
        System.out.println(obj.getName());

        // update the name, this object is mutable
        obj.setName("Machine Learning Masters");
        System.out.println(obj.getName());
    }
}

```

``` Java
// Immutable class
// 1. A class should be declared as *final* so that it can't be extended.
// 2. All the fields should be made private so that direct access is not allowed
// 3. No setter methods
// 4. Make all mutable fields final, so that they can be assigned only once.

public class immutableClass {
    private final String coursename;

    immutableClass(final String coursename) {
        this.coursename = coursename;
    }

    public final String getName() {
        return coursename;
    }

    public static void main(String[] args) {
        example obj = new example("Machine Learning");
        System.out.println(obj.getName());
    }
}

```
