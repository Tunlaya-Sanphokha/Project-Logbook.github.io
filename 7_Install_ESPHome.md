# ติดตั้ง ESPHome  
### Install ESPHome container  
#### Docker-compose  
เราจะทำการเพิ่มการกำหนด config สำหรับ ESPHome container ในไฟล์ docker-compose.yaml เหมือนเช่นที่ผ่านมา โดยเพิ่ม code ดังนี้   

```
services:
  [...]

  esphome:
    container_name: esphome
    image: esphome/esphome
    restart: unless-stopped
    ports:
      - "6052:6052/tcp"
    environment:
      - TZ=Europe/Brussels
    # mDNS doesn't work across VLANs, use static IP for devices when disabling mDNS
    #   - ESPHOME_DASHBOARD_USE_PING=true
    volumes:
      - /opt/esphome/config:/config
      - /etc/localtime:/etc/localtime:ro
    # devices:
    #   - /dev/ttyUSB0:/dev/ttyUSB0
    network_mode: host
```

