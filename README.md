# Geth exporter for Prometheus

[![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)

Metrics page example:

```
# HELP geth_version Client version
# TYPE geth_version gauge
geth_version{value="Geth//v1.11.7-stable-085035f-20180717/x86_64-linux-gnu/rustc1.27.1"} 1

# HELP geth_chain Client chain
# TYPE geth_chain gauge
geth_chain{value="ethereum classic"} 1

# HELP geth_latest Latest block information
# TYPE geth_latest gauge
geth_latest{hash="0xeb9f857555053d93e661e2d9324dcb729c30707e6cbba945fc19f89f4bd73ebc"} 6347076

# HELP bitcoind_blockchain_sync Blockchain sync info
# TYPE bitcoind_blockchain_sync gauge
bitcoind_blockchain_sync{type="current"} 6347076
bitcoind_blockchain_sync{type="highest"} 6362392
bitcoind_blockchain_sync{type="progress"} 0.99759

# HELP geth_gas_price Current gas price in wei
# TYPE geth_gas_price gauge
geth_gas_price 20000000000

# HELP geth_mempool_size Mempool information
# TYPE geth_mempool_size gauge
geth_mempool_size{type="size"} 0
geth_mempool_size{type="bytes"} 0

# HELP geth_peers Connected peers
# TYPE geth_peers gauge
geth_peers{version="all"} 4
```

Usage:

```
docker run \
  -p 8000:8000 \
  -e GETH_EXPORTER_LISTEN=0.0.0.0:8000 \
  -e GETH_EXPORTER_NODE=http://geth:8545/ \
  quay.io/exodusmovement/geth-exporter
```

### LICENSE

MIT
