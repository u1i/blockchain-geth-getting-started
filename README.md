# Getting Started with Blockchain - Ethereum

Tools and platforms are constantly evolving and documentation is easily outdated. This is how you get started with Ethereum / geth on Ubuntu as of January 2018.

## Install geth command line client on Ubuntu

`sudo apt-get install software-properties-common`

`sudo add-apt-repository -y ppa:ethereum/ethereum`

`sudo apt-get update`

`sudo apt-get install ethereum
`
## Connect to Rinkeby test network

### This will sync the chain - and take some time

`geth --rinkeby`

### Open Console in a separate (screen) window and keep the other command running

`geth --datadir=$HOME/.ethereum/rinkeby   attach ipc:$HOME/.ethereum/rinkeby/geth.ipc console`

Once the console is open, you should have meaningful output from these commands to find out if the syncing is running and/or completed yet:

`net.listening`

`net.peerCount`

`eth.syncing`

## You need an Account - let's create one

`geth --datadir=$HOME/.ethereum/rinkeby account new`

then in console type: `eth.accounts` - take note of your account identifier

alternatively create the account in the console:

`personal.newAccount("somepassword")`

## Ask for 'Free' Money

https://www.rinkeby.io/#faucet - takes seconds only!

## Check Balance

`eth.coinbase`

`eth.getBalance(eth.coinbase)`


## Look up transactions for account (this is my test account)

https://rinkeby.etherscan.io/address/0xecd2e6a46e3ddd19674581c0464df335fe474c3e

## Transfer ETH

create a second account first

`from = eth.accounts[0];`

`to   = eth.accounts[1];`

`amount = 1 `

`personal.unlockAccount(from, "mypassword", 300)`

`eth.sendTransaction({from: from, to: to, value: amount})`


![](https://raw.githubusercontent.com/u1i/blockchain-geth-getting-started/master/screen.png)

![](https://raw.githubusercontent.com/u1i/blockchain-geth-getting-started/master/funded.png)

What's next? Storing data - or 'contracts'. [This is where it gets tricky](https://medium.com/@ConsenSys/a-101-noob-intro-to-programming-smart-contracts-on-ethereum-695d15c1dab4).

--
Thanks to [cryptogoth](https://gist.github.com/cryptogoth/10a98e8078cfd69f7ca892ddbdcf26bc)