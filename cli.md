Check downloading header status
-------------------------------
```bash
./sugarchain-cli getblockchaininfo | jq -r '[.headers] | "\(.[0])"'
```

Add some more
