# Setup Minikube On AWS
# Following commands are used to setup minikube on AWS

1. sudo su
2. apt-get update
3. apt-get install docker.io -y
4. docker --version
5. systemctl status docker
6. systemctl start docker
7. systemctl enable docker
8. systemctl status docker
9. sudo wget https://storage.googleapis.com/minikube/release/latest/minikube-linux-amd64
10. sudo cp minikube-linux-amd64 /usr/local/bin/minikube
11. sudo chmod 755 /usr/local/bin/minikube
12. minikube version
13. curl -LO  https://storage.googleapis.com/kubernetes-release/release/'curl -s https://storage.googleapis.com/kubernetes-release/release/stable.text'/bin/linux/amd64/kubectl
14. chmod +x ./kubectl
15. sudo mv ./kubectl /usr/local/bin/kubectl
16. kubectl version
17. sudo usermod -aG docker $USER && newgrp docker
18. minikube start
19. minikube status
20. kubectl cluster-info
21. kubectl get nodes
