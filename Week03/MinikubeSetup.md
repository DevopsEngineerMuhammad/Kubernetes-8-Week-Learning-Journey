# How to Set Up Minikube on an AWS EC2 Server

## What You Need
- At least 2 CPUs
- 2GB or more memory
- 20GB or more of free disk space
- Internet connection
- A container or virtual machine manager like Docker, VirtualBox, or VMware

### Step 1: Set Up an Ubuntu Server on AWS Cloud
Create a t2.medium EC2 instance with Ubuntu. This instance type has 2 vCPUs and 4GB of RAM, which is good for running Minikube.

### Step 2: Install Docker on the Ubuntu Server
We’ll use Docker to run Minikube. Let’s install it first.

```sh
# Update the system and install some tools:
sudo apt-get update
sudo apt-get install ca-certificates curl

# Add Docker’s security key:
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add Docker’s repository:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

# Install Docker and some additional tools:
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y

```

### Step 3: Give Docker Permissions to the Ubuntu User 

```sh
sudo usermod -aG docker ubuntu
```

### Step 4: Install Minikube
Next, we’ll install Minikube, which allows you to run Kubernetes on your ubuntu machine.

```sh
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube && rm minikube-linux-amd64
```
### Step 5: Start Minikube
Now that Minikube is installed, start the Kubernetes cluster.
```sh
minikube start
```
### Step 6: Install kubectl
kubectl is a command-line tool for interacting with your Kubernetes cluster. Let’s install it.
```sh
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
### Step 7: Check if the Installation Was Successful
To make sure everything is installed correctly, check the version of kubectl:
```sh
kubectl version --client
```
### Step 8: Deploy a Test Pod
Now, let's deploy a simple NGINX pod to ensure everything is working.
```sh
kubectl run demo-1 --image nginx
```
### Step 9: Check the Status of the Pod
To see if the pod is running, check the status with this command:
```sh
kubectl get pods
```
