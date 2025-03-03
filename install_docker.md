# install docker
<strong>install_docker</strong><br>
sudo apt update<br>
sudo apt install apt-transport-https ca-certificates curl software-properties-common<br>
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg<br>
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null<br>
sudo apt update<br>
sudo apt install docker-ce<br>
sudo systemctl status docker<br>
<br>
<strong>make docker as sudo</strong><br>
sudo usermod -aG docker ${USER}<br>
su - ${USER}<br>
groups<br>
sudo usermod -aG docker {{username}}<br>
