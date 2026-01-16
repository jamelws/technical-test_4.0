# Technical Test, DevOps / WSO2 Micro Integrator

## Overview
This project sets up a simple WSO2 Micro Integrator solution using Docker, Kubernetes, and Helm.  
It offers a health check REST API and shows containerization, Kubernetes management, autoscaling, and ingress routing.

---

## Prerequisites
- Docker Desktop (with Kubernetes enabled) 
- kubectl 
- Helm 3.x 
- WSO2 Integration Studio 

---

## Project Structure
technical-test/
|─ docker/
│  ─ Dockerfile
├─ integration/
│  ─ technical-test_4.0.car
├─ k8s/
│  ─ deployment.yaml
│  ─ service.yaml
│  ─ ingress.yaml
│  ─ hpa.yaml
│  ─ secret.yaml
├─ helm/
│  ─ technical-test/
│    | ─ Chart.yaml
│    | ─ values.yaml
│    | ─ templates/
├─ docs/
│  ─ README.md
│  ─ answers.md
└─ .gitignore
