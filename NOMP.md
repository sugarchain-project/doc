Building Mining Pool for Sugarchain
===================================
Since we are the first [BECH32](https://en.bitcoin.it/wiki/BIP_0173) user, so your issue is only about this address. Currently there is no pre-made pool software for this. You have to make your own.

Requirement
-----------
- Minimum: 1 CPU / 1 GB RAM / 3 GB HDD (at least 2 GB [swap](https://github.com/sugarchain-project/doc/blob/master/swap.md))
- 10+ Miners: 2 CPU / 4 GB RAM / 8 GB HDD
- 100+ Miners: 4 CPU / 8 GB RAM / 32 GB SSD

Swap
----
you need at least `2 GB` swap or 2x of your RAM size.

```bash
sudo fallocate -l 2G /swapfile && \
sudo chmod 600 /swapfile && \
ls -lh /swapfile | grep -e "-rw-------" && \
sudo mkswap /swapfile && \
sudo swapon /swapfile && \
sudo swapon --show && \
sudo cp /etc/fstab /etc/fstab.bak && \
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
```

NOMP
----
Check #dev branch  
https://github.com/zone117x/node-open-mining-portal/tree/2f3a1bc63edb0fe52441d513b973663058421fa1

YespowerSugar
-------------
https://github.com/sugarchain-project/sugarchain/blob/7c48b42b8f0bfd6c5dd333b75c039ddf15591bf2/src/primitives/block.cpp#L30-L36

- Yespower 1.0.1  
https://github.com/sugarchain-project/yespower

- `yespower_sugarchain.c`
```cpp
#include "yespower-1.0.1/yespower.h"

void yespower_hash(const char *input, char *output, uint32_t len) {
    static const yespower_params_t params = {
        .version = YESPOWER_1_0,
        .N = 2048,
        .r = 32,
        .pers = "Satoshi Nakamoto 31/Oct/2008 Proof-of-work is essentially one-CPU-one-vote",
        .perslen = 74
    };
    yespower_tls( (yespower_binary_t*)input, len, &params, (yespower_binary_t*)output );
}
```

- Coin settings  
https://github.com/sugarchain-project/doc/blob/master/sugarchain.json
```json
{
    "name": "sugarchain",
    "symbol": "SUGAR",
    "algorithm": "YespowerSugar",
    "peerMagic": "9feb4b9d",
    "peerMagicTestnet": "b0119070",

    "mainnet": {
      "bech32": "sugar",
      "bip32": {
        "public": "0488b21e"
      },
      "pubKeyHash": "3f",
      "scriptHash": "7d"
    },

    "testnet": {
      "bech32": "tugar",
      "bip32": {
        "public": "043587cf"
      },
      "pubKeyHash": "42",
      "scriptHash": "80"
    }
}
```

- Stratum
```js
YespowerSugar: {
        multiplier: Math.pow(2, 16),
        hash: function(coinConfig){
            var nValue = coinConfig.nValue || 2048;
            var rValue = coinConfig.rValue || 32;
            return function(data){
                return multiHashing.yespower(data,nValue,rValue);
            }
        }

case 'YespowerSugar':
            return function (d) {
                return util.reverseBuffer(util.sha256d(d));
                };
```

- Bech32 Patch for Website (Credit @okoto-xyz)  
Remove these lines on `libs/website.js`
```diff
- buildKeyScriptPage();

- app.get('/key.html', function(req, res, next){
-   res.end(keyScriptProcessed);
- });
```

If you have an additional question, contact [cryptozeny](https://keybase.io/cryptozeny) on [Discord](https://discord.gg/D6NJn5t) or [Telegram](https://t.me/sugarchain).
