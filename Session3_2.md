# 3.2. Chaincode query & invoke
```
cd ~/fabric-samples/first-network/
./start3_2.sh up -s couchdb
```

## chaincode query
```
docker exec -it cli /bin/bash
peer chaincode query -C $CHANNEL_NAME -n mycc -c '{"Args":["query","a"]}'
peer chaincode query -C $CHANNEL_NAME -n mycc -c '{"Args":["query","b"]}'
```
![query result](https://github.com/skblockedu/edu19/blob/master/images/query1.png)


## chaincode invoke


