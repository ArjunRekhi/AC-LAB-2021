# Experiment 11: Docker Container Restart Policy

## Aim
To prepare and implement Docker Container Restart Policy

## Steps Performed
### Stop On Fail
```bash
docker run -d --name restart-default scrapbook/docker-restart-example
docker ps -a
docker logs restart-default
```
![k1](https://user-images.githubusercontent.com/46739435/116852183-7a3a6180-ac11-11eb-8ce0-2d91931a138e.png)
![k2](https://user-images.githubusercontent.com/46739435/116852186-7b6b8e80-ac11-11eb-848c-e60caae37365.png)

### Restart on Fail
- Docker will restart the container three times before stopping.
```bash
docker run -d --name restart-3 --restart=on-failure:3 scrapbook/docker-restart-example
docker logs restart-3
```
![k3](https://user-images.githubusercontent.com/46739435/116852188-7c042500-ac11-11eb-98b1-5538d9acaa49.png)

### Always Restart
- Use the always flag to automatically restart the container when is crashes
```bash
docker run -d --name restart-always --restart=always scrapbook/docker-restart-example
docker logs restart-always
```
![k4](https://user-images.githubusercontent.com/46739435/116852190-7c042500-ac11-11eb-9ade-578c466c7752.png)
