Running a Sugarchain Node on Linux
----------------------------------
`64-bit` version is always recommended for best performance

## Minimum Requirement
```
CPU: 1 core
RAM: 1024 MB (at least 2048 MB swap)
DISK: 3.65 GB
```
If you have only `1024 MB RAM`, you may need at least `2048 MB swap`.
- SWAP: https://github.com/sugarchain-project/doc/blob/master/swap.md

## Download
- URL: https://github.com/sugarchain-project/sugarchain/releases/latest
- filename: `sugarchain-0.16.3.x-x86_64-linux-gnu.tar.gz`

```
wget filename
```

## Verify & Unzip
```
sha256sum filename # check if hash match
tar -xvzf filename
```

## Crontab

- Run crontab
```bash
crontabe -e
```

- Adding this line:
  * Remove `debug.log` at every reboot, to save disk space.
  * Starting node (daemon) at every reboot.
```bash
# delete logs
@reboot rm $HOME/.sugarchain/debug.log

# run daemon
@reboot $HOME/sugarchain-0.16.3/bin/sugarchaind -server=1 -rpcuser=rpcuser -rpcpassword=rpcpassword -daemon
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
sudo ufw allow 80 && \
sudo ufw allow 443 && \
sudo ufw allow 34230 && \
sudo ufw allow 44230 && \
sudo ufw enable && \
sudo ufw status
```

## CLI commands
https://github.com/sugarchain-project/doc/blob/master/cli.md
