# usefulLinuxCommands

## Ubuntu/Debian

#### Initial setup

> ```
> sudo apt install htop git pm-utils`
> ```

#### Power

> ```
> sudo poweroff
> sudo reboot
> sudo pm-suspend
> sudo shutdown
> ```

## Maintenance

> ```
> sudo apt update`
> sudo apt upgrade -y
> sudo apt full-upgrade -y
> sudo apt dist-upgrade -y
> sudo apt install -f
> sudo dpkg --configure -a
> sudo apt autoremove
> sudo apt clean
> ```

#### Java

> ```
> wget --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u162-b12/0da788060d494f5095bf8624735fa2f1/jdk-8u162-linux-x64.tar.gz
> wget --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u162-b12/0da788060d494f5095bf8624735fa2f1/jre-8u162-linux-x64.tar.gz
> sudo cp -avr jdk1.8.0_162 jre1.8.0_162 /opt
> sudo update-alternatives --install /usr/bin/java java /opt/jdk1.8.0_162/bin/java 100
> sudo update-alternatives --install /usr/bin/javac javac /opt/jdk1.8.0_162/bin/java 100
> sudo update-alternatives --install /usr/bin/java java /opt/jre1.8.0_162/bin/java 100
> java -version
> ```

#### Maven

> ```
> sudo apt install maven`
> mvn -version
> mvn -v
> ```

#### Nodejs 9

> ```
> https://nodejs.org/en/download/package-manager/
>
> curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
> sudo apt-get install -y nodejs
> sudo apt-get install -y build-essential
> node -v
> ```

#### npm

> ```
> npm init
> npm -v
> ```

#### IntelliJ and WebStorm

> ```
> wget https://download.jetbrains.com/idea/ideaIC-2017.3.4.tar.gz
> tar zxvf ideaIC-2017.3.4.tar.gz
> ```

#### C++

> ```
> sudo apt install g++
> ```

#### C#

> ```
> http://www.mono-project.com/download/stable/
> ```

#### Jenkins

> ```
> https://www.digitalocean.com/community/tutorials/how-to-install-jenkins-on-ubuntu-16-04
> 
> wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | sudo apt-key add -
> sudo apt install jenkins
> ```






## install Docker

`$ wget -qO- https://get.docker.com/ | sh`

`$ sudo usermod -aG docker ubuntu`

`$ logout`

## Docker Jenkins

`$ docker pull jenkins`

Jenkins requires Maven but it is not a dependency

`$ docker pull maven`

`$ mkdir temp`

a new directory with non-root access is required

`$ docker run -p 8080:8080 -p 50000:50000 -v /home/ubuntu/temp:/var/jenkins_home --detach jenkins`

`$ docker run -ti -v /home/ubuntu/temp:/home/info/ jenkins bash`

`$ java -version`

`$ cat /home/info/secrets/initialAdminPassword`

## Docker Jira

`$ docker pull cptactionhank/atlassian-jira`

`$ docker run --detach --publish 8081:8080 cptactionhank/atlassian-jira:latest`

## Linking Jira and MySQL

## Docker Nexus

`$ docker pull sonatype/nexus`

## Docker Zabbix

`$ docker pull zabbix/zabbix-server-mysql`

## GitHub

## Remove all exited Docker Containers

`$ docker stop $(docker ps -a -q)`

`$ docker rm $(docker ps -a -q)`

 *[Commands for docker containers](https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes)*
 
 ## Ansible install
 
`$ sudo apt-get install software-properties-common`

`$ sudo apt-add-repository ppa:ansible/ansible`

`$ sudo apt-get update`

`$ sudo apt-get install ansible`

## Tomcat install

`$ docker pull cloudesire/tomcat:7-jre8`

`$ docker run --detach -p 8888:8080 -e TOMCAT_PASS="thispass" cloudesire/tomcat:7-jre8`

then go to the url of the AWS Instance containing Tomcat then hit 'Manager App' then enter 'admin' as username and 'thispass' as password