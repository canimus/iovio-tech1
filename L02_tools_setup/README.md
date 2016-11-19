## Tools Setup

This section takes care of the setup of the development languages and software tools that will facilitate the development of Selenium WebDriver scripts.

Our tool workbench consists in the following components:

1. Oracle Java 8 Software Development Kit (JDK 1.8)
2. Ruby Environment Manager (RVM)
3. Ruby MRI (ruby-2.3.0)
4. Conda Analytics Python Platform


__Let's move on!__

First we will install the official Oracle Java SDK 8 from its original repository:
```sh
# This will download the Virtual Machine into your environment
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install -y oracle-java8-installer
```

In the process you will have to accept the license terms, press `<ENTER>` and then `<TAB> + <ENTER>`

Next we will install Ruby environment manager `rvm`
```sh
# This will add the keys to accept rvm
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
```

And once downloaded we will execute its installation
```sh
# This downloads a bash stable branch for installation
curl -sSL https://get.rvm.io | bash -s stable
```

Next we need to load it in our environment
```sh
# Acticate RVM as function
source ~/.rvm/scripts/rvm
```

Next we install the version of ruby MRI on the latest:
```sh
# Installation of interpreter
rvm install ruby-2.3.0
```

Now we proceed with Python Bindings using Coda Installer
```sh
wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
chmod 777 Miniconda3-latest-Linux-x86_64.sh
./Miniconda3-latest-Linux-x86_64.sh
```

Proceed accepting all enquiries with `yes + yes + <SPACE><SPACE> + yes`
```sh
# Load conda into the environment
source ~/.bashrc
```

Ok, this will complete the setup of our tools in terms of languages required to interpret our scripts.

Next step is to setup docker containers to minimise the overhead of reconfinguring additional machines when reaching the steps in this workflow covering the distribution of the execution activities.

```sh
# First we add the required keys
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
```
Next we include the source lists for the version of the operative system we have
```sh
echo "deb https://apt.dockerproject.org/repo ubuntu-xenial main" | sudo tee /etc/apt/sources.list.d/docker.list
```

Next we install required additional Libraries
```sh
sudo apt-get install linux-image-extra-$(uname -r) linux-image-extra-virtual
```

Finally we install the docker services
```sh
# Docker installation
sudo apt-get update
sudo apt-get install docker-engine
```

Now we incorporate the images that we will require down in the road, covering the requirement of distributed and grid execution.
```sh
sudo docker pull selenium/hub:3.0.1-aluminum
sudo docker pull selenium/node-chrome:3.0.1-aluminum
sudo docker pull selenium/node-firefox:3.0.1-aluminum
```

[Next >](http://github.com/canimus/iovio-tech1/tree/master/L03_repository_setup)
