# 3.1. Chaincode 설치
## view container before
```
docker container ls
```
![container ls](https://github.com/skblockedu/edu19/blob/master/images/Session3_1_2.png)


## 설치
```
cd ~/fabric-samples/first-network/
./start3_1.sh up -s couchdb
```

## view container after
```
docker container ls .  # 결과는 나오나 너무 길게 보임
docker container ls --format 'table {{.ID}}\t{{.Names}}\t{{.Image}}\t{{.Status}}'
```
![containe ls](https://github.com/skblockedu/edu19/blob/master/images/Session3_1_1.png)


## view couchdb database 
```
http://localhost:5984/_utils   # couchdb0, new database ( mychannel_, mychannel_lscc, mychannel_mycc )                            
http://localhost:6984/_utils   # couchdb1
http://localhost:7984/_utils   # couchdb2
http://localhost:8984/_utils   # couchdb3
```

## view ledger file
```
docker exec -it peer0.org1.example.com bash
ls /var/hyperledger/production/ledgersData/chains/chains/mychannel/  # channel 별로 ledger file이 
```
