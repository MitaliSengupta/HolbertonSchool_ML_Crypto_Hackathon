# AICryptoTrading

This is the example code for "Bitcoin and crypto trading with Artificial Intelligence" hackathon at 
Holberton school https://www.meetup.com/Holberton-School/events/251802757/

The event will take place @HolbertonSchool the weekend of Friday, June 29, 2018, 5:00 PM to Sunday, July 1, 2018, 11:59 AM!

## Getting Started

### Files

The example consists of a jupyter notebook, python code and exchange price csv files for 2 pairs:
 * USD/BTC since 2012 every 5 minutes, high,low,close,open,volume
 * BTC/ETH since 2012 every 5 minutes, high,low,close,open,volume
 
### Dependencies

The easiest way to get all deep learning libraries and dependencies is to use docker, specifically this image:
ufoym/deepo:all-py27-jupyter

To learn more about this image: https://github.com/ufoym/deepo

### Runnning the code on docker

The docker image ufoym/deepo:all-py27-jupyter contains all the libraries needed to run either on CPU or GPU.
To test your code, assuming you checked out the project in your current working directory:

```bash
docker run -it -p 8888:8888 --ipc=host -v $PWD:/root ufoym/deepo:all-jupyter-py27 jupyter notebook --no-browser --ip=0.0.0.0 --allow-root --NotebookApp.token= --notebook-dir='/root'
```

This will run a deep learning jupyter notebook on your machine, accessible at port 8888.
Use your browser to access http://localhost:8888 and open the file crypto_predict.ipynb to get started.


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

### To make the docker image to work properly, please ass "-cpu" to the command. I have udated the command below. Please use this command. Either increase the vagrant size to 20GB or create a new vagrant container.

- $ ```docker run -it -p 8888:8888 --ipc=host -v $PWD:/root ufoym/deepo:all-jupyter-py27-cpu jupyter notebook --no-browser --ip=0.0.0.0 --allow-root --NotebookApp.token= --notebook-dir='/root'```

- use this command when you need to reboot the image