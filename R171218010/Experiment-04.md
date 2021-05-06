# Experiment 4: Docker Networking

## Aim
To create a docker image using docker file, change tag and push it to DockerHub.

## Steps Performed
- Create a Dockerfile in any directory using `vim Dockerfile`.
![z1](https://user-images.githubusercontent.com/46739435/107844400-13b75b80-6df9-11eb-9c7f-8d53fb28e076.png)

- Dockerfile to create nginx server.
    ```Dockerfile
    FROM ubuntu
    RUN apt-get update
    ENV DEBIAN_FRONTEND noninteractive
    RUN apt-get install nginx -y
    RUN echo "daemon off;" >> /etc/nginx/nginx.conf
    COPY index.html /var/www/html/
    EXPOSE 80
    CMD ["nginx"]
    ```

- Create a index.html.
    ```html
    <html>
    <h1>Level Up In Tech</h1>
     <p> Learning it. Labbing it. Leveling Up</p>
     <p>This is a simple static website, built and deliver from a docker container</p>
     <p>Visit us here: <a href="levelupintech.com">Level Up In Tech</a></p>
    </html>

    ```

- Run command: `docker build -t nginx:1.0 .` to build image.
![z2](https://user-images.githubusercontent.com/46739435/107844402-14e88880-6df9-11eb-938f-0987d9d8351b.png)

- Verify if image is build `docker images`.
![z3](https://user-images.githubusercontent.com/46739435/107844403-1619b580-6df9-11eb-8c04-7ed4334e6954.png)

- Login to DockerHub from CLI to push image. `docker login`
![z4](https://user-images.githubusercontent.com/46739435/107844404-16b24c00-6df9-11eb-8fcc-ef58f040b099.png)

- Change tag of image with your username `docker tag {old_name} {username}/{new_name}`
![z5](https://user-images.githubusercontent.com/46739435/107844406-174ae280-6df9-11eb-8027-59b96a253696.png)

- Verify if tag is changed `docker images`.
![z6](https://user-images.githubusercontent.com/46739435/107844407-17e37900-6df9-11eb-87d0-754dea12f6b1.png)

- Push the image to DockerHub. `docker push {username}/{image_name}`
![z7](https://user-images.githubusercontent.com/46739435/107844409-187c0f80-6df9-11eb-8cf6-53411b44abf7.png)

- Verify at DockerHub. [DockerHub](https://hub.docker.com/)
![z8](https://user-images.githubusercontent.com/46739435/107844410-187c0f80-6df9-11eb-9173-b0618d8a266f.png)

- Remove image from local computer. `docker rmi {image_name}`

- Use command `docker run -dit -p 5000:80 {username}/{image_name}:{tag}` to pull image and run container. -p is used to bind port 80 of container to 5000 of local.
![z9](https://user-images.githubusercontent.com/46739435/107844411-19ad3c80-6df9-11eb-87f5-c06df28a86b9.png)

- Goto [http://localhost:5000](http://localhost:5000) to verify running.
![z10](https://user-images.githubusercontent.com/46739435/107844413-1a45d300-6df9-11eb-8353-b18bd4c1d8cf.png)


