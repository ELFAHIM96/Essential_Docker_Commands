## Docker ![docker](img/docker.gif)
Docker is a free and open platform that offers an immersive experience to the developers working on various aspects of software development. 
* it is a tool for runnig applications in an isolated Environment
 * it is a containerization platform that allows  devepopers to package code into various deployable units called containers. 
 *  it helps developers build, run, and deploy containers on the server and the cloud. the container contains a builder, engine, and orchestrator to deliver a seamless application that runs in any environment 
 
* now Docker is a standard for software deployment and most companies is adapting docker. 

 ###  Containers and VM
 Containers are an  abstraction at the app layer that packages code and dependencies together. Multiple containers can run on the sane machine and share the Os kernel other containers each running as isolated processess in user space. docker manages all containerized applications. 

in contrast, <strong> VIRUAL MACHINES </strong> are an abstraction of physical hardware turning one server into many servers. The hypervisor allows multiple VMs to run  on a single machine. Each VM includes a full copy of an operating system, _taking up tens of GBs.

### Benefits
* Fast, Run container in seconds instead of minutes.
*  Uses less Memory
* Does not need full OS(operating system)
* Deployement
* Testing

### Installing Docker
you can install docker on Mac and linux and Windows
go to ![install docker](https://docs.docker.com/desktop/)


### Docker version
go to the Terminal and tyoe `docker ` you will get a lot  of commandes
og get version that you are using type:
```bash
`docker --version` or `docker -V`
 ```

at each time you run docker make sure that docker daeman is running to enable docker 
```bash
`sudo systemctl status docker`
```
if it <strong> inactive</strong> you do this commande 
```bash
`sudo systemctl enable --now docker` 
```
after commande you will see that is <strong>active </strong>and <strong>running</strong>


### Docker search 
The “docker search” command searches for specific images through the Docker hub. This command returns the specific information, including image name, description, automated, official stars, etc. Here is how to use it – 
```bash
docker search MySQL
```
Docker Hub is the world's easiest way to create, manage, and deliver your team's container applications.
### Docker Hub
<strong>Docker Hub</strong> is the world's easiest way to create, manage, and deliver your team's container applications.


### Docker pull

### Docker run 

### Docker ps

### Docker stop 

### Docker restart 

### Docker kill

### Docker exec 

### Docker login

### Docker commit 

### Docker push 

### Docker network 

### Docker history 

### Docker rmi 

### Docker ps -a

### Docker copy

### Docker logs   

### Docker volume 

### Docker logout 