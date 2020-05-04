---
layout: post
title: What is ZooKeeper?
categories: Technology
description: Introduction to the ZooKeeper
keywords: Tech, ZooKeeper
---

# What is ZooKeeper 
---

When I asked this question to my 6 years old daughter, she said ZooKeeper is a person, who manages lots of animals in the zoo. This is a great answer, and also my first thought. Generally, when we went to the zoo, we need to buy the tickets at the zoo gate office. The zoo officer would provide a zoo map, which labels different animal areas, cafeteria areas, shopping centers, etc. Also, the officer also checks how many people in the zoo, if it is over the permitted number, we need to wait in a line. If it not, the officer may let us know which area has most of people, and suggest another areas. The officer are also happy to provide any help if we need in the zoo. This is what a ZooKeeper doing in the zoo. They mantain the up-to-date zoo map, name the zoo area, manage the limited people in different area and provide the visitors' services.

What is the Apache ZooKeeper in the technology world? According to the [ZooKeeper Wiki](https://cwiki.apache.org/confluence/display/ZOOKEEPER/Index) page, ZooKeeper is a centralized service for maitaining configuration information, naming, providing distributed synchronization, and providing group services. ZooKeeper provides a vary simple interface to a centralized coordinate service to distill the essence of those different services, including the censensus, group management, and presence protocols.

## Apache ZooKeeper prime features

- Reliable System: This system is very reliable as it keeps working even if a node fails.
- Simple Architecture: quite simple as there is a shared hierachical namespace which helps coordinating the processes.
- Fast Processing: especially fast in "Read-dominant" workloads. (i.e. workloads in which reads are much more common than writes).
- Scalable: The performance of ZooKeeper can be improved by adding nodes.

## Apache ZooKeeper architeture

- Node: The systems installed on the cluster.
- ZNode: The nodes where the status is updated by other nodes in cluster.
- Client Applications: The tools that interact with the distributed applications.
- Server applications: Allows the client applications to interact using a common interface.

## Use Cases

- Naming Service
- Configuration Management
- Data Synchronization
- Leader Election
- Message Queue
- Notification System

## Reference
[1] [ZooKeeper Wiki](https://cwiki.apache.org/confluence/display/ZOOKEEPER/Index).
[2] [Apache ZooKeeper Wiki](https://en.wikipedia.org/wiki/Apache_ZooKeeper).
