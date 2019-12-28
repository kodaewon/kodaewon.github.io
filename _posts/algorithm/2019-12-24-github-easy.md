---
layout: post
title: "프로그래머스 - 가운데 글자 가져오기"
date: 2019-12-24
category: algorithm
tags: [swift, algorithm, programmers]
---

# 코딩테스트 연습 > 연습문제 > 가운데 글자 가져오기

<!-- more -->

### 문제 설명

단어 s의 가운데 글자를 반환하는 함수, solution을 만들어 보세요. 단어의 길이가 짝수라면 가운데 두글자를 반환하면 됩니다.


### 제한 조건

- s는 길이가 1 이상, 100이하인 스트링입니다.


### 입출력 예

| s     | return |
| ----- | ------ |
| abcde | c      |
| qwer  | we     |

### 문제 풀이

n / 2로 해서 가운데 글자를 가져옵니다. 그후에 짝수일 경우에는 문자열 1부터 시작이라  n / 2로 나누어 떨어진 값 전에 string을 가져와야 해서 - 1로 해서 string을 합 쳤습니다.

```swift
func solution(_ s:String) -> String {
    if s.count < 1 || s.count > 100 {
        return ""
    }
    
    var strings = ""
    
    strings = s[s.index(s.startIndex, offsetBy: (s.count / 2))].description
    if s.count % 2 == 0 {
        strings.insert(s[s.index(s.startIndex, offsetBy: (s.count / 2) - 1)], at: strings.startIndex)
    }

    return strings
}
```

결과로는 성공 했지만 효율성이 떨어지는지 점수가 낫게 나와서 다시 고민을 해야겠다.