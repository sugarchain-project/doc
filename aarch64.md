# AARCH64
Raspberry Pi or Smartphone based on aarch64, seems working, but too slow yet.

You need some tweaks:

- SWAP: 
  * Make 3 or 4 GB: https://github.com/sugarchain-project/doc/blob/master/swap.md

- lowmemorykiller
  * `echo '9999' > /sys/module/lowmemorykiller/parameters/adj`
  * `echo '1' > /sys/module/lowmemorykiller/parameters/minfree`
  * Ref: https://github.com/datajerk/arm-bitcoin-fullnode-container
  
