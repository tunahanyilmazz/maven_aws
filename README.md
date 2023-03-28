# maven_aws
Please first do jenkins_aws project to start maven 
maven project on aws 

After creating a redhat instance on aws. 

Open terminal and connect with ssh to your instance. 

Launch instance.

Part-2 Connection instance over SSH on your device. -Open an SSH client.

-Locate your private key file. The key used to launch this instance is Ins1.pem (name what you create)

-Run this command, if necessary, to ensure your key is not publicly viewable.

chmod 400 Ins1.pem -ec2-16-16-70-236.eu-north-1.compute.amazonaws.com.

example : ssh -i "Ins1.pem" ec2-user@ec2-16-16-70-236.eu-north-1.compute.amazonaws.com

$ sudo su - 
$ cd /opt
$ mkdir -p maven
$cd /maven

go to :

https://maven.apache.org/download.cgi

<img width="1396" alt="image" src="https://user-images.githubusercontent.com/10364043/228201344-44faee79-5246-4393-90c0-a74bc669d808.png">

Copy this link. 

$ wget https://dlcdn.apache.org/maven/maven-3/3.9.1/binaries/apache-maven-3.9.1-bin.tar.gz 

$ tar -xvzf apache-maven-3.9.1-bin.tar.gz 

$ cd apache-maven-3.9.1

$ pwd 
/opt/maven/apache-maven-3.9.1

$ cd /root 

$ vi .bash_profile 
Copy this ---


JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.362.b09-2.el9_1.x86_64
M2_HOME=/opt/maven/apache-maven-3.9.1
M2=$M2_HOME/bin
PATH=$PATH:$JAVA_HOME:$M2_HOME:$M2:$HOME/bin
export PATH
 
Save and quit. 

Restart SSH connection. 
$ echo $PATH

The output will be: 

/root/.local/bin:/root/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:
/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.362.b09-2.el9_1.x86_64:/opt/maven/apache-maven-3.9.1:
/opt/maven/apache-maven-3.9.1/bin:/root/bin

Go to 

Jenkins

Install maven invoker plugin and restart Jenkins 

In Global Tool Configuration
Add Maven 

<img width="451" alt="image" src="https://user-images.githubusercontent.com/10364043/228205256-98acef23-19de-449c-8133-9638ac689892.png">

On terminal 

$ yum install git -y

Jenkins 
Install GitHub plugins

<img width="325" alt="image" src="https://user-images.githubusercontent.com/10364043/228206290-3c0b7216-9b20-42f7-a06a-6ce8b80f2ff1.png">

Save. 

Create Maven project 

<img width="801" alt="image" src="https://user-images.githubusercontent.com/10364043/228206444-758322b8-7cc0-47d9-8598-2ba0d09291f6.png">


