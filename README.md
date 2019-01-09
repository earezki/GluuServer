# [Deprecated]
A new version has come out.

# Gluu server Vagrant box 

## Getting Started

These instructions will allow you to get a gluu server instance running quickly without effort nor a mess.

### Prerequisites

* 4GB of RAM.
* 2 CPUS.
* Install Vagrant software from HashiCorp: https://www.vagrantup.com/downloads.html
* Install Virtualbox from Oracle: https://www.virtualbox.org/wiki/Downloads
* Git (obviously)

### Setup

Clone the repository to a folder in your machine
```
git clone https://github.com/earezki/gluu-server-box.git
cd gluu-server-box
```

Download the base box and provision it. It will download the base box and install the Gluu server. This may take a few minutes depending on your internet connection. Next time, it won't download the base box.
```
cd gluu-server-box
vagrant up
```

SSH into the virtual machine.
```
vagrant ssh
```

Run in sudo mode.
```
$ sudo su
```

Start and login to the gluu server
```
# service gluu-server-3.1.3 start
# service gluu-server-3.1.3 login
```

Run the configuration script: https://gluu.org/docs/ce/3.1.3/installation-guide/install/#3-run-setuppy
```
# cd /install/community-edition-setup
# ./setup.py
```

Add the hostname url to your host OS's host file:
* **C:\Windows\System32\drivers\etc\hosts** on Windows
* **/etc/hosts** on Ubuntu
```
127.0.0.1 {{hostname}}
```

### Use
* Go to the **hostname** you chosed from your browser.
* Enter **username** and the **password** you chosed while configuring.

### Cleanup
When you're done and you want to remove the server, just run:
* vagrant destroy
* vagrant box remove ubuntu/xenial64 *(When you run this, you'll need to download once more the basebox while provisioning)*
