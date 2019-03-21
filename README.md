# rdeck-slackware "Runware"
Unofficial Rundeck port for Slackware Linux

![alt text](https://readonlyfridayshome.files.wordpress.com/2019/03/rundeck_slackware.png)

# Requisites
1. Slackware Linux 14.2 64 bits.
2. Java 8, you can obtain it from here: 

http://www.slackware.com/~alien/slackbuilds/openjdk/pkg64/14.2/openjdk-8u201_b08-x86_64-1alien.txz

3. Create rundeck group and user:
```
groupadd -g 263 rundeck
useradd -g 263 -u 263 -r -s /bin/bash -d /var/lib/rundeck rundeck
```
# Steps to build Rundeck Slackware package
1. git clone https://github.com/reinerrdeck/rdeck-slackware
2. cd rdeck-slackware/
3. tar xvf rundeck-3.0.17.tar.gz
4. cd var/lib/rundeck/bootstrap/
5. wget -c https://dl.bintray.com/rundeck/rundeck-maven/rundeck-3.0.17-20190311.war 
6. cd ../../../../../
7. tar cfJ rundeck-3.0.17.tar.xz rundeck-3.0.17
8. mv rundeck-3.0.17.tar.xz build/
9. cd build/
10. chmod +x rundeck.SlackBuild
11. ./rundeck.Slackbuild (as root)

The build process takes a moment, depending of your hardware.

The package is generated in /tmp directory.

# How to install Rundeck package
```
installpkg /tmp/rundeck-3.0.17-x86_64-1_SBo.txz
```
# How to launch Rundeck
```
. /etc/rc.d/rc.rundeck start
```
The launch process may take some time, depending of your hardware.

# How to access to Rundeck
Go to http://localhost:4440 in your web browser.

user:admin
password:admin

# How to stop Rundeck
```
. /etc/rc.d/rc.rundeck stop
```
# Documentation
https://docs.rundeck.com/docs/

Custom Rundeck logo by: G3NSVRV.

©2019 Rundeck. All Rights Reserved.
