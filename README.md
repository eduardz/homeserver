#### Container Applications Deployment

This repository contains configuration files and instructions for deploying containerized applications using **Docker Compose** but also **Nerdctl**
All applications run without requiring root access / sudo  but still rootful . 



#### Deploy process either compose or cli 
To start or redeploy containers:

| Docker | Nerdctl |
|---------|----------|
| [Docker Cheatsheet](https://docs.docker.com/get-started/docker_cheatsheet.pdf)  | [ NerdCTL CheatSheet](https://github.com/containerd/nerdctl/blob/main/docs/command-reference.md) | 
| `docker compose up -d ` | `nerdctl compose up -d` |
| ` docker run` | `nerdctl run`



All in one solution: 
#### Updates + Security
Crontab updates
```
0 4 * * * docker compose -f /home/debian/docker/arr/docker-compose.yaml pull && docker compose -f /home/debian/docker/arr/docker-compose.yaml up -d  > /dev/null 2>&1
```

#### Monitor & restart on demand (proposed HomeAssistant)
With HomeAssistant + Android/IOS App: HomeAssistant under VPN 

