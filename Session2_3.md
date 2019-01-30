# 2.3. Channel 생성 및 조인
```
cd ~/fabric-samples/first-network/
./start2_3.sh up -s couchdb
```

## view channel
```shell
docker exec -it cli bash
env | grep CORE
```
* Result
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_3_1.png)


```shell
peer channel list
```
* Channels peers has joined: mychannel
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_3_2.png)

## view chaincode
```
peer chaincode list
```
* Error
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_3_3.png)

```
peer chaincode list --installed
```
* Result
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_3_4.png)
