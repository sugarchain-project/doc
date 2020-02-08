# Build an API-server for TESTNET

### Yumekawa (testnet)
https://github.com/sugarchain-project/sugarchain

##### Depends on Bitcoin Core
Exactly the same as dependencies of Bitcoin Core v0.16.3.

```bash
sudo add-apt-repository -y ppa:bitcoin/bitcoin && \
sudo apt-get update && \
sudo apt-get install -y \
software-properties-common libdb4.8-dev libdb4.8++-dev \
build-essential libtool autotools-dev automake pkg-config \
libssl-dev libevent-dev bsdmainutils libboost-all-dev \
libminiupnpc-dev libzmq3-dev libqt5gui5 libqt5core5a \
libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev \
protobuf-compiler libqrencode-dev help2man
```

##### Build from source (testnet)
```bash
git clone --single-branch --branch API-addressindex https://github.com/sugarchain-project/sugarchain.git && \
cd sugarchain && \
./autogen.sh && \
./configure && \
make -j$(nproc) && \
make check -j$(nproc)
```

##### Running node (testnet)
Run with `-testnet` flag
https://github.com/sugarchain-project/doc/blob/master/running_node.md

### API-server
https://github.com/sugarchain-project/api-server.git

##### Build API-server
```bash
git clone https://github.com/sugarchain-project/api-server.git && \
cd api-server && \
sudo apt-get install python3-pip && \
pip3 install -r requirements.txt
```

##### Create `config.py` file in root directory
(testnet)
```py
rid = 'api-server'
cache = 3600  # Cache request for 1 hour
secret = 'YOU SHOULD HAVE A VERY STRONG PASSWORD HERE'
endpoint = 'http://rpcuser:rpcpassword@127.0.0.1:44229/' # RPC 34229 or 44229
host = '0.0.0.0'
port = 1234
debug = True
```

##### Run
```bash
$ python3 app.py
```

### SSL Certbot

##### Firewall
`34230` for mainnet, `44230` for testnet
```bash
sudo ufw allow 22 && \
sudo ufw allow 80 && \
sudo ufw allow 443 && \
sudo ufw allow 34230 && \
sudo ufw allow 44230 && \
sudo ufw enable && \
sudo ufw status
```

##### NGINX (testnet)
Install
```bash
URL="api-testnet.sugarchain.org" && \
sudo apt-get install -y nginx && \
sudo rm /etc/nginx/sites-enabled/default && \
sudo nano /etc/nginx/sites-available/$URL
```

Paste it into file `api-testnet.sugarchain.org`
```json
server {
    listen 80;
    server_name api-testnet.sugarchain.org;

    location / {
        proxy_set_header   X-Forwarded-For $remote_addr;
        proxy_set_header   Host $http_host;
        proxy_pass         "http://127.0.0.1:8080";
    }
}
```

Restart NGINX
```bash
URL="api-testnet.sugarchain.org" && \
sudo ln -s \
/etc/nginx/sites-available/$URL \
/etc/nginx/sites-enabled/$URL && \
sudo service nginx restart
```

##### Add `A` record on your DNS

##### Certbot
Certbot installing
```bash
sudo apt-get update && \
sudo apt-get install -y software-properties-common && \
sudo add-apt-repository -y universe && \
sudo add-apt-repository -y ppa:certbot/certbot && \
sudo apt-get update && \
sudo apt-get install -y certbot python-certbot-nginx
```

Cerbot run
`sudo certbot --nginx`

Certbot test
`sudo certbot renew --dry-run`

Certbot cron
`crontab -e`

Add following for automatic SSL update every week
```bash
# SSL renew by certbot (every Wed at 08:16 AM)
16 8 * * 4 sudo certbot renew --force-renewal >> $HOME/certbot.log 2>&1
```

##### Cronjob result (testnet)
Make logfile
```bash
touch $HOME/certbot.log && \
touch $HOME/api-server.log
```

Cronjob (total)
```bash
# delete logs
@reboot rm $HOME/.sugarchain/testnet5/debug.log
@reboot rm $HOME/certbot.log
@reboot rm $HOME/api-server.log

# SSL renew by certbot (every Wed at 08:16 AM)
16 8 * * 4 sudo certbot renew --force-renewal >> $HOME/certbot.log 2>&1

# run daemon
@reboot $HOME/sugarchain/src/sugarchaind -server=1 -rpcuser=rpcuser -rpcpassword=rpcpassword -testnet -txindex=1 -addressindex=1 -daemon

# run api-server
@reboot /usr/bin/python3 $HOME/api-server/app.py >> $HOME/api-server.log 2>&1
```
