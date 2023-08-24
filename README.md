A redis local in-memory storage for trade data. Create a docker network and run redis server. 

0! create network 

sudo docker network create momentum_network

1 build

sudo docker build -t momentum_redis .

2 run

sudo docker run -d --restart always --name momentum_redis_container --network momentum_network --log-opt mode=non-blocking --log-opt max-size=10m --log-opt max-file=3 redis:latest

3 stop

sudo docker stop momentum_redis_container

4 remove

sudo docker rm momentum_redis_container

5 logs

sudo docker logs momentum_redis_container
