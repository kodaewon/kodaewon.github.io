---
layout: post
title: "프로그래머스 - 시저 암호
도움말
도움말"
date: 2020-01-06
category: algorithm
tags: [swift, algorithm, programmers]
---

# 코딩테스트 연습 > 연습문제 > 시저 암호

<!-- more -->

### 문제 설명

어떤 문장의 각 알파벳을 일정한 거리만큼 밀어서 다른 알파벳으로 바꾸는 암호화 방식을 시저 암호라고 합니다. 예를 들어 AB는 1만큼 밀면 BC가 되고, 3만큼 밀면 DE가 됩니다. z는 1만큼 밀면 a가 됩니다. 문자열 s와 거리 n을 입력받아 s를 n만큼 민 암호문을 만드는 함수, solution을 완성해 보세요..


### 제한 조건

- 공백은 아무리 밀어도 공백입니다.
- s는 알파벳 소문자, 대문자, 공백으로만 이루어져 있습니다.
- s의 길이는 8000이하입니다.
- n은 1 이상, 25이하인 자연수입니다.

### 입출력 예

| s     | n    | result |
| ----- | ---- | ------ |
| AB    | 1    | BC     |
| z     | 1    | a      |
| a B z | 4    | e F d  |

### 문제 풀이

```swift
import Foundation

let alphabet: [String] = ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z"]

func solution(_ s:String, _ n:Int) -> String {
    return s.map { s in
        if s.description == " " {
            return " "
        }else {
            guard let ascii = s.asciiValue else {
                return ""
            }
            
            var isLowercased = false
            var index = Int(ascii - 65.uValue)
            if ascii >= 97.uValue && ascii <= 122.uValue {
                isLowercased = true
                index = Int(ascii - 97.uValue)
            }
            
            index = (index + n) % (alphabet.count)
            if isLowercased {
                return alphabet[index].lowercased()
            }
            
            return alphabet[index]
        }

    }.joined()
}

extension Int {
    var uValue: UInt8 {
        return UInt8(self)
    }
}
```

풀이들에는 유닛코드를 사용해야한다~