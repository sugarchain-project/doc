SYNC TIME
---------
at block height around `1,000,000` (2019-10-22)

- 8cpu65536ram [Ryzen1700](https://en.wikichip.org/wiki/amd/ryzen_7/1700)
  * Linux64: download 2h / sync 3h / `total 5h`
    - `-reindex-chainstate`: 3h
    - `-reindex`: 6h 20m 
  * Linux32: ? / ? / ?
  * Bootstrap: verify 3:30 / sync 4:00 / `total 7:30` (bootstrap is slower than normal)

- 1cpu1024ram VPS (+2gb swap)
  * Linux64: download 3h / sync 4h / `total 7h`
  * Linux32: ? / ? / ?

- 2cpu4096ram [Celeron G3930](https://en.wikichip.org/wiki/intel/celeron/g3930)
  * Win64: download 2h / sync 5h / `total 7h`
  * Win32: ? / ? / `total 25h`

- 2cpu4096ram [MacbookAir 13inch late 2010](https://support.apple.com/kb/sp618)
  * OSX(High Siera): download 5h / sync 7h / `total 12h`
  
- ARM64 ***(too slow)***
  * aarch64: ? / ? / `total 80h (4d)`
- ARM32 ***(not acceptable)***
  * armv7l: ? / ? / `total 160h (a week)`
