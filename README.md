## Docker Ethereum Embark
Docker Decentralized Applications using Embark and Ethereum

[Further documentation for Embark can be found below](https://github.com/iurimatias/embark-framework)

We keep a Docker image with recent snapshot builds on DockerHub.

### Docker Pull
Run this first:
```
docker pull eliottbacker/docker-ethereum-embark
```
### Docker Run
To start a node that runs the JSON-RPC interface on port 8545, run:
```
docker run  -it -v "`pwd`/dapps:/opt/dapps" --name embark eliottbacker/docker-ethereum-embark bash
```
## Demo
You can easily create a sample working DApp with the following:
```
cd /dapps
embark demo
```
You can run a REAL ethereum node for development purposes:
```
cd embark_demo
embark blockchain
```

if lis accounts is empty, try to add a new account with tyhe followinf command
```
geth --networkid 12301 --password config/development/password account new
```

or, to use an ethereum rpc simulator simply run:
```
embark simulator
```

and leave this running on your terminal.

By default embark blockchain will mine a minimum amount of ether and will only mine when new transactions come in. This is quite usefull to keep a low CPU. The option can be configured at config/blockchain.json

Open a new terminal and deploy the contracts:
```
docker exec -it embark bash
embark run
```

This will automatically deploy the contracts, update their JS bindings and deploy your DApp to a local server at http://localhost:8000

