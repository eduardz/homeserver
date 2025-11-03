#### Deploy container (docker) aplications 
User applications, no root access

#### Updates + Security
Crontab updates
```
0 4 * * * docker compose -f /home/debian/docker/arr/docker-compose.yaml pull && docker compose -f /home/debian/docker/arr/docker-compose.yaml up -d  > /dev/null 2>&1
```



