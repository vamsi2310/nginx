# nginx
#web app dockerized
This is a Hello world program on microsoft azure Centos virtual machine.
Stpes followed are as follows :
1. Create the Virtual machine with SSH and HTTP requests open
2. install Docker
sudo yum update
sudo dnf update
sudo dnf config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo
sudo dnf install docker-ce --nobest
sudo systemctl enable --now docker
3. write a simple HTML file (attached)
4. Write the Docker file
FROM nginx:alpine
COPY . /usr/share/nginx/html
5. Login to Docker
6. Build the container
go to the dir. where html and Dockerfile are present, run the following command
sudo docker build -t vamc2310/nginx:nginx-website-v1 ./
7. Push the container to the git hub repo.
sudo docker push vamc2310/nginx:nginx-website-v1
8. Run the container
sudo docker run -d -p 8080:80 vamc2310/nginx:nginx-website-v1
d = debug
p = port setup 
8080 = azure VM port
80 = container port for nginx
9. test the working on azure VM
curl 0.0.0.0:8080
curl 127.0.0.1:8080
10. test the working of website from interner (from any browser from a different PC)
http://<Azure VM IP address>:8080
  Your index.html will appear
 
