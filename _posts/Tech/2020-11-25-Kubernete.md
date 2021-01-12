---
layout: post
title: What is Kubernetes?
categories: Technology
description: Introduction to the Kubernetes
keywords: Tech, Kubernetes, Microservice
---


Kubernetes is a popular open-source platform for managing containers and their hosted services. Kubernetes was initially developed by Google and open sourced in 2014; it is maintained by the Cloud Native Computing Foundation. Kubernetes is a modular platform that focuses on automation of container management tasks such as service discovery and load balancing, storage orchestration, deployment roll outs and rollbacks, container bin packing, self-healing, secret and configuration management. The architecture of Kubernetes is divided into three distinct component areas—Master Components, Node Components, and Add-ons. The Master Components form the control plane of the cluster making global decisions on scheduling, backup and ensuring node pod deployments to hardware nodes. The Node Components form and maintain usable Kubernetes environment on a hardware node. These components are deployed on each individual node in the data centre that are zoned to be used for container hosting providing network proxy features, healthy container state and enable container runtime features. Add-ons are an optional component group that complements the Master and Node Components by providing additional DNS, web UI and resource monitoring features (Kubernetes 2019). Kubernetes is used as a base platform for Red Hat OpenShift3 and Rancher,4 which provide additional features for Kubernetes cluster management, resource provisioning, monitoring and security