Running a Sugarchain Node on Linux
----------------------------------
`64-bit` version is always recommended for best performance

## Minimum Requirement (Date: 2020-05-26)
```
CPU: 1 core
RAM: 1024 MB
DISK: 5 GB
```

If you have only `1024 MB RAM`, you need at least `3 GB swap`.
- SWAP: https://github.com/sugarchain-project/doc/blob/master/swap.md
- Reduce Memory Usage: https://github.com/bitcoin/bitcoin/blob/master/doc/reduce-memory.md

Optional UTF-8 and Timezone
- https://github.com/sugarchain-project/doc/blob/master/UTF%2Btimezone.md

## Download
- URL: https://github.com/sugarchain-project/sugarchain/releases/latest
```bash
wget https://github.com/sugarchain-project/sugarchain/releases/download/v0.16.3.34-starboy/sugarchain-0.16.3.34-starboy-x86_64-linux-gnu.tar.gz
```

## Verify & Unzip
```
sha256sum sugarchain-0.16.3.34-starboy-x86_64-linux-gnu.tar.gz
# starboy # 4a79d2bb85c306fa37b57ab5790931103e4311b7dc8edeca4c86c3ec26590b62
tar -xvzf sugarchain-0.16.3.34-starboy-x86_64-linux-gnu.tar.gz
```

## Crontab

- Run crontab
```bash
crontab -e
```

- Adding this line:
  * Remove `debug.log` at every reboot, to save disk space.
  * Starting node (daemon) at every reboot.
```bash
# delete logs
@reboot rm $HOME/.sugarchain/debug.log

# run daemon
@reboot $HOME/sugarchain-0.16.3/bin/sugarchaind -server=1 -rpcuser=rpcuser -rpcpassword=rpcpassword -daemon

# reboot every week on Monday(1) 01:01
# Minute | Hour | Day | Month | Day(Week) 
# 1 1 * * MON sudo /sbin/shutdown -r now
```

## Firewall
Open some ports for Sugarchain
  * `22`: SSH connection
  * `80`: Website (optional)
  * `443`: SSL (optional)
  * `34230`: mainnet
  * `44230`: testnet (optional)

```
sudo ufw allow 22 && \
sudo ufw allow 34230 && \
sudo ufw allow 44230 && \
sudo ufw enable && \
sudo ufw status
```

## CLI commands
https://github.com/sugarchain-project/doc/blob/master/cli.md

## Trouble Shooting
- Stuck when restarting, if your RAM is under 1 GB.
  * https://github.com/sugarchain-project/sugarchain/issues/156
  * `init message: Rewinding blocks...`
  * `Using obfuscation key for /root/.sugarchain/blocks/index: 0000000000000000`
  * Due to low memory, it can takes from some hours upto a day. Just wait.
