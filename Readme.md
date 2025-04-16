# sogo-dark-theme
Dark theme for SOGo web mail client used in mailcow dockerized

Created by mailcow official documentation - https://docs.mailcow.email/manual-guides/SOGo/u_e-sogo/#apply-custom-sogo-theme

## How to install
Download theme to /opt/mailcow-dockerized/data/conf/sogo/
``` bash
cd /opt/mailcow-dockerized/data/conf/sogo/
wget https://github.com/thechevycarguy/Sogo-Dark-Theme/blob/main/custom-theme.css
```
Update or create /opt/mailcow-dockerized/docker-compose.override.yml:
```yml
version: '1.1'

services:
  sogo-mailcow:
    volumes:
      - ./data/conf/sogo/custom-theme.css:/usr/lib/GNUstep/SOGo/WebServerResources/css/theme-default.css:z
```
Recreate containers:
```bash
cd /opt/mailcow-dockerized/ && docker compose up -d
```
Restart your browser and clear the cache `CTRL+F5`
