=========

## Spring Boot + Postgresql + Docker Compose 

### Prepair

Launch 1 EC2 Amazon Linux

Install docker, docker-compose:  
```sh
sudo yum install git -y
sudo yum update -y
sudo yum install -y docker
sudo service docker start
sudo usermod -a -G docker ec2-user
sudo -i
curl -L https://github.com/docker/compose/releases/download/1.23.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
exit
#Logout and Login
```

Install maven, java8:

`https://docs.aws.amazon.com/neptune/latest/userguide/iam-auth-connect-prerq.html`

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
In Browser check this link `http://<EC2-PUBLIC-IP>:12345/v1/product/product001`
if success, browser will show something like this:
`{"product":{"id":1,"name":"product001","new":false},"result":{"success":true,"message":"Success"}}`

### REFERENCES: 
https://muzir.github.io/spring/docker/docker-compose/postgres/2019/03/24/Spring-Boot-Docker.html
