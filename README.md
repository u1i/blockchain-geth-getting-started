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

## Ask for Money

https://www.rinkeby.io/#faucet

## Check Balance
eth.coinbase

eth.getBalance(eth.coinbase)


## Look up transactions for account

https://rinkeby.etherscan.io/address/0xecd2e6a46e3ddd19674581c0464df335fe474c3e

## Transfer ETH


from = eth.accounts[0];

to   = eth.accounts[1];

amount = 1 

personal.unlockAccount(from, "mypassword", 300)

eth.sendTransaction({from: from, to: to, value: amount})


![](https://raw.githubusercontent.com/u1i/blockchain-geth-getting-started/master/screen.png)

![](https://raw.githubusercontent.com/u1i/blockchain-geth-getting-started/master/funded.png)



https://gist.github.com/cryptogoth/10a98e8078cfd69f7ca892ddbdcf26bc