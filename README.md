# Gluu server Vagrant box 

## Getting Started

These instructions will allow you to get a gluu server instance running quickly without effort nor a mess.

### Prerequisites

* Install Vagrant software from HashiCorp: https://www.vagrantup.com/downloads.html
* Install Virtualbox from Oracle: https://www.virtualbox.org/wiki/Downloads
* Git (obviously)

### Setup

Clone the repository to a folder in your machine
```
git clone git@github.com:earezki/gluu-server-box.git
```
Download the base box and provision it. (install the Gluu server)
```
vagrant up
```
Add the following url to your host file:
```
127.0.0.1 ci.gluu.info
```
Go to **ci.gluu.info** from your browser.
enter **admin** for the username and **nimda** for the password.
