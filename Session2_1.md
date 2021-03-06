# 2.1. cryto. & configuration 파일 생성

```shell
cd ~/fabric-samples/first-network
./start2_1.sh generate
```

## Cryto. 파일 확인
[crytogen generate crytogen.yaml]
```shell
tree -L 2 crypto-config     # orderer, org1, org2 구조 확인
```
![image1](https://github.com/skblockedu/edu19/blob/master/images/cryptoconfig1.png)

```shell
tree crypto-config/peerOrganizations/org1.example.com/peers  # org1내 peer별 cert., keystore, tls 생성 확인
```
![image1](https://github.com/skblockedu/edu19/blob/master/images/cryptoconfig2.png)


## Configuation 파일 확인
[configen generate crytogen.yaml]
```shell
ls channel-artifacts       # genesis.block, channel.tx, *MSPAnchor.tx 생성 확인
```
- genesis.block: Orderer, Org, Policy 정보
- channel.tx: TwoOrgChannel (Org1 & Org2)
- Org1MSPAnhcor.tx Org2MSPAnchor.tx
![network2](https://github.com/skblockedu/edu19/blob/master/images/network2.png)

["2.2. Container 구동" >>](https://github.com/skblockedu/edu19/blob/master/Session2_2.md)
