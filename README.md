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

## Create Account

geth --datadir=$HOME/.ethereum/rinkeby account new

then in console: eth.accounts

alternatively:

personal.newAccount("somepassword")

## Check Balance
eth.coinbase

eth.getBalance(eth.coinbase)





![](https://raw.githubusercontent.com/u1i/blockchain-geth-getting-started/master/screen.png)