# 3.2. Chaincode query & invoke

## chaincode query
```shell
docker exec -it cli /bin/bash
peer chaincode query -C mychannel -n mycc -c '{"Args":["query","a"]}'
peer chaincode query -C mychannel -n mycc -c '{"Args":["query","b"]}'
```
![query result](https://github.com/skblockedu/edu19/blob/master/images/query1.png)


## chaincode invoke
```
cd ~/aaaaa
./start3_2.sh up -s couchdb
```

```shell
docker exec -it cli /bin/bash
peer chaincode invoke 
     -o orderer.example.com:7050 
     --tls true 
     --cafile /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/ordererOrganizations/example.com/orderers/orderer.example.com/msp/tlscacerts/tlsca.example.com-cert.pem 
     -C mychannel 
     -n mycc 
     --peerAddresses peer0.org1.example.com:7051 
     --tlsRootCertFiles /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org1.example.com/peers/peer0.org1.example.com/tls/ca.crt 
     --peerAddresses peer0.org2.example.com:7051 
     --tlsRootCertFiles /opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org2.example.com/peers/peer0.org2.example.com/tls/ca.crt 
     -c '{"Args":["invoke","a","b","10"]}'
```

## chaincode query
```shell
docker exec -it cli /bin/bash
peer chaincode query -C mychannel -n mycc -c '{"Args":["query","a"]}'
peer chaincode query -C mychannel -n mycc -c '{"Args":["query","b"]}'
```
![query result](https://github.com/skblockedu/edu19/blob/master/images/query2.png)

## chaincode source
- [chaincode_example02.go](https://github.com/skblockedu/edu19/blob/master/src/chaincode_example02.go)

