# TodoApp

An app for todo task written in nodejs, and uses mongoDB to store tasks.

## How to deploy app in cluster

Build the docker file.

```docker
docker build -t todoapp:latest .
```

Create a secret named mongo, that will contain the mongoDB_connct secret.

```kubectl
kubectl create secret mongo --from-literal=mongo=${SECRET_VALUE}
```

Deploy the deployment and load balance yaml files.

```docker
kubectl apply -f deployment.yml
kubectl apply -f load-balancer.yml
```

The application will be accessible over clusterIP:30050
