# Mining on Apple Mac (OSX) using Sugarmaker

### Download
https://github.com/decryp2kanon/sugarmaker/releases/download/v2.5.0-sugar4/sugarmaker-v2.5.0-sugar4-osx.zip

### Unzip
```bash
unzip sugarmaker-v2.5.0-sugar4-osx.zip
```

### Move to sugarmaker
```bash
cd sugarmaker-v2.5.0-sugar4-osx
```

### Run
```bash
./sugarmaker -a YespowerSugar -o stratum+tcp://1pool.sugarchain.org:3333 -u sugar1q49dwwrwxle07wzvs84qe77m6wwfmtkn07ycmcm -t1
```

- `stratum+tcp://1pool.sugarchain.org:3333` is stratum address of pool

- `sugar1q49dwwrwxle07wzvs84qe77m6wwfmtkn07ycmcm` is your sugarchain address

- `-t1` is using how many threads. Recommendation is `(T/2)+1`. If you have 16 threads, use `-t9`
