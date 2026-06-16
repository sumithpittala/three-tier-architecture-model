A simple 3 tier architecture web application via kubernetes (minikube)

*workspace*

docker desktop - ensure docker is installed and running

minikube - the tool that runs a single-node Kubernetes cluster inside a container or VM on your machine

kubectl - command line tool used to talk to the kubernetes cluster

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

*project bulletins*

- Orchestrated a three-tier web application (React, Node.js, MongoDB) using Kubernetes, ensuring high availability and self-healing capabilities
- Developed Kubernetes Manifests (Deployments, Services, ConfigMaps) to manage container lifecycles and environment configurations
- Implemented Service Discovery to allow seamless internal DNS communication between the microservice tiers within the cluster
- Utilized ConfigMaps to inject application assets and decouple configuration data from containerized images
