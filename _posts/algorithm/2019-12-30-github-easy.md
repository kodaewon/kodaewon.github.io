---
layout: post
title: "프로그래머스 - 문자열 내 p와 y의 개수
도움말"
date: 2019-12-31
category: algorithm
tags: [swift, algorithm, programmers]
---

# 코딩테스트 연습 > 연습문제 > 문자열 내 p와 y의 개수

<!-- more -->

### 문제 설명

대문자와 소문자가 섞여있는 문자열 s가 주어집니다. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 return 하는 solution를 완성하세요. 'p', 'y' 모두 하나도 없는 경우는 항상 True를 리턴합니다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않습니다.

예를 들어 s가 pPoooyY면 true를 return하고 Pyy라면 false를 return합니다.


### 제한 조건

- 문자열 s의 길이 : 50 이하의 자연수
- 문자열 s는 알파벳으로만 이루어져 있습니다.

### 입출력 예

| s       | answer |
| ------- | ------ |
| pPoooyY | true   |
| Pyy     | false  |

### 문제 풀이

swift는 대소문자 비교를 가리기 때문에 소문자 또는 대문자로 바꾼후에

filter를 사용해서 값을 추출했다.

```swift
import Foundation

func solution(_ s: String) -> Bool {
    let S = s.lowercased()
    return S.filter { $0 == "y" }.count == S.filter { $0 == "p" }.count ? true : false
}
```
