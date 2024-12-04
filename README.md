# Cosmocloud Deploy Helm Chart

## Overview
This Helm chart deploys a full-stack application with three services:
- Backend (shreybatra/sample-backend)
- Frontend (shreybatra/sample-frontend)
- Redis Database

## Deployment Details
- Namespace: default
- Deployments: 1 replica each
- Services:
  1. Backend Service (ClusterIP)
     - Name: backend-svc
     - Port: 8000
  2. Frontend Service (NodePort)
     - Name: frontend-svc
     - Port: 5173
     - NodePort: 31000
  3. Redis Service (ClusterIP)
     - Name: redis-svc
     - Port: 6379

## Environment Variables
- Backend: 
  - REDIS_URI=redis://redis-svc:6379
- Frontend:
  - BACKEND_URL=http://backend-svc:8000

## Installation
```bash
helm install testapp cosmocloud-deploy --atomic --timeout 30s
```
