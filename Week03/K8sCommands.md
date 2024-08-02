# Setup Kubernetes Master Node and Worker Nodes on AWS
# Following are common commands for Master Node and Worker Nodes
1 sudo su
2 apt-get update
3 apt-get install apt-transport-https
4 apt-get install docker -y
5 docker --version
6 systemctl start docker
7 systemctl enable docker
8 curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add
9 nano /etc/apt/sources.list.d/kubernetes.list
10 deb http://apt.kubernetes.io/kubernetes-xenial main
11 apt-get update
12 apt-get install kubelet kubeadm kubectl kubernetes-cni -y
Note: The above 12 commands must be apply on all nodes, either if they are Master Node or worker Nodes

