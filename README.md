# Installing Minikube with Docker on Ubuntu 20.04

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
