# ติดตั้ง Docker and Portainer  

### ติดตั้ง Docker and Docker Compose
### ติดตั้ง Docker  
ในที่นี้เราไม่ได้ทำการติดตั้ง Docker Desktop  แต่จะทำการติดตั้ง Docker Engine บน Ubuntu แทน  

โดยสามารถอ่านเอกสารได้เพิ่มเติม [ Docker Engine](https://docs.docker.com/engine/install/debian/)   

โดยจะเริ่มต้นทำการติดตั้งดังนี้  เพื่อเป็นการอัปเดตแพคเกจและติดตั้งแพคเกจในระบบ Ubuntu  

```
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
ทำการเพิ่ม  Docker repositor โดยใช้คำสั่งดังต่อไปนี้  
```
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
และทำการ ติดตั้ง Docker Engine  
```
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
### ติดตั้ง Docker Compose  
เอกสารประกอบของ [Docker Compos](https://docs.docker.com/compose/install/) จะให้เราทำการติดตั้ง Docker Desktop  
ซึ่งเราไม่จำเป็นต้องดาวน์โหลด Docker Compose จาก [GitHub](https://github.com/docker/compose/releases)   
เนื่องจากจริงๆ แล้วมันถูกรวมไว้ระหว่างการติดตั้ง Docker Engine สิ่งเดียวที่เราต้องทำคือทำการเชื่อมโยงไปยังไฟล์ปฏิบัติการและให้สิทธิ์ในการดำเนินการ โดยใช้คำสั่งต่อไปนี้  

```
sudo ln -s /usr/libexec/docker/cli-plugins/docker-compose /usr/bin/docker-compose
sudo chmod u+x /usr/bin/docker-compose
```
### Setting up permissions
ต่อไปเราจะทไการตั้งค่า เพื่ออนุญาตให้ผู้ใช้ที่ไม่ใช่ผู้ดูแลระบบ (ในที่นี้จะตั้งชื่อว่า sysadmin) เพื่อดำเนินการรูทโดยใช้ sudo และเรียกใช้ docker และ docker-compose  
```
su # enter root password
# install sudo
apt install sudo
gpasswd -a sysadmin sudo
# add sysadmin to docker group
gpasswd -a sysadmin docker
```
Exit SSH session and login as the non-admin user again for changes to apply.


