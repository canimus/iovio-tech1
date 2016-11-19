## 1. Platform Setup

This section takes care of the setup in our local environment, in such a way that it will be managed by Vagrant and VirtualBox respectively. It describes how to construct our platform, using these two technologies.

Our platform will be using the following architectural components:

1. Ubuntu Xenial 16.04 LTS distribution
2. Oracle Java 8 Software Development Kit (JDK 1.8)
3. Selenium WebDriver Java Bindings (v3.0.1)

__Let's get started!__

```sh
# This will download the Virtual Machine into your environment
vagrant box add ubuntu/xenial64
```

After completed, you can confirm that the box is available by entering the following command:

```sh
# This will show which boxes area available in Vagrant
>vagrant box list
ubuntu/xenial64   (virtualbox, 20161117.0.0)
```

Next we will initialise the virtual machine with the following command:
```sh
# This will create a Vagrantfile in the local directory
vagrant init -m ubuntu/xenial64
```

Your file should look like this:
```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
end
```

Now we need to add a simple line to make sure we can interact between host and gust machines in a secure manner and without having to explicitly define port forwarding:
```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  # TODO: You have add this line below
  config.vm.network "private_network", ip: "192.168.33.10"
end
```
Once modified you are ready to launch your virtual box:
```sh
# Launch an ubuntu box
vagrant up
```

The result is that a new machine will be instantiated and you will be ready to login into it:
```sh
# Connect into the virtual machine
vagrant ssh
```
[Next >](http://github.com/canimus/iovio-tech1/tree/master/L02_tools_setup)
