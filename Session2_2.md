# 2.2. Container 구동
```
cd ~/fabric-samples/first-network
./start2_2.sh up -s couchdb
(docker-compose -f docker-compose-cli.yaml -f docker-compose-couch.yaml up -d)
```

## docker-compose configuration file 

## check docker image/container/network

```
docker image ls
```
* orderer, peer, couchdb, tools(CLI)

![](https://github.com/skblockedu/edu19/blob/master/images/Session2_2_1.png)

```
docker container ls
```
* 1 orderer, 4 peers, 4 couchdb, 1 cli
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_2_2.png)

```
docker network ls
```
* new network (net_byfn)
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_2_3.png)

## check couchdb database
```
http://localhost:5984/_utils   # couchdb0
http://localhost:6984/_utils   # couchdb1
http://localhost:7984/_utils   # couchdb2
http://localhost:8984/_utils   # couchdb3
```
* Port fowarding
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_2_4.png)

* couchdb0
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_2_5.png)
