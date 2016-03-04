
# Disclaimer

**This is a docker compose for a PRIVATE and INSECURE ethereum network - Use it for dev and test purpose only**

This ethereum private network uses a genesis block with really low difficulty, this allow you to mine block in ms, useful for test and dev, but this makes the blockchain insecure.

Eth nodes have all rpc api enabled (included admin, db, ecc...), this allow full access from  an external ethereum console, but it is insecure!

# Introduction

Start here - Great introduction to cryptocurrency, bitcoin and ethereum   https://github.com/ethereum/wiki/wiki/White-Paper

# How to run

## Install docker & docker composer
First install docker and docker composer. Follow the instructions on the official site:
https://docs.docker.com/compose/install/

If you already have Docker engine > 1.7.1, you can skip directly to installing docker composer (currently 1.6.2):
https://github.com/docker/compose/releases/tag/1.6.2

## Build containers

Once docker is installed, you can download and build the docker container.
This repo creates a single docker instance (the other 2 are commented out). The ethereum console host will not be able to connect by default to it
 
folder geth-solidity contains a docker for go ethereum with solidity compiler (solc)

folder geth-compose contains a docker compose for a private network with 3 nodes

```$ cd geth-compose
$ docker-compose build
$ docker-compose up```

The build process may takes some time...

A single docker instance will be started - gethcompose_geth-node-01_1

## Use geth
In order to connect to the geth console, use the script openConsole.sh in the root folder

# Tutorials

Check geth-solidity/console-script for two tutorials: one creates a simple transection between two users, second creates and compiles a smart contract



# Links

* main wiki https://github.com/ethereum/wiki/wiki
* https://github.com/ethereum/go-ethereum/wiki/Connecting-to-the-network
* rpc api docs https://godoc.org/github.com/ethereum/go-ethereum/rpc/api
* example transaction https://ethereum.gitbooks.io/frontier-guide/content/sending_ether.html

# Rpc api

Check if the Geth server is up and running

```curl http://dockerhost:8545  -X POST --data '{"jsonrpc":"2.0","method":"admin_peers","params":[]}'```
