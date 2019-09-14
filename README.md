# Install_DockerCE_Compose
Install Docker CE and Docker compose.

## Remove docker if it is installed on your instance.  If you have custome docker containers created I suggest pushing them to your docker hub account before proceeding. Obviously, don't include the $.
```
$ sudo apt remove docker docker-engine docker.io
```

## Get the necessary package from docker
```
$ sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
```
## Get docker gpg key
```
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
## Verify finger print.
```
$ sudo apt-key fingerprint 0EBFCD88
```
## Add the stable docker repo
```
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```
## Update your package index and install docker community edition
```
$ sudo apt update
$ sudo apt install docker-ce -y
```
## Add your user account to docker group.
```
$ sudo usermod -aG docker $USER
```
## Reboot your instance our you will not be able to run docker command as your user.

## Test out your docker account.
```
$ docker --version
$ docker run ubuntu
```

