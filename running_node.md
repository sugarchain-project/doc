Running a Sugarchain Node on Linux
----------------------------------
64-bit version is always recommended

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
