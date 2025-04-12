# Todo App

A simple todo application with Docker, Kubernetes, and React.

## Recent Updates

- Released version 2.0 of the application
- Docker image tagged as `v2` and published to Docker Hub
- Updated Kubernetes deployment configuration


## Docker Information

The application is containerized using Docker:

```bash
# Build the Docker image
docker build -t but05051/todo-app:v2 .

# Push to Docker Hub
docker push but05051/todo-app:v2
```

## Kubernetes Setup

### Deployment

The application is deployed on Kubernetes. Apply the configuration files:

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

The `deployment.yaml` file has been updated to use the `v2` image:

```yaml
spec:
  containers:
  - name: todo-app
    image: but05051/todo-app:v2
    ports:
    - containerPort: 3000
```

### Accessing the Application

Port-forward to access the application locally:

```bash
kubectl port-forward service/todo-service 3000:3000
```

Then open [http://localhost:3000](http://localhost:3000) in your browser.

## Technology Stack

- Frontend: React
- Containerization: Docker
- Orchestration: Kubernetes

## License

MIT License
