# Jitsi Meet Docker Skyclick

realizar la instalacion como Super Usuario
## Setup

Instalar dependencias 
```bash
apt update ; apt install -y build-essential net-tools curl git software-properties-common neofetch apt-transport-https ca-certificates curl gnupg-agent docker.io docker-compose
```
```bash
systemctl enable --now docker ; usermod -aG docker $USER ; newgrp docker
```
## Clonar Repositorio

```bash
git clone https://github.com/DgamonP/docker-jitsi-skyclick && cd docker-jitsi-skyclick
```
## Installation

```bash
cp env.example .env
```
_Verificar valores de IP local y hostname_

```
hostname -I
```
Resultado tu direccion IP local

```
hostname
```
Resultado "www.room.skyclick.com" o **asigne un dominio propio**

_Editar el archivo .env_
modifique los siguientes valores

**HTTP_PORT=80**

**HTTPS_PORT=443**

**TZ=Asia/Kolkata**

**PUBLIC_URL="https://www.yourdomain.com"**

**DOCKER_HOST_ADDRESS=yourIPlocal**

**ENABLE_HTTP_REDIRECT=1**

```bash
nano .env
```
_Generar claves Jitsi_

```bash
./gen-passwords.sh
```
_Crear las carpetas de configuracion_

```bash
mkdir -p ~/.jitsi-meet-cfg/{web/letsencrypt,transcripts,prosody/config,prosody/prosody-plugins-custom,jicofo,jvb,jigasi,jibri}
```

## Desplegar con Docker-compose 🚀

```bash
docker-compose up -d
```



