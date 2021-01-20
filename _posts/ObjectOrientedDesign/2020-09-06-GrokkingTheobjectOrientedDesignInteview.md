---
layout: post
title: Grokking the Object Oriented Design Inteview
categories: OOD
description: Some notes on OOD
keywords: OOD
---

## Definition of OOP

OOP: a style of programming that focuses on using objects to design and build applications. OOP organized the program to combine data and functionality and wrap it inside something called an "Object".

Objects: real-word entity and basic building block of OOP.

Class: Class is the prototype or blueprint of an object. It is a template definition of the attributes and methods of an object.

## The principles of OOP: Encapsulation, Abstraction, Inheritance, and Polymorphism

**Encapsulation**: Encapsulation is the mechanism of binding the data together and hiding it from the outside world. Encapsulation is achieved when each object keeps its state private so that other objects don't have direct access to its state. Instead, they can access this state only through a set of public functions.

**Abstraction**: It means hiding all but the relevant data about an object in order to reduce the complexity of the system. Abstraction helps by hiding internal implementation details of objects and only revealing operations that are relevant to other objects.

**Inheritance**: Inheritance is the mechanism of creating new classes from existing ones.

**Polymorphism**: Polymorphism means many forms. It is the ability of an object to take differenct forms and thus, depending upon the context, to respond to the same message in different ways.

## OO Analysis and Design

OOAD: a structured method for analyzing and designing a system by applying object-oriented concepts. The process of OO analysis and design as followings:

1. Identifying the objects in a system;
2. Defining relationships between objects;
3. Establishing the interface of each objects;
4. Making a design, which can be coverted to executables using OO languages.

## What is UML

UML stands for Unified Modeling Language and is used to model the Object-Oriented Analysis of a software system.

### Type of UML

#### Structural UML Diagrams

    * Class diagram: describe structure and behavior in the use cases, this diagram provides a conceptual model of the system in terms of entities and their relationships.
    * Object diagram
    * Package diagram
    * Component diagram
    * Composite structure diagram
    * Deployment diagram
    * Profile diagram
  
#### Behavioral UML diagrams

    * Use case diagram: describe a set of user scenarios, this digram, illustrates the functionality provided by the system.
    * Activity diagram: Used to model the functional flow-of-control between two or more class objects.
    * Sequence diagram: used to describe interactions among classes in terms of an exchange of messages over time.
    * State Diagram
    * Communication diagram
    * Interaction overview diagram
    * Timing diagram

### Use Case Diagrams

#### Definition

Use case diagrams describe a set of actions (called use cases) that a system should or can perform in collaboration with one or more external users of the system (called actors).

    1. Use case diagrams describe the high-level functional behavior of the system. 
    2. It answers what system does from the user point of view
    3. Use case answers "What will the system do?" and at the same time tells us "What will the system Not do?". 
   
![Sample use-case diagram for online shopping system](https://raw.githubusercontent.com/wbing520/wbing520.github.io/master/images/OOD/Use%20Case%20Diagrams%20-%20Grokking%20the%20Object%20Oriented%20Design%20Interview.png)

#### Components of the use case diagrams

    * System boundary: Defines the scope and limits of the system. shown as a rectangle that spans all use cases of the system. 
    * Actors: An actor is an entity who performs specific actions. 
    * Use case: Every business functionality is a potential use case.
    * Include: Include relationship represents an invocation of one use case by another use case. From a coding perspective, it is like one function being called by another function.
    * Extend: This relationship signifies that the extended use case will work exactly like the base use case, except that some new steps will be inserted in the extended use case.
  
### Class Diagram

#### Definition of class diagram

    Class Diagram is the backbone of object-oriented modeling - it shows how different entities(people, things, and data) relate to each other. It shows the static structure of the system.  

    A class diagram describes the attributes and operations of a class and also the constraints imposed on the system. 
![Class](https://raw.githubusercontent.com/wbing520/wbing520.github.io/master/images/OOD/Class%20Diagram%20-%20Grokking%20the%20Object%20Oriented%20Design%20Interview.png)

#### Purpose

    1. Analysis and design of the staic view of an application
    2. To describe the responsibilities of a system
    3. To provide a base for component and deployment diagrams; and 
    4. Forward and reverse engineering.

A class is depicted in the class diagram as a rectangle with three horizontal sections, class name, properies of class, methods of class.

![Sample class diagram for flight reservation system](https://raw.githubusercontent.com/wbing520/wbing520.github.io/master/images/OOD/FightReserveSystem_Class%20Diagram%20-%20Grokking%20the%20Object%20Oriented%20Design%20Interview.png)

#### Different types of relationships between classes

* Association: a line between classes with an arrow indicating the navigation direction, including defaulted bi-direction and uni-direction.

* Multiplicity: Multiplicity indicates how many instances of a class participate in the relationship.

* Aggregation: "whole to its parts" relationship. Aggregation implies a relationship where the child can exist independently of the parent.

* Composition: The child class's instance lifecycle is dependent on the parent class's instance lifecycle. Composition implies a relationship where the child cannot exist independent of the parent.

* Generalization: Generalization is the mechanism for combining similar classes of objects into a single, more general class.

* Dependency: A dependency relationship is a relationship which one class depends on another class.
  
* Abstract class: use *italics* for the name.

![UML Convertions](https://raw.githubusercontent.com/wbing520/wbing520.github.io/master/images/OOD/UML%20Conversion-Class%20Diagram%20-%20Grokking%20the%20Object%20Oriented%20Design%20Interview(1).png)

### Sequence Diagram

#### Definition of Sequence Diagram

Sequence diagrams describe interactions among classes in terms of an exchange of messages over time and are used to explore the logic of complex operaations, functions or precedure. It shows a detailed flow for a specific use case or even just part of a particular use case.

#### Two Dimensions

    1. Vertical dimention shows the sequence of messages in the chronological order that they occur;
    2. Horizontal dimension shows the object instances to which the message are sent.

![An example of sequence diagram](https://raw.githubusercontent.com/wbing520/wbing520.github.io/master/images/OOD/Sequence%20diagram%20-%20Grokking%20the%20Object%20Oriented%20Design%20Interview.png)

#### How to draw

    1. Identify the class instances(objects) by putting each class instance inside a box. 
    2. If a class instance sends a message to another class instance, draw a line with an open arrowhead pointing to the reiving class instance and place the name of the message above the line
    3. Optionally, for important messages, you can draw a dotted line with an arrowhead pointing back to the originating class instance; label the return value above the dotted line.

### Activity Diagrams

    Activity diagrams illustrate the flow of control in a system. 
![Sample Activity diagram for online shopping](https://raw.githubusercontent.com/wbing520/wbing520.github.io/master/images/OOD/Activity%20Diagrams%20-%20Grokking%20the%20Object%20Oriented%20Design%20Interview.png)

#### Activity diagram vs Sequence diagram

    1. Activity diagram: captures the process flow. it used for functional modeling. A functional model represents the flow of values from external inputs, through operations and internal data stores, to external outputs. 
    2. Sequence diagram: tracks the interaction between the objects. It is used for dynamic modeling, which is represented by tracking states, transitions between states, and the events that trigger these transitions.
