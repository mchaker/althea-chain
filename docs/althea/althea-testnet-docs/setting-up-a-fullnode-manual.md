# How to run a Althea testnet full node

A Althea chain full node is just like any other Cosmos chain full node and unlike the validator flow requires no external software

## What do I need?

A Linux server with any modern Linux distribution, 2gb of ram and at least 20gb storage. Requirements are very minimal.

### Download Althea chain software

```
# the althea chain binary itself
wget https://github.com/althea-net/althea-chain/releases/download/v0.2.2/althea-0.0.5-26-gcf92625-linux-amd64
mv althea-0.0.5-26-gcf92625-linux-amd64 althea

chmod +x althea
sudo mv althea /usr/bin/
```

### Init the config files

```
cd $HOME
althea init mymoniker --chain-id althea-testnet2v2
```

### Copy the genesis file

```
wget https://github.com/althea-net/althea-chain/releases/download/v0.2.2/althea-testnet2v2-genesis.json
cp althea-testnet2v2-genesis.json $HOME/.althea/config/genesis.json
```

### Add seed node

Change the seed field in ~/.althea/config/config.toml to contain the following:

```

seeds = "6a9cd8d87ab9e49d7af91e09026cb3f40dec2f85@testnet2.althea.net:26656"

```

### Start your full node and wait for it to sync

Ask what the current blockheight is in the chat

```
althea start
```
