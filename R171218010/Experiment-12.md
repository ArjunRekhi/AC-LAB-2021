# Experiment 12: Docker Metadata and Labels

## Aim
To work with Metadata, Log File using Docker.

## Steps Performed
### Single Label
To add a single label use command `-l <label>=<value>`
```bash
docker run -l user=12345 -d redis
```
![l1](https://user-images.githubusercontent.com/46739435/116864342-55e88000-ac25-11eb-9a58-9361d6270ad3.png)
![l2](https://user-images.githubusercontent.com/46739435/116864339-554fe980-ac25-11eb-8c29-0532fbe34894.png)

### External File
We can use a external file to add multiple labels at a time.
```bash
echo 'user=123461' >> labels && echo 'role=cache' >> labels
docker run --label-file=labels -d redis
```
![l3](https://user-images.githubusercontent.com/46739435/116864337-54b75300-ac25-11eb-8e10-a89d662c8670.png)
![l4](https://user-images.githubusercontent.com/46739435/116864330-53862600-ac25-11eb-87db-2256544aa1f7.png)

