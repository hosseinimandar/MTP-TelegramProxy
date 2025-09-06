# MTProto Proxy (Docker)

This repository provides a step-by-step guide to install and run **MTProto Proxy** using **Docker**.  
With this method, you can easily set up an MTProto Proxy on port **443**.

---

## 🚀 Installation Steps

### 1. Update the system
apt update && apt upgrade -y

### 2. Install Docker
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh

### 3. Run MTProto Proxy
docker run -d --name=mtproxy-443 --restart=always -p 443:443 \
-v mtproxy-config-443:/data \
-e SECRET="ee6d6565742e676f6f676c652e636f6d" \
-e TAG=205d5dfddd0936a2a402a13e26498514 \
telegrammessenger/proxy:latest

---

## 🔍 Check Status

### List running containers
docker ps

### View logs
docker logs mtproxy-443

---

## ⚙️ Parameters
- `SECRET` → The proxy secret key (you can generate your own).  
- `TAG` → The proxy tag used for Telegram MTProxy promotion.  
- `-p 443:443` → Exposes the proxy on port **443**.  

---

## 📖 References
- [Docker Official Install Guide](https://docs.docker.com/get-docker/)  
- [Telegram MTProxy Docker Image](https://hub.docker.com/r/telegrammessenger/proxy)  

---
