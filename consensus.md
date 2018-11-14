# 규칙변경합의규정
consensus.nRuleChangeActivationThreshold
https://github.com/bitcoin/bitcoin/blob/74213fa4d13e53c3811d69a516fc865b79fdd0c7/src/chainparams.cpp#L77

### 비트코인
 * 비트코인은 `2016블록(2주)`마다 난이도 재조정을 한다. 
 * 규칙변경은 `2주 이내`에 `95% 이상` 합의요망.
```cpp
consensus.nPowTargetTimespan = 14 * 24 * 60 * 60; 	// 1209600초 (2주)
consensus.nPowTargetSpacing = 10 * 60;			// 600초 (10분)
consensus.nRuleChangeActivationThreshold = 1916; 	// 1916블록 (319.2시간) (95% of 2016블록)
consensus.nMinerConfirmationWindow = 2016; 		// 2016블록 (336시간) (2주) (1209600 / 600 = 2016)
```

### 라이트코인
 * 비트코인보다 블록타임이 `4배` 빠르다. (2.5분)
 * 난이도 재조정 기간은 `2주`로 비트코인과 같다. 
 * 규칙변경은 `2주 이내`에 `75% 이상` 합의요망.
```cpp
consensus.nPowTargetTimespan = 3.5 * 24 * 60 * 60; 	// 302400초 (3.5날)
consensus.nPowTargetSpacing = 2.5 * 60;			// 150초 (2.5분)
consensus.nRuleChangeActivationThreshold = 6048; 	// 6048블록 (252시간) (75% of 8064블록)
consensus.nMinerConfirmationWindow = 8064; 		// 8064블록 (336시간) (2주) (302400 / 150 * 4 = 8064)
```

### 모나코인 (Digishield: 매블록당 난이도조절)
 * 난이도조절은 매블록당. 
 * 규칙변경은 `252시간(10.5날)`이내에 `75% 이상` 합의요망.
```cpp
consensus.nPowTargetTimespan = 1.1 * 24 * 60 * 60; 	// 95040초 (1.1날)
consensus.nPowTargetSpacing = 1.5 * 60; 		// 90초 (1.5분)
consensus.nPowTargetTimespanDigisheld = 1.5 * 60;	// DIGISHIELD: 매블록당 난이도 재조정
consensus.nRuleChangeActivationThreshold = 7560; 	// 7560블록 (189시간) (75% of 10080블록)
consensus.nMinerConfirmationWindow = 10080; 		// 10080블록 (252시간) (10.5날) (302400[3.5날] / 90 * 4 * 0.75)
```

### 비트제니 (DarkGravityWave3: 매블록당 난이도조절)
 * 난이도조절은 매블록당. 
 * 규칙변경은 `2주 이내`에 `100% 만장일치` 합의요망.
```cpp
consensus.nPowTargetTimespan = 14 * 24 * 60 * 60; 	// DGW3: 매블록당 난이도 재조정
consensus.nPowTargetSpacing = 90;			// 90초 (1.5분)
consensus.nRuleChangeActivationThreshold = 13440; 	// 13440블록 (336시간) (100% of 13440블록)
consensus.nMinerConfirmationWindow = 13440; 		// 13440블록 (336시간) (2주) (비트코인과동일)
```

### 버트코인 (KimotoGravityWell: 매블록당 난이도조절)
 * 비트코인보다 블록타임이 `4배` 빠르다. (2.5분) `라이트코인`과 같다.
 * 난이도조절은 매블록당.
 * 규칙변경은 `3.5날 이내`에 `75% 이상` 합의요망.
```cpp
consensus.nPowTargetTimespan = 3.5 * 24 * 60 * 60; 	// 302400초 (3.5날)
consensus.nPowTargetSpacing = 2.5 * 60;			// 150초 (2.5분)
consensus.nRuleChangeActivationThreshold = 1512; 	// 1512블록 (63시간) (75% of 2016블록)
consensus.nMinerConfirmationWindow = 2016; 		// 2016블록 (84시간) (3.5날) (302400 / 150 = 2016)
```

### 레이븐코인
 * 비트코인보다 블록타임이 `10배` 빠르다. (1분)
 * 난이도조절은 매블록당.
 * 규칙변경은 `1.4날 이내`에 `대략 90% 이상` 합의요망. (시간상으로는 90% 이지만 `0.4블록` 오차가 있다.)
```cpp
consensus.nPowTargetTimespan = 2016 * 60; 		// 120960초 (1.4날)
consensus.nPowTargetSpacing = 1 * 60;			// 60초 (1분)
consensus.nRuleChangeActivationThreshold = 1814; 	// 1814블록 (30.24시간) (대략 90% of 2016블록: 정확히는 `1814.4블록`)
consensus.nMinerConfirmationWindow = 2016; 		// 2016블록 (33.6시간) (1.4날)
```

### 슈가체인 (DarkGravityWave3: 매블록당 난이도조절)
 * 비트코인보다 블록타임이 `20배` 빠르다. (30초) 
 * 난이도조절은 매블록당. 
 * 규칙변경은 `2주 이내`에 `75% 이상` 합의요망. `라이트코인`과 같다.
```cpp
consensus.nPowTargetTimespan = 14 * 24 * 60 * 60; 	// DGW3: 매블록당 난이도 재조정
consensus.nPowTargetSpacing = 0.5 * 60; 		// 30초 (0.5분)
consensus.nRuleChangeActivationThreshold = 30240; 	// 30240블록 (252시간) (75% of 40320블록)
consensus.nMinerConfirmationWindow = 40320; 		// 40320블록 (336시간) (2주) (1209600 / 30 = 40320) 
```




