# Installing Minikube with Docker on Ubuntu 20.04

## Prerequisite

* 2 CPUs or more
* 2GB of free memory
* 20GB of free disk space


## Install docker 

* Switch to the root user by running the following command:
```sudo su -```

* Update the package list:
```apt update```

* Install the required dependencies:

```apt install apt-transport-https ca-certificates curl software-properties-common```

* Download and add Docker's official GPG key:

```curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -```

* Add the Docker repository:
```add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"```

* Install Docker Community Edition:
```apt install docker-ce```

* Add your user to the docker group and switch to the newly added group:

```sudo usermod -aG docker $USER && newgrp docker```


## Step 2: Install Minikube
Install the latest stable release of Minikube on x86-64 Linux using the binary download:

* Download the Minikube binary:
```curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64```

* Install Minikube by moving the binary to the appropriate location:
* ```sudo install minikube-linux-amd64 /usr/local/bin/minikube```

### Start Minikube with the Docker driver (from a non-root terminal with administrator access):

```sudo minikube start --driver=docker```

## Step 3: Install kubectl
Download the kubectl binary:
* ```sudo curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"```
* Download the SHA-256 checksum file:
* ```sudo curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"```
* Verify the integrity of the kubectl binary:
* ```echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check```
* Install kubectl:
* ```sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl```

### Verify kubectl installation
```kubectl version --client```


