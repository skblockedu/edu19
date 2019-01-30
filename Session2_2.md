# 2.2. Container 구동
```shell
cd ~/fabric-samples/first-network
./start2_2.sh up -s couchdb

(docker-compose -f docker-compose-cli.yaml -f docker-compose-couch.yaml up -d)
```

## docker-compose configuration file 

## check docker image
```shell
docker image ls
```
* orderer, peer, couchdb, tools(CLI)
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_2_1.png)

## check docker container
```shell
docker container ls
```
* 1 orderer, 4 peers, 4 couchdb, 1 cli
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_2_2.png)

* container list
![](https://github.com/skblockedu/edu19/blob/master/images/network3.png)

## check docker network
```shell
docker network ls
```
* new network (net_byfn)
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_2_3.png)

## check couchdb database
```
http://localhost:5984/_utils 
http://localhost:6984/_utils
http://localhost:7984/_utils
http://localhost:8984/_utils
```
* Port fowarding (VirtualBox >> 설정 >> 네트워크 >> 고급)
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_2_4.png)

* couchdb0 
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_2_5.png)

["2.3. Channel 생성 및 조인" >>](https://github.com/skblockedu/edu19/blob/master/Session2_3.md)
