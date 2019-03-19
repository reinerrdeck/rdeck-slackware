# rdeck-slackware
Unofficial Rundeck port for Slackware Linux

# Requisites
1. Slackware Linux 14.2 64 bits.
2. Java 8, you can obtain it from here: 

http://www.slackware.com/~alien/slackbuilds/openjdk/pkg64/14.2/openjdk-8u201_b08-x86_64-1alien.txz

# Steps to build Rundeck Slackware package
1. git clone https://github.com/reinerrdeck/rdeck-slackware
2. tar xvf rundeck-3.0.7
3. cd var/lib/rundeck/bootstrap/
4. wget -c https://dl.bintray.com/rundeck/rundeck-maven/rundeck-3.0.17-20190311.war 
5. cd ../../../../../
6. tar cfJ rundeck-3.0.17.tar.xz rundeck-3.0.17
7. mv rundeck-3.0.17.tar.xz build/
8. cd build/
9. chmod +x rundeck.SlackBuild
10. ./rundeck.Slackbuild (as root)

The build process takes a moment, depending of your hardware.

The package is generated in /tmp directory

# How to install Rundeck package
installpkg /tmp/rundeck-3.0.17-x86_64-1_SBo.txz

# How to launch Rundeck
. /etc/rc.d/rc.rundeck start

The launch process may take some time, depending of your hardware.

# How to access to Rundeck
Go to localhost:4440 in your web browser
user:admin
password:admin

# How to stop Rundeck
. /etc/rc.d/rc.rundeck stop

# Documentation
https://docs.rundeck.com/docs/
