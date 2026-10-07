# DevOps Project 12 – Containerized Application Deployment on Amazon EKS

## Architecture

![alt text](<project 12 EKS.gif>)


## Project Overview

In this project, I deployed a containerized frontend and backend application on Amazon EKS using Kubernetes.

I first created Docker containers for the frontend and backend and then deployed them on an EKS cluster using Kubernetes YAML files.

The frontend and backend are deployed using Kubernetes Deployments, and Kubernetes Services are used to provide stable communication with the Pods.

For external access, I used an AWS Application Load Balancer with Kubernetes Ingress. The Ingress handles path-based routing, so requests to `/` are sent to the frontend and requests to `/api` are sent to the backend.

This project helped me understand how a containerized application is deployed and accessed using Kubernetes and Amazon EKS.

## Technologies Used

- AWS EKS
- Kubernetes
- Docker
- AWS Application Load Balancer
- Kubernetes Ingress
- React
- Node.js

## Kubernetes Resources Used

- Namespace
- Deployment
- Pod
- Service
- Ingress

## Application Flow

```text
User
  ↓
Application Load Balancer
  ↓
Ingress
  ↓
 ┌─────────────────────┐
 │      Amazon EKS     │
 │                     │
 │  Frontend Service   │ → Frontend Pods
 │                     │
 │  Backend Service    │ → Backend Pods
 │                     │
 └─────────────────────┘