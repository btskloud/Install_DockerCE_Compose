# Install Docker CE and Docker Compose.
*************************************
# Install Docker Community Edition

### Remove docker if it is installed on your instance.  If you have custome docker containers created I suggest pushing them to your docker hub account before proceeding. Obviously, don't include the $.
```
sudo apt remove docker docker-engine docker.io
```

### Get the necessary package from docker
```
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
```
### Get docker gpg key
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
### Verify finger print.
```
sudo apt-key fingerprint 0EBFCD88
```
### Add the stable docker repo
```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```
### Update your package index and install docker community edition
```
sudo apt update
sudo apt install docker-ce -y
```
### Add your user account to docker group.
```
sudo usermod -aG docker $USER
```
### Reboot your instance or you will not be able to run docker command as your user.

### Test out your docker account.
```
docker --version
docker run ubuntu
```
# YOU'RE DONE ENJOY Docker CE...
****************************************
# Install Docker Compose

## Find current release of Docker Compose.
[link to latest version of Docker Compose](https://github.com/docker/compose/releases)

## Replace the version "1.25.0-rc2" with the latest version. 
```
sudo curl -L https://github.com/docker/compose/releases/download/1.25.0-rc2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

docker-compose --version
```
# YOU'RE DONE.. Enjoy Docker Compose.


