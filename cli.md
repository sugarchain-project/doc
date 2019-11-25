CLI COMMANDS
------------

## Check downloading header status (watch -n5)
```
watch -n 5 '~/sugarchain-0.16.3/bin/sugarchain-cli -rpcuser=rpcuser -rpcpassword=rpcpassword getblockchaininfo | grep headers'
```

## Get block count
```
~/sugarchain-0.16.3/bin/sugarchain-cli -rpcuser=rpcuser -rpcpassword=rpcpassword getblockcount
```

## Get connection count
```
~/sugarchain-0.16.3/bin/sugarchain-cli -rpcuser=rpcuser -rpcpassword=rpcpassword getconnectioncount
```
