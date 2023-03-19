### What is Kubernetes
Kubernetes  is an open-source container orchestration system for automating software deployment, scaling, and management. Originally designed by Google, the project is now maintained by the Cloud Native Computing Foundation is an open-source container orchestration system for automating software deployment, scaling, and management. Originally designed by Google, the project is now maintained by the Cloud Native Computing Foundation

### How to install kubernetes


### Step 1 Apply updates
Apply all updates of existing packages of your system 
```bash
sudo get-apt update
sudo get-apt upgrade
```


first of all we should install minikibe and kuberctl

Minikube is a lightweight Kubernetes implementation that creates a VM on your local machine and deploys a simple cluster containing only one node

#### Step 2 Install Minikube dependencies

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

### configure local client docker environment
```bash
$ minkube start
```
to connect the docker client to docker engine which provided by Minikube,
the minikube docker-env command returns the necessary environment variables to configure
```bash
echo $(minikube docker-env)
```
message:
export DOCKER_TLS_VERIFY="1" export DOCKER_HOST="tcp://192.168.49.2:2376" export DOCKER_CERT_PATH="/home/omar/.minikube/certs" export MINIKUBE_ACTIVE_DOCKERD="minikube" # To point your shell to minikube's docker-daemon, run: # eval $(minikube -p minikube docker-env)
```bash
eval $(minikube -p minikube docker-env)
```
```bash
echo $DOCKER_HOST
```
`tcp://192.168.49.2:2376`

### Deploy a container in a kubernetes pod

```bash
kubectl --version
```
Create an image docker 
```bash
docker build . -t app-text:v1
```
now we can deploy a container  in a  kubernetes pod
```bash
kubectl create deployment node-app --image app-text:v1
```

```bash
kubectl get deployment
```
consult pods run the following command:
```bash
kubectl get pods
```

```bash
kubectl expose deployment node-app --type=NodePort --port=8080
```
```bash
kubectl describe service node-app
```
### Consult the remote app-test service
```bash
minikube service node-app
```
### Consult the local app-test service

Linux:
```bash
kubectl get pods

kubectl exec -ti <name of pod > bash
```
Windows:
```bash
winpty kubectl exec <nome of pod > bash 
```
```bash
/# ls

/# cat <file>

/# exit
```

### Clean

```bsah
kubectl describe service node-app
```
### delete service node app

```bash
kubectl delete service <app>
 ```
 ```bash
 kubectl delete pod <name of pod >
```
```bash
minikube stop
minikube detele
```
you can start again by runing new minikube
```bash
minikube start
```












