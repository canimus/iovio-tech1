## Repository Setup

This section is very simple, it refers to initialising a local directory with our project name and the selected version control system. In our case we will be using `git`.

Our repository consists in:

1. iovio-tech1 folder
2. Git repository and remote branch


__Never forget to control versions__

First we will create our project folder
```sh
# Preferably in the /vagrant/ mounted partition, so that if you destroy your image the scripts will persists
mkdir -p /vagrant/selenium-training
cd /vagrant/selenium-training
mkdir -p java
mkdir -p python
mkdir -p ruby
touch README.md
```

Now that we have the backbone of our project, then we initialise the repository
```sh
git init .
```
[Next >](http://github.com/canimus/iovio-tech1/tree/master/L03_repository_setup)
