# Private-Chain-Scaffold

A Private Chain Scaffold - mainly will be used for testing and attacking Smart Contracts

### Prerequisites

Install Geth via instructions on website

```
https://www.ethereum.org/cli
```

Install Truffle via npm

```
npm i -g truffle
```

## Setup

(Guide to starting from scratch, if you git pull this project, this will be setup)

Initialze the Project with Truffle

```
truffle init
```

Create the data directory folder to hold the Private Chain Data

```
mkdir data
cd data
```

Create the Genesis Block using a JSON file

Run the first command and then copy the code below
```
cat > genesis.json
```

```
{
    "config": {
        "chainId": 100,
        "homesteadBlock": 0,
        "eip155Block": 0,
        "eip158Block": 0
    },
    "difficulty": "0x0400",
    "gasLimit": "0x8000000",
    "alloc": {
         "<enter new account address here>": {
		"balance": "30000000000000000000000000"
	}
     }
}
```


Initialize the Genesis Block via the geth cli

Run the first command and then paste the code below
```
cat > init-genesis.sh
```

```
#!/bin/bash
geth -datadir="./data" init-genesis.json
```

Make the script executable
```
chmod +x init-genesis.sh
```
