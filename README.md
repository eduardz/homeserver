#### Docker Applications Deployment

This repository contains configuration files and instructions for deploying containerized applications using **Docker Compose**.  
All applications are run without requiring root access.



#### Deploy container (docker) aplications 
Applications, no root access
To start or redeploy containers:
```bash
cd ~/docker/app
docker compose up -d
```

All in one solution: 
#### Updates + Security
Crontab updates
```
0 4 * * * docker compose -f /home/debian/docker/arr/docker-compose.yaml pull && docker compose -f /home/debian/docker/arr/docker-compose.yaml up -d  > /dev/null 2>&1
```

#### Monitor & restart on demand (proposed HomeAssistant)
With HomeAssistant + Android app: HomeAssistant

