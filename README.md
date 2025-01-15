# Docker_Assets
Configurations scripts and container YAMLs

Initial setup
1. Install Ubuntu 24.04 Server (Or latest)
   
2. Following install and restart login as user created during setup
sudo apt update
sudo apt upgrade
sudo apt update && sudo apt -y install open-vm-tools  #Install VM WAre tools for ESXI if required

4. Install docker
sudo apt install docker.io -y
sudo systemctl status docker

If server is not started you can sudo systemctl start docker

sudo usermod -aG docker $USER
Needs logout or reboot 

4. Install Portainer, container management GUI
docker pull portainer/portainer-ce:latest

docker images   #should list the image installed above
docker run -d -p 9000:9000 --restart always -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer-ce:latest
docker ps

http://server-ip:9000  # Portainer should now be running on teh servers IP and port number

5. Portainer Config
If restoring from backup do not set username and password.  On that screen at the bottonm is option to restore config file.







