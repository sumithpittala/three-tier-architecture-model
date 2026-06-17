# A simple 3 tier architecture web application via kubernetes (minikube)

*workspace*

docker desktop - ensure docker is installed and running

minikube - the tool that runs a single-node Kubernetes cluster inside a container or VM on your machine

kubectl - command line tool used to talk to the kubernetes cluster

<img width="705" height="477" alt="image" src="https://github.com/user-attachments/assets/7dee94e3-36aa-421e-a948-ab7a84c57241" />


*project throughput*

1. start
   ```bash
   minikube start

2. deploy MangoDB
   ```bash
   kubectl apply -f k8s/mongodb.yaml

3. deploy the backend
   ```bash
   kubectl apply -f k8s/backend.yaml

4. deploy the frontend
   ```bash
   kubectl apply -f k8s/frontend.yaml

5. verification and testing
   - check your pods
     ```bash
     kubectl get pods

   - check your services
     ```bash
     kubectl get svc

   - launch the application
     ```bash
     minikube service frontend-service

*project repo blueprint*

```
├── k8s/
│   ├── frontend.yaml     # Declares ConfigMap, Nginx Deployment, & NodePort Service
│   ├── backend.yaml      # Declares Node.js Replicas & ClusterIP Service
│   └── mongodb.yaml      # Declares MongoDB Deployment & Internal Database Service
└── README.md             # Your professional project documentation
```

*project output*

<img width="661" height="500" alt="Screenshot 2026-06-16 190845" src="https://github.com/user-attachments/assets/02325209-3559-4def-9644-4d1fbbb4b5e4" />


*project bulletins*

- Orchestrated a three-tier web application (React, Node.js, MongoDB) using Kubernetes, ensuring high availability and self-healing capabilities
- Developed Kubernetes Manifests (Deployments, Services, ConfigMaps) to manage container lifecycles and environment configurations
- Implemented Service Discovery to allow seamless internal DNS communication between the microservice tiers within the cluster
- Utilized ConfigMaps to inject application assets and decouple configuration data from containerized images
