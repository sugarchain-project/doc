Check downloading header status
-------------------------------

## Update every 5 seconds
```bash
watch -n 5 'some command | grep whatyouwant'
```

## Headers count (watch -n5)
```
watch -n 5 './sugarchain-0.16.3/bin/sugarchain-cli -rpcuser=rpcuser -rpcpassword=rpcpassword getblockchaininfo | grep headers'
```

## Get block count
```
./sugarchain-0.16.3/bin/sugarchain-cli -rpcuser=rpcuser -rpcpassword=rpcpassword getblockcount
```

## Get connection count
```
./sugarchain-0.16.3/bin/sugarchain-cli -rpcuser=rpcuser -rpcpassword=rpcpassword getconnectioncount
```
