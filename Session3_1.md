# 3.1. Chaincode 설치
## check container before
```
docker container ls
```

## 설치
./start3_1.sh up -s couchdb
``
## check container after
```
docker container ls
docker container ls --format 'table {{.ID}}\t{{.Names}}\t{{.Image}}\t{{.Status}}'
```

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
