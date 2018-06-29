# Getting Ready For the Hackathon

This is a file that will help in installing a vagrant box with ubuntu 16.04 and the docker container that has all the docker images that will be used and required for the Hackathon.

## Installing Vagrant 

### Mac OSx
- Download VirtualBox from this [*link*](https://www.virtualbox.org/wiki/Downloads)
- Install VirtualBox
- Download Vagrant from this [*link*](https://www.vagrantup.com/downloads.html)
- Install Vagrant
- Open the Terminal application:
  -Now you will execute command line in your Terminal (each of them start with $)
  -Add the Ubuntu 16.04 image to your box list: ```$ vagrant box add ubuntu/xenial64``` Warning: this step can take time
Many other images are available [*here*](https://app.vagrantup.com/boxes/search)

### Windows
- Download VirtualBox from this [*link*](https://intranet.hbtn.io/rltoken/Z2roTuyhhdPF0CnohrZQIw)
- Install VirtualBox
- Download Vagrant from this [*link*](https://intranet.hbtn.io/rltoken/0WSgWVLsNmTFDTgwy1Xg1Q)
- Install Vagrant

## Create your first virtual machine

### MAC OS:
- Create your first virtual machine:
  - ```$ vagrant init ubuntu/xenial64``` -> it will generate a Vagrantfile with base = "ubuntu/trusty64" - you don’t have to execute this command line everyday, only once, to create a new virtual machine 
  - $ vagrant up -> it will start your virtual machine 
  - $ vagrant ssh -> now you are inside your virtual machine. 

### Windows:
- Create a folder to contain the vagrant container files and shift + right click it and choose open CLI here
- Make sure the current path name includes the folder name
- C:\Users\xenial64> vagrant init ubuntu/xenial64 
- C:\Users\xenial64> vagrant up -> it will start your virtual machine 
- C:\Users\xenial64> vagrant ssh -> now you are inside your virtual machine. 

### Ubuntu:
- Open the Terminal application:
  - Now you will execute command line in your Terminal (each of them start with $)
  - Install VirtualBox: $ sudo apt-get install virtualbox
  - Install Vagrant: $ sudo apt-get install vagrant
  - Create your first virtual machine:
  - $ vagrant init ubuntu/xenial64 -> it will generate a Vagrantfile with base = "ubuntu/xenial64" - you don’t have to execute this command line everyday, only once, to create a new virtual machine
  - $ vagrant up -> it will start your virtual machine
  - $ vagrant ssh -> now you are inside your virtual machine.

## Modifying Vagrant settings to increase storage from default 10GB to 13GB

- $ exit
- \> vagrant halt

From CLI:
- \> vagrant plugin install vagrant-disksize

Then open the vagrantfile within the vagrant folder with notepad and add the following line:
```
   config.vm.box = "ubuntu/xenial64"
   config.disksize.size = '13GB' <----------
```
- \> vagrant up 
- \> vagrant ssh

## Installing Docker

- $ curl -fsSL get.docker.com -o get-docker.sh

- $ sudo sh get-docker.sh

When running "sudo docker run hello-world", you should get :
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
9bb5a5d4561a: Pull complete
Digest: sha256:f5233545e43561214ca4891fd1157e1c3c563316ed8e237750d59bde73361e77
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
...

- $ exit
- \> vagrant halt

## How to configure Vagrant to open Jupyter on your web browser through CLI
- open vagrantfile with notepad
- uncomment line with: ```config.vm.network "forwarded_port", guest: 80, host: 8080```
- change ```guest: 80, host: 8080``` with ```guest: 8888, host: 8888```
- \> vagrant up
- \> vagrant ssh

## Installing Docker Image
- $ ```docker run -it -p 8888:8888 --ipc=host -v $PWD:/root ufoym/deepo:all-jupyter-py27 jupyter notebook --no-browser --ip=0.0.0.0 --allow-root --NotebookApp.token= --notebook-dir='/root'```

- use this command when you need to reboot the image 

