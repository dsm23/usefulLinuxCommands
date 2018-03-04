# usefulLinuxCommands

## Ubuntu/Debian

#### Initial setup

> ```
> sudo apt install htop git curl pm-utils`
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

#### Distro Upgrade

> ```
> https://help.ubuntu.com/lts/serverguide/installing-upgrading.html
> 
> do-release-upgrade
> ```

#### Java 8

> ```
> wget --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u162-b12/0da788060d494f5095bf8624735fa2f1/jdk-8u162-linux-x64.tar.gz
> wget --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u162-b12/0da788060d494f5095bf8624735fa2f1/jre-8u162-linux-x64.tar.gz
> tar zxvf jdk-8u162-linux-x64.tar.gz
> tar zxvf jre-8u162-linux-x64.tar.gz
> sudo cp -avr jdk1.8.0_162 jre1.8.0_162 /opt
> sudo update-alternatives --install /usr/bin/java java /opt/jdk1.8.0_162/bin/java 100
> sudo update-alternatives --install /usr/bin/javac javac /opt/jdk1.8.0_162/bin/java 100
> sudo update-alternatives --install /usr/bin/java java /opt/jre1.8.0_162/bin/java 100
> java -version
> ```

#### Java 9

> ```
> wget --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/9.0.4+11/c2514751926b4512b076cc82f959763f/jdk-9.0.4_linux-x64_bin.tar.gz
> wget --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/9.0.4+11/c2514751926b4512b076cc82f959763f/jre-9.0.4_linux-x64_bin.tar.gz
> sudo tar zxvf jdk-9.0.4_linux-x64_bin.tar.gz -C /opt/
> sudo tar zxvf jre-9.0.4_linux-x64_bin.tar.gz -C /opt/
> sudo update-alternatives --install /usr/bin/java java /opt/jdk-9.0.4/bin/java 100
> sudo update-alternatives --install /usr/bin/javac javac /opt/jdk-9.0.4/bin/java 100
> sudo update-alternatives --install /usr/bin/java java /opt/jre-9.0.4/bin/java 100
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

#### Lamp server

> ```
> 
> ```

#### Atom

> ```
> wget https://atom.io/download/deb
> ```

#### Eclipse

> ```
> wget http://mirror.switch.ch/eclipse/oomph/epp/oxygen/R2/eclipse-inst-linux64.tar.gz
> ```

#### IntelliJ and WebStorm

> ```
> wget https://download.jetbrains.com/idea/ideaIC-2017.3.4.tar.gz
> sudo tar zxvf ideaIC-2017.3.4.tar.gz -C /opt/
> sudo touch jetbrains-idea-ce.desktop
> 
[Desktop Entry]
Version=1.0
Type=Application
Name=IntelliJ IDEA Community Edition
Icon=/opt/idea-IC-173.4548.28/bin/idea.png
Exec="/opt/idea-IC-173.4548.28/bin/idea.sh" %f
Comment=The Drive to Develop
Categories=Development;IDE;
Terminal=false
StartupWMClass=jetbrains-idea-ce
> 
> sudo mv ~/jetbrains-idea-ce.desktop /usr/share/applications/
> ```

#### Sublime Text 3

> ```
> wget https://download.sublimetext.com/sublime_text_3_build_3143_x64.tar.bz2
> sudo tar xjvf sublime_text_3_build_3143_x64.tar.bz2 -C /opt/
> ```

#### C++

> ```
> sudo apt install g++
> ```

#### C#

> ```
> http://www.mono-project.com/download/stable/
> ```

#### Apache

> ```
> sudo apt install apache2
> ```

#### MySQL

> ```
> sudo apt install mysql-server
> ```

#### PHP 7

> ```
> sudo apt install php7.0 libapache2-mod-php php-mcrypt php-mysql
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