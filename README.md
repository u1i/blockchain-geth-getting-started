# blockchain-geth-getting-started

## Install on Ubuntu

sudo apt-get install software-properties-common

sudo add-apt-repository -y ppa:ethereum/ethereum

sudo apt-get update

sudo apt-get install ethereum

## Connect to test network

### Sync the chain

geth --rinkeby

### Open Console (while the other thing is running)

geth --datadir=$HOME/.ethereum/rinkeby   attach ipc:$HOME/.ethereum/rinkeby/geth.ipc console

## Test Connectivity and sync status on the console

net.listening

net.peerCount

eth.syncing

