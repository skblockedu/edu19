# 2.2. Container 구동
```
./start2_2.sh up -s couchdb
docker-compose -f docker-compose-cli.yaml -f docker-compose-couch.yaml up -d
```

## check docker image/container/network
```
docker image ls      # orderer, peer, couchdb, tools(CLI)
docker container ls  # 1 orderer, 4 peers, 4 couchdb, 1 cli
docker network ls    # new network (net_byfn)
```

## check couchdb database
```
http://localhost:5984/_utils   # couchdb0
http://localhost:6984/_utils   # couchdb1
http://localhost:7984/_utils   # couchdb2
http://localhost:8984/_utils   # couchdb3
```
