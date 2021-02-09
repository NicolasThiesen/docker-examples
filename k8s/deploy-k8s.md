```Shell
#!/bin/bash

sudo hostname elliot-01
sudo echo "elliot-01" > /etc/hostname

sudo apt -y update
sudo apt -y install docker.io

sudo systemctl start docker
sudo systemctl enable docker

sudo curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add
sudo apt-add-repository "deb http://apt.kubernetes.io/ kubernetes-xenial main"

sudo apt-get -y install kubeadm kubelet kubectl

kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"

nano /etc/docker/daemon.json
mkdir -p /etc/systemd/system/docker.service.d
systemctl daemon-reload
systemctl restart docker
docker info | grep -i cgroup


{
  "exec-opts": ["native.cgroupdriver=systemd"],
  "log-driver": "json-file",
  "log-opts": {
     "max-size": "100m"
  },
  "storage-driver": "overlay2"
}
```