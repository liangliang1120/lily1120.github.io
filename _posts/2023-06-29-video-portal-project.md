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

Each PoC demo is delivered as a container image and deployed on the Kubernetes platform.


---
## PoC1: Django and PostgreSQL for SQL queries.
- Design and test SQL queries of database for transcoding video jobs
{% capture images %}
	https://github.com/liangliang1120/iOS-app/assets/35073431/c873a034-f12f-404f-93e3-4c7d19006423
	https://github.com/liangliang1120/iOS-app/assets/35073431/5a39a20b-8c17-474b-b5b6-d072930ec72c
{% endcapture %}
{% include gallery images=images caption="Test images" cols=2 %}


## PoC2: Django and Kubernetes API integration with RBAC credentials.
- Use RBAC( Role-Based Access Control) credential for Kubernetes workload requests, status, and logs
- Integration with Kubernetes API for workload management
- Invoke Kubernetes API to create a job
{% capture images %}
	https://github.com/liangliang1120/iOS-app/assets/35073431/8102743b-1f71-4d7c-bdfc-eb0a4cc403f8
	https://github.com/liangliang1120/iOS-app/assets/35073431/3b667735-8869-4592-a989-37687c5c780c
{% endcapture %}
{% include gallery images=images caption="app for Kubernetes API and official GitHub API examples" cols=2 %}

##### Experimented 4 with Pythons scripts:
1. Use a **YAML file** to **apply “resource” to Kubernetes**
- yaml_file = '/Users/lgu/Documents/PycharmProjects/pythonProject/job2.yml’
- utils.create_from_yaml(aApiClient,yaml_file,verbose=True,namespace="poc2test")
2. Use **V1 API** to apply k8s **Job crud**
- api_response = api_instance.create_namespaced_job(body=job,namespace="poc2test")
- api_response = api_instance.read_namespaced_job_status(name=..,namespace=..)
- api_response = api_instance.patch_namespaced_job(…)
- api_instance.delete_namespaced_job(…)
3. Use **V1 API** to **apply k8s deployment**
- k8s_apps_v1.create_namespaced_deployment(body=dep, namespace="poc2test")
4. Show the **log** in a Kubernetes **Pod**
- api_instance.read_namespaced_pod_status(name, namespace)

## PoC3: HTML form with pre-signed URL for uploading files to Object storage (MinIO).
- Upload video files to MinIO using Django backend with MinIO API
- Create an HTML form, get the MinIO bucket list, and return the upload status
- Get a pre-signed URL for uploading files
![image](https://github.com/liangliang1120/iOS-app/assets/35073431/78369bdd-f5aa-442c-b925-16f035312e7d)

## PoC4: Kubernetes API to trigger video processing.
- Get a pre-signed URL for video file in MinIO source bucket
- Kubernetes API to trigger a Job for video processing (YAML)
- Video Processor container (3 tasks):
- - Transcoding Video in h.264
- - Transcoding Video in h.265
- - Transcribing Audio into text (in WebVTT)
- Real-time response of a K8s Pod. Use StreamingHttpResponse API, and JavaScript code to create an EventSource object from the Django template
{% capture images %}
	https://github.com/liangliang1120/iOS-app/assets/35073431/05732def-1c2a-4eff-bc6e-9474a0e519ec
	https://github.com/liangliang1120/iOS-app/assets/35073431/f08c566d-02d8-46c7-ae36-723417445e28
  https://github.com/liangliang1120/iOS-app/assets/35073431/8ca40a59-6b91-4e1f-89ed-1ac78a731c0e
{% endcapture %}
{% include gallery images=images caption="app for trigger video processing, MinIO shared link, expected result" cols=3 %}

## PoC5: Implementing a Video Portal with thumbnail and preview functionality.
- Implement a Web Portal to present a list of processed videos in a YouTube-like UI
- Enhance the audience experience with JavaScript (Thumbnail and animated preview GIF)
- A HTML5 video player supporting both HLS and DASH video streaming
![poc5](https://github.com/liangliang1120/iOS-app/assets/35073431/be04bdda-954f-4eec-b079-9dd8bf29dc04)

## PoC6: Retrieving files from MinIO bucket to VOD pod on Kubernetes via Django.
Retrieve video from MinIO bucket and transfer to VOD Pod in Kubernetes (use MinIO API and K8s API for transferring files)
Provide content to VOD Pod for VOD streaming
![image](https://github.com/liangliang1120/iOS-app/assets/35073431/b93ff806-9a2f-4832-a970-c3e6f111a431)

## Final: Integrate all PoCs into a Video Portal
Upload video to Object bucket and submit a video processor pod to transcode video and transcribe audio for subtitle
![image](https://github.com/liangliang1120/iOS-app/assets/35073431/443a9d08-0e7e-409e-8f62-a8c24f5d958c)