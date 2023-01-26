### How to install kubenetes


### Step 1) Apply updates
Apply all updates of existing packages of your system
```bash
sudo get-apt update
sudo get-apt upgrade
```


first of all we should install minikibe and kuberctl

#### Step 2) Install Minikube dependencies

intall the following minikube dependencies by runing this commands:

```bash
sudo apt install -y curl wget apt-transport-https

```
### Step 3) Download Minikube Binary
We use the get command to download minikube binary
```bash
wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

```
Once the minikube binary is downloaded
```bash
$ sudo cp minikube-linux-amd64 /usr/local/bin/minikube
$ sudo chmod +x /usr/local/bin/minikube
```
Verify the minikube version
```bash
minikube version

```

### Step 4) Install Kubectl utility

kubectl utility is a command line which used to interact with kubernetes cluster. it used for managenig deployments, service and podsetc.

to download it we use the follwing command, with this command we will doawload the latest version
```bash
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

```
Once kubectl is downloaded then set the following command 

```bash
$ chmod +x kubectl
$ sudo mv kubectl /usr/local/bin/
```
verify the kubectl vesrion
```bash
kubectl version -o yaml
```
### Step 5) Start minikube
now we will state in the beginning that we would be using docker as base for minikue, so start the minikube with the docker driver, run
```bash
minikube start --driver=docker

```

```bash
minikube start --addons=ingress --cpus=2 --cni=flannel --install-addons=true --kubernetes-version=stable --memory=6g

```

### Step 6) Managing Addons on minikube

```bash
$ minikube addons list

```
### Step 7) Verify Minikube Installation
to verify minikube installation we will deploy `nignix` image

```bash
$ kubectl create deployment my-nginx --image=nginx
```
Run following kubectl command to verify deployment status

```bash
$ kubectl get deployments.apps my-nginx
$ kubectl get pods
```
### Step 8) Managing Minikube Cluster
to stop minikube cluster
```bash
$ minikube stop
```
in order to  delete the minikube, run the following command:
```bash
$ minikube delete
```
To Start the minikube, run
```bash
$ minikube start
```




