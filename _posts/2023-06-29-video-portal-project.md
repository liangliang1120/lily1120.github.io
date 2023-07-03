---
layout: post
title:  "Video Portal Project"
date:   2023-06-29
excerpt: "A video protal using Django and PostgreSQL, triggering Kubernetes container for video transcoding and audio transcribing."
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
## Video Portal for video transcoding and audio transcribing

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
- PoC1: Django and PostgreSQL for SQL queries.
- PoC2: Django and Kubernetes API integration with RBAC credentials.
- PoC3: HTML form with pre-signed URL for uploading files to Object storage (MinIO).
- PoC4: Kubernetes API to trigger video processing.
- PoC5: Implementing a Video Portal with thumbnail and preview functionality.
- PoC6: Retrieving files from MinIO bucket to VOD pod on Kubernetes via Django.


---
## PoC1: Django and PostgreSQL for SQL queries.
Design and test SQL queries of database for transcoding video jobs

## PoC2: Django and Kubernetes API integration with RBAC credentials.
Use RBAC( Role-Based Access Control) credential for Kubernetes workload requests, status, and logs
Integration with Kubernetes API for workload management
Invoke Kubernetes API to create a job
{% capture images %}
	https://github.com/liangliang1120/iOS-app/assets/35073431/8102743b-1f71-4d7c-bdfc-eb0a4cc403f8
	https://github.com/liangliang1120/iOS-app/assets/35073431/3b667735-8869-4592-a989-37687c5c780c
{% endcapture %}
{% include gallery images=images caption="Test images" cols=2 %}