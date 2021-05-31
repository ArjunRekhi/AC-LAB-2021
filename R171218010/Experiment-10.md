# Experiment 10: Using .dockerignore

## Aim
To build docker image using .dockerignore file.

## Steps Performed
- Create a simple `Dockerfile` to demonstrate the experiment.
![A6](https://user-images.githubusercontent.com/46739435/116842274-9af6bd00-abf9-11eb-8e07-67d447817365.png)

- Create a file with name `.dockerignore`.
![A5](https://user-images.githubusercontent.com/46739435/116842273-9af6bd00-abf9-11eb-8e48-a8d89cde6c8f.png)

- Add file name in `.dockerignore` to be ignored by docker engine while building image.
![A4](https://user-images.githubusercontent.com/46739435/116842272-9a5e2680-abf9-11eb-918c-da3a7c6f86a5.png)

- Use command `docker build -t nosecret .` to build image.
![A2](https://user-images.githubusercontent.com/46739435/116842268-99c59000-abf9-11eb-923e-c6b11c9b7dad.png)

- Use command `docker run nosecret ls /app` to verify results.
![A1](https://user-images.githubusercontent.com/46739435/116842266-98946300-abf9-11eb-8c93-46039b13025f.png)

