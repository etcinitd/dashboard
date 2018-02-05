## To run with Vagrant and Kubernetes in Docker-for-Mac

```
Vagrant up
kubectl config use-context docker-for-desktop
kubectl config view --minify > kube-config
```

* Replace `client-certificate-data` and `client-key-data` values in `kube-config` file with real values from `~/.kube/config`

```
vagrant ssh -- -R 6443:localhost:6443
cd /rsync
npm i --no-optional
kubectl --kubeconfig=./kube-config proxy --port=8080 &
kubectl get nodes
gulp serve
```

## To setup Vagrant VM
Start from up-to-date Ubuntu 16.04 LTS.
```
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-key fingerprint 0EBFCD88
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
sudo apt-get update
sudo apt-get install docker-ce
sudo docker ps
```

```
wget https://dl.google.com/go/go1.9.3.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.9.3.linux-amd64.tar.gz
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.profile
source ~/.profile
go version
```

```
sudo apt-get install openjdk-8-jdk
java --version
```

```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash
nvm install --lts
npm version
npm install --global gulp-cli
```

```
sudo apt-get install python-minimal build-essential
sudo snap install kubectl --classic
```
