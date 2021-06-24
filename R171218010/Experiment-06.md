# Experiment 6: Docker Linking and Monitoring

## Aim
To create containers and link them.

## Steps Performed
- Run a container in detach mode (-d) with name "db" and image "traning/postgress" `docker run -it -d --name db training/postgress`
![7](https://user-images.githubusercontent.com/46739435/114682628-e3bf0280-9d2c-11eb-8a36-62cb79baa66d.png)

- Run another container in detach mode with name "web" and image "training/webapp" and link it to container "db" with alias "mydb". `docker run -it -d -–name web -–link db:mydb  training/webapp python app.py`
![9](https://user-images.githubusercontent.com/46739435/114682637-e588c600-9d2c-11eb-911e-cfdb9d79dc47.png)

- Run `docker exec -it web bash` and run `ping mydb` to verify connection.
![8](https://user-images.githubusercontent.com/46739435/114682636-e4579900-9d2c-11eb-8af2-bf1eacf4f9f7.png)
