# 3.1. Chaincode 설치
## view container before
```
docker container ls
```
![container ls](https://github.com/skblockedu/edu19/blob/master/images/Session3_1_2.png)


## chaincode 설치
```
cd ~/fabric-samples/first-network/
./start3_1.sh up -s couchdb
```
- peer chaincode install -n mycc -v 1.0 -l golang -p github.com/chaincode/chaincode_example02/go/
- peer chaincode instantiate -o orderer.example.com:7050 --tls true --cafile $ORDERER_CA -C mychannel -n mycc -l golang -v 1.0 -c '{"Args":["init","a","100","b","200"]}' -P 'AND ('\''Org1MSP.peer'\'','\''Org2MSP.peer'\'')'
- peer chaincode query -C mychannel -n mycc -c '{"Args":["query","a"]}'
- $ORDERER_CA: /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem

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
![couchd1](https://github.com/skblockedu/edu19/blob/master/images/couch1.png)


## view ledger file
```
docker exec -it peer0.org1.example.com bash
ls /var/hyperledger/production/ledgersData/chains/chains/mychannel/  # channel 별로 ledger file이 
```
