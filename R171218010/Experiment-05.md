# Experiment 5: Docker Compose

## Aim
To create docker-compose for 'nginx' and 'mySQL'

## Steps Performed
- Create `docker-compose.yml`
```yaml
version: '3'
services:
 databases:
  image: mysql
  ports:
   - "3307:3306"
  env_file:
   - evs.env   
 web:
  image: nginx   
  ports:
   - "80:80" 
  depends_on:
   - databases
```
![1](https://user-images.githubusercontent.com/46739435/114682605-df92e500-9d2c-11eb-8d9a-e0020fe76fe5.png)
![4](https://user-images.githubusercontent.com/46739435/114682617-e1f53f00-9d2c-11eb-80fd-0116fce10064.png)

- Create `evs.env` to create environment file.
```env
MYSQL_ROOT_PASSWORD=redhat08
MYSQL_DATABASE=nginxdb
MYSQL_USER=root
```
![2](https://user-images.githubusercontent.com/46739435/114682609-e0c41200-9d2c-11eb-8a76-3ca74524a403.png)
![3](https://user-images.githubusercontent.com/46739435/114682613-e15ca880-9d2c-11eb-89f7-262e98ce9432.png)

- Run `docker-compose up` command.
![5](https://user-images.githubusercontent.com/46739435/114682619-e28dd580-9d2c-11eb-96f7-c952b7c2e936.png)

- `docker ps` to verify compose setup.
![6](https://user-images.githubusercontent.com/46739435/114682624-e3266c00-9d2c-11eb-81ee-452e7c2198e4.png)