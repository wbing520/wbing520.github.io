---
layout: post
title: Top C# Basic Structures we should know. 
categories: Blog
description: Introduce basic C# data structures. 
keywords: blog, C#, Data Structures
---

C# basic structure is an essential skills when we are programming using C#. 

```C#

    public static void BasicDataStructure()
    {
        #region Primitive data types
        //Primitive data types
        bool myBool = true;
        byte myByte = 101; // 0 - 255
        sbyte mySbyte = 1; // -128 to 127
        char myChar = 'a'; //U+0000 to U+FFFF
        decimal myDecimal = 300.5m;  //±1.0 x 10(-28) to ±7.9228 x 10(+28)
        double myDouble = 33.4d;
        float myFloat = 33.44f;
        int myInt = -5;
        uint myUInt = 5;
        long myLong = 1000000000000;
        ulong myULong = 1000000;
        object myObject = new object();
        short myShort = 255;       //-32,768 to 32,767	 Signed 16-bit integer
        ushort myUShort = 32776;    //0 to 65,535       Unsigned 16-bit integer
        string myString = "abc";

        #endregion

        //Array :https://www.geeksforgeeks.org/c-sharp-arrays/
        //Syntax:
        //<Data Type>[] <Name_Array> = new <datatype> [size];
        int[] intArray1 = new int[5]; //default value is 0
        int[] intArray2 = new int[5] { 1, 2, 3, 4, 5 };
        int[] intArray3 = { 1, 2, 3, 4, 5 };

        for (int i = 0; i < intArray1.Length; i++)
        {
            Console.WriteLine(intArray1[i]);
        }

        //Multidimensional Arrays, (Rectangular Array)
        int[,] intArray2D = new int[4, 2];  //two dimensional array
        int[,,] intArray3D = new int[4, 2, 3]; // three dimensional array


        int rows = intArray3D.GetLength(0);
        int cols = intArray3D.GetLength(1);
        int heights = intArray3D.GetLength(2);

        for (int i = 0; i < rows; i++)
        {
            for (int j = 0; j < cols; j++)
            {
                for (int k = 0; k < heights; k++)
                {
                    Console.WriteLine(intArray3D[i, j, k]);

                }
            }
        }

        //Jagged Array: array of arrays.
        //Jagged array elements maybe of different dimensions and sizes.
        int[][] arr = new int[2][];
        arr[0] = new int[5] { 1, 2, 3, 4, 5 };
        arr[1] = new int[4] { 1, 2, 3, 4 };
        for (int i = 0; i < arr.Length; i++)
        {
            Console.WriteLine("Element [" + i + "] Array: ");
            for (int j = 0; j < arr[i].Length; j++)
            {
                Console.WriteLine("arr[i][j]: " + arr[i][j]);
            }
        }

        //Comment here because of page error.
        //Mix jagged and multidimensional arrays
        // int[][,] arrMix = new int[3][,]
        // {   
        // };

        for (int k = 0; k < arrMix.Length; k++)
        {
            Console.WriteLine("array[k]: " + k);
            for (int i = 0; i < arrMix[k].GetLength(0); i++)
            {
                for (int j = 0; j < arrMix[k].GetLength(1); j++)
                {
                    Console.Write(arrMix[k][i, j] + " ");
                }
            }
        }

        //Arrays are most useful for creating and working with a fixed number of strongly-typed objects. 
        //Collections provide a more flexible way to work with groups of objects. 
        //Unlike the arrays, the group of objects you work with 
        //      can grow and shrink dynamically as the needs of the application change.
    }
``` 

This part is for the basic collection
```C# 

    /// <summary>
    /// The basic collection includes the followings:
    /// List<T>
    /// Dictionary<Key, Value>
    /// HashSet<T>
    /// Stack<T>
    /// Queue<T>
    /// </summary>
    public static void BasicCollecions()
    {
        //string
        string s = "";

        //StringBuilder


        ///List Add/Remove at the beginning: O(n)
        ///Add/Remove items at the end: O(1)
        ///Search for an item(IndexOf, Contains, Find): O(n)
        //create a new list
        List<int> list = new List<int>();
        //Create a list with initial size
        var list2 = new List<int>(1000000);
        //Some operations on List
        //Add an item at the end of the list;
        list.Add(5);
        //Add the item at index 0
        list.Insert(4, 0);
        //Remove an item
        list.Remove(5);
        //remove the item at index 1
        list.RemoveAt(1);
        //Get the item at 0
        var item = list[0];
        //return the index of an item
        var index = list.IndexOf(4);
        //check to see if the list contains an item
        var contains = list.Contains(4);
        //Return the number of the list
        var count = list.Count;

        //Iterate over all objects in a list
        foreach (var t in list)
        {
            Console.WriteLine(t);
        }

        //Dictionary 
        //Dictionary is useful when you need fast lookups by keys. O(1)
        Dictionary<int, string> dic = new Dictionary<int, string>();
        dic.Add(1, "abc");
        dic.Add(2, "bcd");

        var dic2 = new Dictionary<int, string>
        {
            {1, "abc"},
            {2, "bcd"}
        };
        //Get the value from the key
        string value = dic[1];
        //Remove an object by its key
        dic.Remove(1);
        //Remove all objects
        dic.Clear();
        //Get the number of elements in dictionary
        int countDic = dic.Count;
        bool containsKey = dic.ContainsKey(1);
        bool containsValue = dic.ContainsValue("abc");
        foreach (var key in dic.Keys)
        {
            Console.WriteLine(key);
        }
        foreach (var val in dic.Values)
        {
            Console.WriteLine(val);
        }
        foreach (var keyvaluepair in dic)
        {
            Console.WriteLine("Key: {0}  Value: {1}", keyvaluepair.Key, keyvaluepair.Value);
        }

        //HashSet<T>: a hash-based collection.
        //hashset represents a set of unique items, just like a mathematical set. 
        //A set cann't contain duplicate and the order of items is not relevant.
        //{1,2, 3} is the same as {3,2 1}
        var hashSet = new HashSet<int>();
        var hashSet2 = new HashSet<int>() { 1, 2, 3 };
        //add an object to the set
        hashSet.Add(1);
        //Remove the object
        hashSet.Remove(1);
        //Remove all objects
        hashSet.Clear();
        //check to see if the set contains an object
        bool containsObj = hashSet.Contains(1);
        //Return the number of objects in the set
        int countSet = hashSet.Count;


        //Stack<T>
        Stack<string> stack = new Stack<string>();
        //push items in a stack
        stack.Push("https://google.com");
        //Check whether has the value
        bool hasValue = stack.Contains("google.com");
        //Remove and return the item on the top of the stack
        var topItem = stack.Pop();
        //Return the item on the top of hte stack without removing it
        var topExist = stack.Peek();
        //Get the total number of the items in stack
        int countStack = stack.Count;
        //remove all items from stack
        stack.Clear();


        //Queue<T>
        Queue<int> queue = new Queue<int>();
        queue.Enqueue(1);
        queue.Enqueue(2);
        int countQueue = queue.Count;

        bool containsVal = queue.Contains(1);
        int itemqueue = queue.Dequeue();
        int itemQ = queue.Peek();
        queue.Clear();

    }
```