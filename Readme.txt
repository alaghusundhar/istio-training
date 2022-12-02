
1 - ## Install Docker using Below Command
sudo yum update
sudo yum install docker

sudo systemctl enable docker.service
sudo systemctl start docker.service

2 - ## Install Kind 

curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.17.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/bin/kind

3 - ## Install Kubectl

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
mv kubectl /usr/bin/kubectl

4 - ## Install Istioctl

curl -sL https://istio.io/downloadIstioctl | sh -
export PATH=$HOME/.istioctl/bin:$PATH

5 -- ## Create Kubernetes Cluster using Kind

kind create cluster --name istio-training

kubectl cluster-info --context kind-istio-training

6 -- ## Install GetMesh

curl -sL https://istio.tetratelabs.io/getmesh/install.sh | bash
export GETMESH_HOME="$HOME/.getmesh"
export PATH="$GETMESH_HOME/bin:$PATH"
