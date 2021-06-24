# Experiment 8: Kubernetes-Minikube installation and fundamentals

## Aim
To install minikube and understand fundamentals of minikube.

## Installation
- Update System and Install Required Packages.
```bash
sudo apt-get update -y
sudo apt-get install curl apt-transport-https
```
- Install VirtualBox Hypervisor

`sudo apt install virtualbox virtualbox-ext-pack`

- Install Minikube
```bash
wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo cp minikube-linux-amd64 /usr/local/bin/minikube
sudo chmod 755 /usr/local/bin/minikube
minikube version
```

- Install kubectl
```bash
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
kubectl version -o json
```
- Start Minikube
`minikube start`

## Comman Minikube Commands
- To see the kubectl configuration. `kubectl config view`
- To show the cluster information. `kubectl cluster-info`
- To check running nodes. `kubectl get nodes`
- To see a list of all the Minikube pods. `kubectl get pod`
- To stop minikube. `minikube stop`
- To enable and access the Minikube dashboard via terminal. `minikube dashboard`
