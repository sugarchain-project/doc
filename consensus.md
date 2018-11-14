# 규칙변경합의규정
consensus.nRuleChangeActivationThreshold

### 비트코인
비트코인은 `2016블럭`, `2주`마다 난이도 재조정을 한다. 규칙변경은 `2주 이내`에 `95% 이상` 합의요망.
```cpp
consensus.nPowTargetTimespan = 14 * 24 * 60 * 60; 	// 1209600초 (2주)
consensus.nPowTargetSpacing = 10 * 60;			// 600초 (10분)
consensus.nRuleChangeActivationThreshold = 1916; 	// 1916블럭 (319.2시간) (95% of 2016블럭)
consensus.nMinerConfirmationWindow = 2016; 		// 2016블럭 (336시간) (2주) (1209600 / 600 = 2016)
```

### 라이트코인
비트코인보다 블럭타임이 `4배` 빠르지만 각 비례하여 난이도 재조정 기간은 `2주`로 같다. 규칙변경은 `2주 이내`에 `75% 이상` 합의요망.
```cpp
consensus.nPowTargetTimespan = 3.5 * 24 * 60 * 60; 	// 302400초 (3.5날)
consensus.nPowTargetSpacing = 2.5 * 60;			// 150초 (2.5분)
consensus.nRuleChangeActivationThreshold = 6048; 	// 6048블럭 (252시간) (75% of 8064블럭)
consensus.nMinerConfirmationWindow = 8064; 		// 8064블럭 (336시간) (2주) (302400 / 150 * 4 = 8064)
```

### 모나코인 (독자)
난이도조절은 매블록당이며 규칙변경은 `252시간`이내에 `75% 이상` 합의요망.
```cpp
consensus.nPowTargetTimespan = 1.1 * 24 * 60 * 60; 	// 95040초 (1.1날)
consensus.nPowTargetSpacing = 1.5 * 60; 		// 90초 (1.5분)
consensus.nPowTargetTimespanDigisheld = 1.5 * 60;	// DIGISHIELD: 매블록당 난이도 재조정
consensus.nRuleChangeActivationThreshold = 7560; 	// 7560블럭 (189시간) (75% of 10080블럭)
consensus.nMinerConfirmationWindow = 10080; 		// 10080블럭 (252시간) (10.5날) (302400[3.5날] / 90 * 4 * 0.75)
```

### 비트제니 (독자)
난이도조절은 매블록당이며 규칙변경은 `2주`이내에 `100% 만장일치` 합의요망.
```cpp
consensus.nPowTargetTimespan = 14 * 24 * 60 * 60; 	// DGW3: 사용안함: 매블록당 난이도 재조정
consensus.nPowTargetSpacing = 90;			// 90초 (1.5분)
consensus.nRuleChangeActivationThreshold = 13440; 	// 13440블럭 (336시간) (100% of 13440블럭)
consensus.nMinerConfirmationWindow = 13440; 		// 13440블럭 (336시간) (2주) (비트코인과동일)
```

### 슈가체인
비트코인보다 블럭타임이 `20배` 빠르고 각 비례하여 난이도 재조정 기간은 `2주`로 같다. 규칙변경은 `2주 이내`에 `75% 이상` 합의요망.
```cpp
consensus.nPowTargetTimespan = 14 * 24 * 60 * 60; 	// DGW3: 매블록당 난이도 재조정
consensus.nPowTargetSpacing = 0.5 * 60; 		// 30초 (0.5분)
consensus.nRuleChangeActivationThreshold = 30240; 	// 30240블럭 (252시간) (75% of 40320블럭)
consensus.nMinerConfirmationWindow = 40320; 		// 40320블럭 (336시간) (2주) (1209600 / 30 = 40320) 
```
