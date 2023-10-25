# CI-CD-Projects

I have created the setup of CI-CD pipeline for the WebProject for which the flow diagram is as shown below:



## Flow

1. Create three EC2 Instances for installing and executing the above CI-CD Pipeline (eg: Jenkins, Sonarqube, Docker)

EC2 Instance 1( Jenkins):
Install Jenkins on this EC2 instance.

EC2 Instance 2( Sonarqube):
* Change the homedirectoty name. 
```
sudo homenamectl set-hostname sonarqube
/bin/bash
```
* Update the repository
```
sudo apt update
```
* Install the Java run-time environment.
```
sudo apt install openjdk-17-jre
```
* Install sonarqube by copying the url from the sonarqube website and then use the command.
```
wget 'url' (eg: wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.9.2.77730.zip)
```
* Install utility unzip
```
sudo apt install unzip
```
then 
```
unzip 'foldername' (eg unzip sonarqube-9.9.2.77730.zip)
```

Install Jenkins on this EC2 instance.


2. Push the code on to the github
3. Set up the Webhooks in Github repository settings as well as make the setting in the corresonsing jenkins URLfor the automatic process.
4. 
```

