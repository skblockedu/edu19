# 2.3. Channel 생성 및 조인
```shell
cd ~/fabric-samples/first-network/
./start2_3.sh up -s couchdb
```
- peer channel create -o orderer.example.com:7050 -c mychannel -f ./channel-artifacts/channel.tx --tls true --cafile $ORDERER_CA   # mychannel.block 생성
- peer channel join -b mychannel.block   # on each peers

## view channel
```shell
docker exec -it cli bash # -it은 Docker에게 컨테이너의 표준 입력에 연결된 pseudo-TTY를 할당하여 대화 형 bash 쉘을 컨테이너에 작성
env | grep CORE
```
* Result
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_3_1.png)


```shell
peer channel list
```
* Channels peers has joined: mychannel
![](https://github.com/skblockedu/edu19/blob/master/images/Session2_3_2.png)

## view chaincode (현재 chaincode는 설치되지 않은 상태임)
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

["3.1. Chaincode 설치" >>](https://github.com/skblockedu/edu19/blob/master/Session3_1.md)
