VM paraméterei:
4096 RAM
32GB tárhely
Debian 11 Bullseye

Tárhely kiosztás:
/opt 10%
/tmp 10%
swap 5%
/ maradék 100%-a

Openjdk 8 és 11 telepítése és beállítása
nano /etc/apt/source.list
	deb http://security.debian.org/debian-security stretch/updates main
apt-get update
apt-get install openjdk-8-jdk
apt-get install openjdk-11-jdk
update-alternatives --config javac
	2-es szám
	
Felhasználó hozzáadása:
useradd -m -d /opt/udemx udemx
passwd udemx
	udemx

SSH beállítása: 
ssh 2222 porton

Apache telepítése	
apt-get install apache2
systemctl enable apache2

MariaDB telepítése:
apt-get install mariadb-server
mysql_secure_installation

docker telepítése
sudo apt install apt-transport-https ca-certificates curl gnupg2 software-properties-common
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
sudo apt update
apt-cache policy docker-ce
sudo apt install docker-ce
sudo systemctl status docker

docker run -it hello-world 
docker ps -a 

git telelpítése
apt upgrade
apt install git
apt-get update
apt-get install make libssl-dev libghc-zlib-dev libcurl4-gnutls-dev libexpat1-dev gettext unzip
wget  https://github.com/git/git/archive/refs/heads/master.zip
unzip master.zip
cd git-master
make prefix=/usr/local all
make prefix=/usr/local install
git config --global user.name "udemx@udemx.eu"
git config --global user.email "udemx@udemx.eu"


