# Geth exporter for Prometheus

[![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)

Metrics page example:

```
# HELP geth_version Client version
# TYPE geth_version gauge
geth_version{value="Geth/v1.9.9-stable-01744997/linux-amd64/go1.13.5"} 1

# HELP geth_network Client network
# TYPE geth_network gauge
geth_network{value="mainnet"} 1

# HELP geth_latest Latest block information
# TYPE geth_latest gauge
geth_latest{hash="0x68694093d40cff31e3902b5de0fc32b3484ab40241c7b6c566ea004df3c5cdfd"} 9746115

# HELP bitcoind_blockchain_sync Blockchain sync info
# TYPE bitcoind_blockchain_sync gauge
bitcoind_blockchain_sync{type="current"} 9746115
bitcoind_blockchain_sync{type="highest"} 9746115
bitcoind_blockchain_sync{type="progress"} 1

# HELP geth_gas_price Current gas price in wei
# TYPE geth_gas_price gauge
geth_gas_price 5000000000

# HELP geth_mempool_size Mempool information
# TYPE geth_mempool_size gauge
geth_mempool_size{type="size"} 499

# HELP geth_peers Connected peers
# TYPE geth_peers gauge
geth_peers{version="all"} 45
```

Usage:

```
docker run \
  -p 8000:8000 \
  -e GETH_EXPORTER_LISTEN=0.0.0.0:8000 \
  -e GETH_EXPORTER_NODE=http://geth:8545/ \
  geth-exporter
```

### LICENSE

MIT
