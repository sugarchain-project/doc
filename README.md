# Sugarchain

#### Decentralized cryptocurrency for one-CPU-one-vote

## 스펙
|Sugarchain | SPEC |
|---|---|
|Ticker | SUGAR |
|Consensus Algorithm | Proof-of-Work (YesPoWer 1.0) |
|Difficulty Algorithm | Adjust difficulty every blocks (DarkGravityWave 3.0) |
|Block Time | 18 Seconds |
|Port / RPC | 7979 / 7978 |
|Block Reward | 50 SUGAR |
|Reward Halving | Every 2,500,000 (250만) blocks |
|Max supply | 250,000,000 (2억5천만) SUGAR |
|Premine | 0 % (None) |

웹사이트: https://www.sugarchain.org  
GITHUB: https://github.com/sugarchain  

## 개요

### 1. one-CPU-one-vote
> Proof-of-work is essentially one-CPU-one-vote.  
> 작업증명의 기본은 한 대의 CPU 당 한 번의 투표권을 가지는 것이다.  
> 사토시 나카모토

`Sugarchain`은 한국 최초의 CPU 전용 채굴 가상화폐이며 일반적인 PC 및 스마트폰에서 채굴이 가능하다. 기존의 비트코인 및 이더리움등의 가상화폐는 ASIC이나 GPU와 같은 고가의 전용장비가 없다면 채굴이 불가능하다. 이와같은 전용장비는 대규모 단위의 기업이 아니면 생산과 판매가 불가능하여 BITMAIN 및 NVIDIA와 같은 장비 제조업체가 통화시장을 점령하게 된다. Sugarchain은 이와같은 `독점적 중앙화`에서 벗어나 채굴수단을 CPU 한 개에 한정하여 채굴참여의 진입장벽을 낮추고 누구나 참여가 가능한 탈중앙화된 생태계를 만드는데 목적이 있다.  이것은 사토시 나카모토가 그의 비트코인 백서에서 밝힌 `one-CPU-one-vote`의 의도에 근접하려는 시도이다.

### 2. CPU 전용 작업증명 알고리즘

Sugarchain은 ASIC 및 GPU 저항을 위해 `YesPoWer 1.0` 알고리즘을 사용한다. YesPoWer는 GPU 저항이 극대화된 YesCrypt의 개선판이며 `Alexander Peslyak`에 의해 2018년 7월에 발표되었다. 4년 전에 발표된 그의 전작인 YesCrypt는 ASIC 저항을 위해 개발되었으며 그것의 GPU 저항은 나쁘지 않았다. 하지만 인공지능 분야의 급격한 성장탓에 GPU 성능도 기하급수적으로 증가했기에 이에 맞서 GPU 저항을 강화하였다. YesPoWer에서는 현존하는 어떤 최상급의 GPU를 사용해도 채굴이 불가능하며 향후 5년간의 GPU 업계의 성능향상을 감안해도 탁월한 저항성능을 지닌것으로 평가된다.

### 3. 비트코인 기반

Sugarchain은 비트코인을 기반으로 개발되었기에 동일한 보안성을 제공한다. v0.15.1 버젼을 기초로 `SegWit Activation`을 기본탑재 하였다. 향후 주요 로드맵은 세컨드 레이어 솔루션인 `Lightning Network` 및 다중서명일원화 솔루션인 `Schnorr Signature`를 2019-Q3/4에 출시를 목표로 한다. 그 외에 CVE-2018-17144 버그를 수정하였다. 기술적인 로드맵은 비트코인을 그대로 답습하여 최상의 보안을 제공한다.

## 로드맵

2019.Q1
 * 클라이언트: 비트코인 v0.15 기반
 * 마이닝앱: cpuminer-opt (데스크탑)
 * 마이닝풀: NOMP
 * 블록탐색기: Insight v0.2

2019.Q2
 * 클라이언트: 비트코인 v0.17 기반으로 업그레이드
 * 마이닝앱: 스마트폰 마이닝앱 (안드로이드)
 * 마이닝풀: YIIMP
 * 블록탐색기: Insight v0.4

2019.Q3
 * Lightning Network
 * 로고 공모전 개최
 * 트위터 팁봇

2019.Q4
 * Schnorr Signature
 * 캐릭터 공모전 개최
 * 커뮤니티 개설

2020.Q1
 * Cryptopia 상장
 * Tradesatoshi 상장
 * CryptoBridge 상장
 * Bisq 상장
 * Crex24 상장




















