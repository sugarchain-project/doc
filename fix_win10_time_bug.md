# How to fix: Windows 10 Time Bug After Automatic Update

### Symptom
- Your Yumekawa node banned from Sugarchain network
![](https://imgur.com/55KV2lJ.jpg)
![](https://imgur.com/EQzhOh3.jpg)

### What causes this banning?
- Your Windows 10 PC is in wrong internet time
- A bug after Windows 10 automatic update
  * https://www.windowscentral.com/how-manage-time-servers-windows-10

### Yumekawa Network Rule
This is normal behavier and our network rule is much strict than other coins. source: https://sugarchain.org/
* Network rules:
  - To prevent fraud and timestamp attacks, nodes should be within 70 seconds of accurate internet time, or they will be banned.
* Selfish mining & time warp attack:
  - Fraud techniques for manipulating timestamps are already known. We use a future time limit (FTL) to prevent this. Blocks that differ 60 seconds or more from the current head will be banned. (credit: zawy12)

### How to fix?
- Change or Refresh your Time Server
  * ![](https://imgur.com/nlmpKh5.jpg)
- Restart your PC and relaunch your Yumekawa.
