---
layout: post
title: Documentation Comments
date: 2019-01-02 01
category: ios
tags: [swift, objective-c, comment] 
---

# Quick Help에 나올수있게 주석을 달아보자

<!-- more -->



주석처리에 중요성을 알게된 이후 공식 API Quick help에 나오겠끔 할수있는 주석처리를 찾아보았다.

주석처리는 Swift와 Objective-c 양식이 다르다.

### Swift

```swift
/**
    // Summary
    Summary Summary

    // Discussion
    Discussion Discussion

    - parameter id(파라미터 네임): userId
    - returns: The new `userData` instance.
*/
```

### Objective-c

```objective-c
/**
 * Summary Summary Text
 * @Discussion Discussion Text
 *
 * @param id(파라미터 네임): userId
 * @return The new `userData` instance.
 */
```



#### Summary

​	주석처리 다음줄에 해당된다 띄어서 쓸때까지 Summary로 인식한다.

#### Discussion

​	Summary에서 띄어쓰기 후에 글을 쓰면 Discussion 해당되여서 나온다.

​	해당 코드에 설명을 작성하는 라인이다.

#### Parameter

​	parameter칸에 나오는 설명은 해당 함수 파라미터에 맞춰서 나온다. 그에 맞춰서 'parameter [id]: [msg]' 을 하면된다. 만약에 없는 파라미터를 한다면, 작성을 해도 quick help에 나오지 않는다.

#### Returns

​	Returns칸에는 해당 함수에 리턴 값을 설명해 주면 된다.



딱히 정해진건 없지만, 자기꺼에 대한 설명이 제대로 들어가있으면 된다고 생각한다.