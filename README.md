=========

## Spring Boot + Postgresql + Docker Containers

### How to run 

```sh
git clone https://github.com/hoangmnsd/spring-gradle-postgres-docker

cd spring-gradle-postgres-docker

./cleanRun.sh
```

### How to test

Using Postman, send POST request to `http://<EC2-PUBLIC-IP>:12345/v1/product` with body:  
```
{"name":"product001"}
```

if `success`:  
```
{
    "product": {
        "id": 1,
        "name": "product001",
        "new": false
    },
    "result": {
        "success": true,
        "message": "Success"
    }
}
```

### REFERENCES: 
https://muzir.github.io/spring/docker/docker-compose/postgres/2019/03/24/Spring-Boot-Docker.html
