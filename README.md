# change_dir_docker
<strong>Stop docker service</strong><br>
sudo systemctl stop docker<br>
<br>
<strong>Cek service docker, pastikan sudah berhenti</strong>
sudo systemctl status docker<br>
or<br>
ps faux | grep -i docker<br>
<br>
<strong>buat directory baru docker</strong><br>
mkdir /home/docker<br>
<br>
<strong>Salin directory docker ke directory baru</strong>
rsync -avxP /var/lib/docker/ /home/docker<br>
<br>
<strong>edit service docker</strong><br>
sudo nano /lib/systemd/system/docker.service<br>
cari baris : ExecStart=/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock<br>
ganti dengan : ExecStart=/usr/bin/dockerd -g /home/docker -H fd:// --containerd=/run/containerd/containerd.sock<br>
<br>
<strong>jalankan lagi service docker</strong><br>
sudo systemctl daemon-reload<br>
sudo systemctl start docker<br>
<br>
<strong>cek docker</strong><br>
docker images<br>
docker inspect image_id | grep WorkDir<br>



