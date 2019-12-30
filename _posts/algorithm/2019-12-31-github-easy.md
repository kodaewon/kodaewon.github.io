---
layout: post
title: "프로그래머스 - 나누어 떨어지는 숫자 배열"
date: 2019-12-26
category: algorithm
tags: [swift, algorithm, programmers]
---

# 코딩테스트 연습 > 연습문제 > 나누어 떨어지는 숫자 배열

<!-- more -->

### 문제 설명

array의 각 element 중 divisor로 나누어 떨어지는 값을 오름차순으로 정렬한 배열을 반환하는 함수, solution을 작성해주세요. divisor로 나누어 떨어지는 element가 하나도 없다면 배열에 -1을 담아 반환하세요.


### 제한 조건

- arr은 자연수를 담은 배열입니다.
- 정수 i, j에 대해 i ≠ j 이면 arr[i] ≠ arr[j] 입니다.
- divisor는 자연수입니다.
- array는 길이 1 이상인 배열입니다.

### 입출력 예

| arr           | divisor | return        |
| ------------- | ------- | ------------- |
| [5, 9, 7, 10] | 5       | [5, 10]       |
| [2, 36, 1, 3] | 1       | [1, 2, 3, 36] |
| [3,2,6]       | 10      | [-1]          |

### 문제 풀이

이번 문제는 많이 쉬웠다고 볼 수 있습니다. 다른 프로젝트 경험이 좀 있다면 쉽게 풀었을것 입니다.

데이터를 걸러내는 문제입니다. 저는 filter로 해서 풀었습니다. 

또는 for문으로 하시면 됩니다.

```swift
func solution(_ arr:[Int], _ divisor:Int) -> [Int] {
    let arrFilter = arr.filter{ ($0 % divisor) == 0 }
    if arrFilter.isEmpty {
        return [-1]
    }
    
    return arrFilter.sorted()
}
```

문제는 풀었지만 한가지 문제가 있었습니다. 프로그래머스가 점수를 .... 1점을 줬습니다.. 다른 방법이 있는 모양 입니다 ㅠㅠ