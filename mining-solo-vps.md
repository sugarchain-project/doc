## VPS solo mining

### 인증
```
ssh-keygen -t rsa -b 4096 -C "cryptozeny@gmail.com" && \
eval "$(ssh-agent -s)" && \
ssh-add ~/.ssh/id_rsa && \
echo "COPY to github ssh" ;\
echo "*******************" ; \
cat ~/.ssh/id_rsa.pub ; \
echo "*******************"
```

### sugar-solo-vps \
```
sudo add-apt-repository ppa:bitcoin/bitcoin -y && \
sudo apt-get update -y && \
sudo apt-get install -y \
software-properties-common libdb4.8-dev libdb4.8++-dev build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils libboost-all-dev libminiupnpc-dev libzmq3-dev libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler libqrencode-dev && \
cd && \
git clone git@github.com:cryptozeny/BitZenyPlus_CZ.git && \
cd BitZenyPlus_CZ/ && \
git checkout fix-name && \
./autogen.sh && \
./configure && \
make -j$(grep -c ^processor /proc/cpuinfo) && \
\
cd && \
sudo apt-get install -y build-essential libssl-dev libcurl4-openssl-dev libjansson-dev libgmp-dev automake zlib1g-dev git && \
git clone https://github.com/bellflower2015/cpuminer-opt.git && \
cd cpuminer-opt && \
./build.sh &&
\
cd && \
rm -rf ~/.sugarchain && \
mkdir ~/.sugarchain && \
touch ~/.sugarchain/sugarchain.conf && \
\
cd && \
echo rpcuser=user >> ~/.sugarchain/sugarchain.conf && \
echo rpcpassword=pass >> ~/.sugarchain/sugarchain.conf && \
echo rpcallowip=127.0.0.1 >> ~/.sugarchain/sugarchain.conf && \
echo server=1 >> ~/.sugarchain/sugarchain.conf && \
\
cd && \
~/BitZenyPlus_CZ/src/sugarchaind -addnode=207.148.106.217 -daemon -rpcport=7978 && \
sleep 1 && \
~/cpuminer-opt/cpuminer -a yespower -o http://localhost:7978 -t$(grep -c ^processor /proc/cpuinfo) -u user -p pass --coinbase-addr=SgEL8X6iREjrES9vn3gYGuoJaeTdHfvLyS
```


### 실행
```
timeout 3600 ~/cpuminer-opt/cpuminer -a yespower -o http://localhost:7978 -t$(grep -c ^processor /proc/cpuinfo) -u user -p pass --coinbase-addr=SgEL8X6iREjrES9vn3gYGuoJaeTdHfvLyS && \
\
sleep 3600 && \
timeout 3600 ~/cpuminer-opt/cpuminer -a yespower -o http://localhost:7978 -t$(grep -c ^processor /proc/cpuinfo) -u user -p pass --coinbase-addr=SgEL8X6iREjrES9vn3gYGuoJaeTdHfvLyS && \
\
```


