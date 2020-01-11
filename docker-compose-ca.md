```yaml
version: "2"

services:
  ca0:
    image: hyperledger/fabric-ca:1.4.4
    environment:
      - FABRIC_CA_HOME=/etc/hyperledger/fabric-ca-server
      - FABRIC_CA_SERVER_CA_NAME=ca-org1
      - FABRIC_CA_SERVER_TLS_ENABLED=true
      - FABRIC_CA_SERVER_PORT=7054
    ports:
      - "7054:7054"
    command: sh -c 'fabric-ca-server start -b admin:adminpw -d'
    volumes:
      - ./organizations/fabric-ca/org1:/etc/hyperledger/fabric-ca-server
    container_name: ca_org1
```
