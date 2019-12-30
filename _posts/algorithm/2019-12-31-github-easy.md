---
layout: post
title: "프로그래머스 - 문자열 내림차순으로 배치하기
도움말"
date: 2019-12-31
category: algorithm
tags: [swift, algorithm, programmers]
---

# 코딩테스트 연습 > 연습문제 > 문자열 내림차순으로 배치하기

<!-- more -->

### 문제 설명

문자열 s에 나타나는 문자를 큰것부터 작은 순으로 정렬해 새로운 문자열을 리턴하는 함수, solution을 완성해주세요.
s는 영문 대소문자로만 구성되어 있으며, 대문자는 소문자보다 작은 것으로 간주합니다.


### 제한 조건

- str은 길이 1 이상인 문자열입니다.

### 입출력 예

| s       | return  |
| ------- | ------- |
| Zbcdefg | gfedcbZ |

### 문제 풀이

간단하게 sorted를 써주시면 됩니다 

```swift
func solution(_ s: String) -> String {
    return String(s.sorted(by: >))
}
```
