# Experiment 9: Deploying Pods and Services on minikube

## Aim
To deploy pods and services on minikube.

## Steps Performed

### Create Deployment
- Start minikube `minikube start`
![m1](https://user-images.githubusercontent.com/46739435/116846207-6d177580-ac05-11eb-9532-c3fd36b0c14d.png)

- Access minikube dashboard `minikube dashboard`
![m2](https://user-images.githubusercontent.com/46739435/116846204-6c7edf00-ac05-11eb-824a-0c5b2617a1c5.png)
![m4](https://user-images.githubusercontent.com/46739435/116846201-6ab51b80-ac05-11eb-90d1-c4ae75ac87fa.png)

- Create deployment e.g. `nginx-deployment.yml`
```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 2
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
          - name: nginx
            image: nginx
            ports:
              - containerPort: 80
```

- Use command `kubectl apply -f nginx-deployment.yml` to create deployment.
![m5](https://user-images.githubusercontent.com/46739435/116846200-6a1c8500-ac05-11eb-9a2e-713e3361df7f.png)

- Use minikube dashboard to verify results.
![m6](https://user-images.githubusercontent.com/46739435/116846198-6983ee80-ac05-11eb-81e7-a731521b67cd.png)
![m7](https://user-images.githubusercontent.com/46739435/116846194-6852c180-ac05-11eb-8694-50e7c00493fd.png)

### Create service
- Create service e.g. `nginx-service.yml`
```yml
apiVersion: v1
kind: Service
metadata:
  name: nginx-service

spec:
  selector:
    app: nginx
  type: NodePort
  ports:
  - port: 80
    targetPort: 80
    protocol: TCP
    nodePort: 30005
```
- Use command `kubectl apply -f nginx-service.yml` to create service.
![m8](https://user-images.githubusercontent.com/46739435/116846192-67ba2b00-ac05-11eb-9ab3-58d6ac609d92.png)

- Use minikube dashboard to verify results.
![m9](https://user-images.githubusercontent.com/46739435/116846186-6688fe00-ac05-11eb-8786-460216450491.png)



