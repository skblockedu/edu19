#####################################################
# 0.1. SSH 연결
ssh edu@127.0.0.1 -p 2222   # using PuTTY, pwd=skcc
 
# 0.2. 설치 프로그램 확인
~/checkVer.sh

# 0.3 nano 실습
nano checkVer.sh   # 종료: Ctrl+X


#####################################################
# 1.1. 작업 폴더(FIRST BLOCKCHAIN NETWORK)로 이동
cd ~/fabric-samples/first-network

# 1.2. 설정파일 확인
nano configtx.yaml   # Organization, Orderer, Channel, Profile (TwoOrgsOrdererGenesis, TwoOrgsChannel)

# 1.3. check docker image/container/network
docker image ls      # orderer, peer, couchdb, tools(CLI)
docker container ls  # nothing (not yet)
docker network ls    # default network (bridge, host, null)


#####################################################
# 2.1. cryto. 파일 생성, genesis.block, channel.tx 파일 생성
./start2_1.sh generate

tree -L 2 crypto-config     # orderer, org1, org2 구조 확인
tree crypto-config/peerOrganizations/org1.example.com/peers  # org1내 peer별 cert., keystore, tls 생성 확인

ls channel-artifacts       # genesis.block, channel.tx, *MSPAnchor.tx 생성 확인


#####################################################
# 2.2. start docker container (orderer, peer, couchdb and so on)
./start2_2.sh up -s couchdb

# check docker image/container/network
docker image ls      # orderer, peer, couchdb, tools(CLI)
docker container ls  # 1 orderer, 4 peers, 4 couchdb, 1 cli
docker network ls    # new network (net_byfn)

# view couchdb database
http://localhost:5984/_utils   # couchdb0
http://localhost:6984/_utils   # couchdb1
http://localhost:7984/_utils   # couchdb2
http://localhost:8984/_utils   # couchdb3

#####################################################
# 2.3. 'mychannel' 생성, peer별 'mychannel' 조인, Anchor peer 업데이트
./start2_3.sh up -s couchdb

# check channel
docker exec -it cli bash
env | grep CORE
CORE_PEER_TLS_ROOTCERT_FILE=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org1.example.com/peers/peer0.org1.example.com/tls/ca.crt
CORE_PEER_TLS_KEY_FILE=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org1.example.com/peers/peer0.org1.example.com/tls/server.key
#CORE_PEER_LOCALMSPID=Org1MSP
#CORE_VM_ENDPOINT=unix:///host/var/run/docker.sock
#CORE_PEER_TLS_CERT_FILE=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org1.example.com/peers/peer0.org1.example.com/tls/server.crt
#CORE_PEER_TLS_ENABLED=true
#CORE_PEER_MSPCONFIGPATH=/opt/gopath/src/github.com/hyperledger/fabric/peer/crypto/peerOrganizations/org1.example.com/users/Admin@org1.example.com/msp
#CORE_PEER_ID=cli
#CORE_PEER_ADDRESS=peer0.org1.example.com:7051

# channel view
peer channel list      # Channels peers has joined: mychannel

# chaincode view
peer chaincode list
peer chaincode --installed


#####################################################
# 3.1. chaincode install & instantiate
./start3_1.sh up -s couchdb

# check container
docker ps -a

# view couchdb database 
http://localhost:5984/_utils   # couchdb0, new database ( mychannel_, mychannel_lscc, mychannel_mycc )
                               # view 
http://localhost:6984/_utils   # couchdb1
http://localhost:7984/_utils   # couchdb2
http://localhost:8984/_utils   # couchdb3

# view ledger file
- ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) `#f03c15`






#####################################################
# 3.2. 
./start3_2.sh up -s couchdb



#####################################################
# 추가로 할일 
# 1. tree 설치
sudo apt install tree 

# 2. checkVer.sh 설치
# edu home 폴더에 설치할 것 
