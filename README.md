<h1 align="center">Chasm Network Node Incentiv</h1> 

```bash
Minimum Requirements:
2 vCPU
4GB RAM
50GB SSD
```
```bash
➡️ Go to : https://console.groq.com/keys
➖ Save API Key
```
```bash
➡️ Go to : https://scout.chasm.net/private-mint
➖ Mint this with 0.025 $MNT Gas fee
➖ After minting, click on _mint(scout) button
➖ Copy the value of SCOUT_UID and WEBHOOK_API_KEY
➖ Done
```
```bash
➡️ Go to : https://dashboard.ngrok.com/signup
➖ Go to Your Authtoken
➖ Click on Show Authtoken button in the corner
➖ Copy & Save 
```
## Install
```bash
sudo apt update && sudo apt upgrade -y
```
```bash
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
```
```bash
sudo apt-get update
```
```bash
sudo apt-get install ca-certificates curl
```
```bash
sudo install -m 0755 -d /etc/apt/keyrings
```
```bash
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
```
```bash
sudo chmod a+r /etc/apt/keyrings/docker.asc
```
```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
```bash
sudo apt-get update
```
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
```bash
sudo apt install screen -y
```
```bash
curl -s https://ngrok-agent.s3.amazonaws.com/ngrok.asc | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null && echo "deb https://ngrok-agent.s3.amazonaws.com buster main" | sudo tee /etc/apt/sources.list.d/ngrok.list && sudo apt update && sudo apt install ngrok
```
## Install Ngrok
# Buat Screen Dulu 
```bash
screen -S ngrok
```


![Cuplikan layar 2024-07-27 193835](https://github.com/user-attachments/assets/ec5462e8-70cf-490a-abc9-75f47982cf70)

![photo_2024-07-27_17-35-38](https://github.com/user-attachments/assets/9077054e-efd5-4b0e-9fab-ccd201efc26d)

![Cuplikan layar 2024-07-27 193853](https://github.com/user-attachments/assets/701655b1-2f4c-453b-b4f7-da83649c8ae6)

## ngrok contoh paste di dalam terminal ( docker run --net=host -it -e NGROK_AUTHTOKEN=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx ngrok/ngrok:latest http 3001 ) ENTER

## kalo sudah jalan ngrok nya CTRL+A+D

## Ambil Di Ngrok URL nya Di Dalam Website Ngrok Di Endpoints CONTOH ( https://1bXX.XX.XXX.XXX.ngrok-free.app )

## Install Nano .env
```bash
nano .env
```

# ISI .ENV JIKA SUDAH SAVE CTRL+X Y ENTER
```bash
PORT=3001
LOGGER_LEVEL=debug
ORCHESTRATOR_URL=https://orchestrator.chasm.net
PROVIDERS=groq
MODEL=gemma2-9b-it
SCOUT_UID=
WEBHOOK_API_KEY=
WEBHOOK_URL=
GROQ_API_KEY=
SCOUT_NAME=
```
```bash
ufw allow 3001
```
```bash
docker pull chasmtech/chasm-scout:latest
```
```bash
docker run -d --restart=always --env-file ./.env -p 3001:3001 --name scout chasmtech/chasm-scout
```
## CEK Server Status
```bash
docker logs scout
```
## CEK Monitor Scout Performance
```bash
docker stats scout
```
