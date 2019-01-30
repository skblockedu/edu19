# 2.1. cryto. & configuration 파일 생성

```
cd ~/fabric-samples/first-network
./start2_1.sh generate
```

## Cryto. 파일 확인
```
tree -L 2 crypto-config     # orderer, org1, org2 구조 확인
tree crypto-config/peerOrganizations/org1.example.com/peers  # org1내 peer별 cert., keystore, tls 생성 확인
```

## Configuation 파일 확인
```
ls channel-artifacts       # genesis.block, channel.tx, *MSPAnchor.tx 생성 확인
```
- genesis.block
- channel.tx
- Org1MSPAnhcor.tx Org2MSPAnchor.tx
