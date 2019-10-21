Running a Sugarchain Node on Linux
----------------------------------
64-bit version is always recommended

## Minimum Requirement
```
CPU: 1 core
RAM: 1024 MB (at least 2048 MB swap)
DISK: 3.65 GB
```
If you have only `1024 MB RAM`, you may need at least `2048 MB swap`.
https://github.com/sugarchain-project/doc/blob/master/swap.md

## Download
```
wget filename.tar.gz
```

## Unzip
```
tar -xvzf filename.tar.gz
```

## Crontab

- Run crontab
```bash
crontabe -e
```

- Adding this line:
  * Remove `debug.log` at every reboot, due to save disk space.
  * Starting node (daemon) at every reboot.
```bash
# delete logs
@reboot rm $HOME/.sugarchain/debug.log

# run daemon
@reboot $HOME/sugarchain-0.16.3/bin/sugarchaind -server=1 -rpcuser=rpcuser -rpcpassword=rpcpassword -daemon
```
