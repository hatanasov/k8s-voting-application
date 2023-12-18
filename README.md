# Kubernetes Voting Application

This project deploys a simple voting application to Kubernetes for demonstration purposes. It allows users to vote between two options and see running results.

## Application Overview
The voting application has two main components - a frontend for voting and a backend to store results. These are deployed as independent microservices in Kubernetes.

## Getting Started
Deploy the Kubernetes manifest files:

Insert at cursor

Copy
```
kubectl apply -f result-app.yaml
kubectl apply -f vote-app.yaml
```
Expose the services:

```
kubectl expose deployment vote-app --type=LoadBalancer --port=80
kubectl expose deployment result-app --type=LoadBalancer --port=80
```

Access the application: The external IP or hostname for each service can be found with `kubectl get services`. Navigate to these URLs in a browser to vote and see results.
Clean up resources:

Delete the application
```
kubectl delete -f .
```
## Structure
```
.
|-- README.md
|-- postgres.yaml
|-- redis.yaml
|-- result-app.yaml
|-- voting-app.yaml
`-- worker.yaml
```
