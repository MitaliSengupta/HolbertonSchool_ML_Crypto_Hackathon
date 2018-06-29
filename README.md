# GETTING READY FOR THE HACKATHON

This is a file that will help in installing a vagrant box with ubuntu 16.04 and the docker container that has all the docker images that will be used and required for the Hackathon.

## Installing Vagrant and Ubuntu 16.04

## Mac OSx
- Download VirtualBox from this [*link*](https://www.virtualbox.org/wiki/Downloads)
- Install VirtualBox
- Download Vagrant from this [*link*](https://www.vagrantup.com/downloads.html)
- Install Vagrant
- Open the Terminal application:
  -Now you will execute command line in your Terminal (each of them start with $)
  -Add the Ubuntu 16.04 image to your box list: ```$ vagrant box add ubuntu/xenial64``` Warning: this step can take time
Many other images are available [*here*](https://app.vagrantup.com/boxes/search)
- Create your first virtual machine:
  - ```$ vagrant init ubuntu/xenial64``` -> it will generate a Vagrantfile with base = "ubuntu/trusty64" - you don’t have to execute this command line everyday, only once, to create a new virtual machine 
  - $ vagrant up -> it will start your virtual machine 
  - $ vagrant ssh -> now you are inside your virtual machine. 

## Windows
- Download VirtualBox from this [*link*](https://intranet.hbtn.io/rltoken/Z2roTuyhhdPF0CnohrZQIw)
- Install VirtualBox
- Download Vagrant from this [*link*](https://intranet.hbtn.io/rltoken/0WSgWVLsNmTFDTgwy1Xg1Q)
- Install Vagrant

Create your first virtual machine:
C:\Users\xenial64> vagrant init ubuntu/xenial64 -> it will generate a Vagrantfile with base = "ubuntu/xenial64" -you don’t have to execute this command line everyday, only once, to create a new virtual machine 
C:\Users\xenial64> vagrant up -> it will start your virtual machine 
C:\Users\xenial64> vagrant ssh -> now you are inside your virtual machine. 

## Ubuntu
Open the Terminal application:
Now you will execute command line in your Terminal (each of them start with $)
Install VirtualBox: $ sudo apt-get install virtualbox
Install Vagrant: $ sudo apt-get install vagrant
Create your first virtual machine:
$ vagrant init ubuntu/xenial64 -> it will generate a Vagrantfile with base = "ubuntu/xenial64" - you don’t have to execute this command line everyday, only once, to create a new virtual machine
$ vagrant up -> it will start your virtual machine
$ vagrant ssh -> now you are inside your virtual machine.

## Tweaking Vagrant settings to increase storage from 10GB to 15GB



