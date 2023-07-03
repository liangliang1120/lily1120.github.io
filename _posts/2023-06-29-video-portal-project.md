---
layout: post
title:  "Video Portal Project"
date:   2023-06-29
excerpt: "A video protal using Django and PostgreSQL,trigger Kubernetes container."
project: true
tag:
- Django
- PostgreSQL
- Object Storage
- Kubernetes
- Ingress
- Docker
comments: true
---
![image](https://github.com/liangliang1120/iOS-app/assets/35073431/be92f86f-af99-40b0-8ea6-41afb4be76e3)
# Video Portal for video transcoding and audio transcribing

### Project Overview:
YouTube-like video portal for video transcoding and audio transcribing
### Purpose:
Proof of Concept (PoC) for enhancing the demo of VOD and video processor
### Key Technologies:
Django (Python3), PostgreSQL, Object Storage API, Kubernetes APIs

### Scope of the project
Building a Minimum Viable Product (MVP) video portal.
The project is broken down into multiple phases and delivered with PoCs weekly.
### The phases with weekly PoC demos:

## PoC1: Django and PostgreSQL for SQL queries.
Design and test SQL queries of database for transcoding video jobs

## PoC2: Django and Kubernetes API integration with RBAC credentials.
Use RBAC( Role-Based Access Control) credential for Kubernetes workload requests, status, and logs
Integration with Kubernetes API for workload management
Invoke Kubernetes API to create a job

