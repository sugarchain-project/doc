Running a Sugarchain Node on Linux
----------------------------------
`64-bit` version is always recommended for best performance

## Minimum Requirement
```
CPU: 1 core
RAM: 1024 MB (at least 2048 MB swap)
DISK: 3.65 GB
```

If you have only `1024 MB RAM`, you may need at least `3 GB swap`.
- SWAP: https://github.com/sugarchain-project/doc/blob/master/swap.md

Optional UTF-8 and Timezone
- https://github.com/sugarchain-project/doc/blob/master/UTF%2Btimezone.md

## Download
- URL: https://github.com/sugarchain-project/sugarchain/releases/latest
- filename: `sugarchain-0.16.3.x-x86_64-linux-gnu.tar.gz`

```
wget https://github.com/sugarchain-project/sugarchain/releases/download/v0.16.3.30-moonlight/sugarchain-0.16.3.30-moonlight-x86_64-linux-gnu.tar.gz
```

## Verify & Unzip
```
sha256sum sugarchain-0.16.3.30-moonlight-x86_64-linux-gnu.tar.gz # check if hash match # 20ca6c6e5fd395cd3ff0cc41601eaa156ee43ae92e44cc0b6eaea8b3cbf09b06
tar -xvzf sugarchain-0.16.3.30-moonlight-x86_64-linux-gnu.tar.gz
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
