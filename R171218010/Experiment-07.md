# Experiment 6: Docker swarm

## Aim
To create docker swarm cluster.

## Steps Performed
- Intialize docker swarm using command `docker swarm init`
![d1](https://user-images.githubusercontent.com/46739435/114967572-539acd80-9e92-11eb-9775-a2f2f6e5ba31.png)

- `docker swarm init` will generate a command with token which is to be used by other nodes to join the cluster.

- Join the cluster using command (copied from output of `docker swarm init`). `docker swarm join --token SWMTKN-1-0mb96yjo0lsb2hwp6fij26vqwshzcypdons7va039kggo58z39-712kz2bt6k0200lyob3v9zz70 172.17.0.42:2377`
![d2](https://user-images.githubusercontent.com/46739435/114967570-53023700-9e92-11eb-8f60-cc3e75d03fed.png)

- Use command `docker node ls` to list all connected nodes.
![d3](https://user-images.githubusercontent.com/46739435/114967568-5269a080-9e92-11eb-8018-236255b339e7.png)

- Create a overlay network with name "mNetwork". All the containers connected to this network can communicate with each other. `docker network create -d overlay mNetwork`
![d4](https://user-images.githubusercontent.com/46739435/114967565-51387380-9e92-11eb-8a3b-f643137dc1b3.png)

- Docker swarm service is used to run container on the swarm cluster. Using command `docker service create --name http --network mNetwork --replicas 2 -p 80:80 katacoda/docker-http-server`
![d5](https://user-images.githubusercontent.com/46739435/114967561-509fdd00-9e92-11eb-9dc5-196f2c7482f0.png)

- `docker service ls` can be used to view services runing on the cluster.
![d6](https://user-images.githubusercontent.com/46739435/114967560-50074680-9e92-11eb-8470-eed3f1775682.png)

- `docker ps` on first node.

![d7](https://user-images.githubusercontent.com/46739435/114967559-4f6eb000-9e92-11eb-9f6f-92668ffbf915.png)

- `docker ps` on second node.
![d7 (copy)](https://user-images.githubusercontent.com/46739435/114967558-4f6eb000-9e92-11eb-97c8-9b1d778ba2fb.png)

- `docker service inspect --pretty http` can be used to view details of service in pretty format.
![d8](https://user-images.githubusercontent.com/46739435/114967554-4da4ec80-9e92-11eb-9eb1-cc51f86a0ef6.png)

- Request to the service will be processed by two containers. Use `curl host01` to verify.
![d9](https://user-images.githubusercontent.com/46739435/114967556-4ed61980-9e92-11eb-82e2-bcb1ec1bfa28.png)


