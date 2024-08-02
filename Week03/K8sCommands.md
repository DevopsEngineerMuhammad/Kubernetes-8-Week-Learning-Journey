# Setup Kubernetes Master Node and Worker Nodes on AWS
# Following are common commands for Master Node and Worker Nodes

1. sudo su
2. apt-get update
3. apt-get install apt-transport-https
apt-get install docker -y
docker --version
systemctl start docker
systemctl enable docker
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add
nano /etc/apt/sources.list.d/kubernetes.list
deb http://apt.kubernetes.io/kubernetes-xenial main
apt-get update
apt-get install kubelet kubeadm kubectl kubernetes-cni -y


