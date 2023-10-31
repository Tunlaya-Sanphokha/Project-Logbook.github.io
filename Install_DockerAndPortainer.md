# ติดตั้ง Docker and Portainer  

### ติดตั้ง Docker and Docker Compose
### ติดตั้ง Docker  
ในที่นี้เราไม่ได้ทำการติดตั้ง Docker Desktop  แต่จะทำการติดตั้ง Docker Engine บน Ubuntu แทน  

โดยสามารถอ่านเอกสารได้เพิ่มเติม [ Docker Engine](https://docs.docker.com/engine/install/debian/)   

โดยจะเริ่มต้นทำการติดตั้งดังนี้  เพื่อเป็นการอัปเดตแพคเกจและติดตั้งแพคเกจในระบบ Ubuntu  

```sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
