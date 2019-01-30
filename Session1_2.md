# 1.2. EDU VM(Virtual Machine) 둘러보기

## 설치 SW
- Ubuntu: Linux OS
- Docker & Docker-compose: Container Platform & Tool
- Git: Version control client & server
- Node.js: Javascript-based development language or platform 
- NPM(Node Package Manager)
- Golang: 2009년 구글에서 개발한 프로그래밍 언어
- Hypserleder Fabric 1.4.0 images
```shell
docker image ls
```
![docker image ls](https://github.com/skblockedu/edu19/blob/master/images/Session2_1.png)

```shell
docker network ls
```
![docker netowork ls](https://github.com/skblockedu/edu19/blob/master/images/Session2_2.png)


- Couchdb: Document-based NoSQL database (hyperledger fabric의 state database)
- nano: Simple Text Editor

## nano 실습
```shell
nano ~/fabric-samples/first-network/configtx.yaml
```
- 종료: Ctrl + X
- Line 이동: Ctrl + _  (underbar)

## 실습용 Hyperledgr Fabric Network
![network1](https://github.com/skblockedu/edu19/blob/master/images/network1.png)

[Session1_3 이동 >>](https://github.com/skblockedu/edu19/blob/master/Session1_3.md)
