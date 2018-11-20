### caution
solo mining is available after 17 blocks (BIP32 height): 
https://github.com/Crypto-Expert/stratum-mining/issues/349#issuecomment-47847231


### wallet
```bash
./src/qt/sugarchain-qt -datadir=/home/ak/.sugarchain-test-15 -printtoconsole -addnode=192.168.1.111 -server=1 -rpcuser=username -rpcpassword=password
```

### cpuminer
```bash
git clone https://github.com/bellflower2015/cpuminer-opt.git && \
cd cpuminer-opt && \
build.sh && \
./cpuminer -a yespower -o http://localhost:7978 -t1 -u username -p password --coinbase-addr=sMXEKcUKNvtRNcj2B63HftwtJbmuPd9ty5 -q -t1
```
