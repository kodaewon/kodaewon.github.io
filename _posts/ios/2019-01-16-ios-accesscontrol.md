---
layout: post
title: "Swift Access Control"
date: 2019-01-16
category: ios
tags: [Swift, Access]
---

# Swfit Access Control 설명

<!-- more -->

라이브러리 만들려고 시작하다 보니 Access Control에 개념이 걸리기 시작했다. 그냥 할때이는 기본적인 것만 알고 사용했지만, 라이브러리를 만들때는 제대로 알지 못하면 만들지 못할꺼라 생각했다. 

접근 제한자(Access Control)는 Open, Public, Private, Fileprivate, Private  5가지가 있다. 

가장 낮은 레벨부터 확인해보자.

### Open

​	가장 개방된 접근 한정자이다. 말 그대로 Open 이다. import또는 상속만 받는다면, 어느 곳에서는 사용이 가능하다. sub class로 받는다면 open 메서드는 override를 받아서 사용할수 있다.

### Public

​	open과 동일한 접근 레벨을 가지고 있다. 하지만 sub class 생성과 orverride에 제한이 있다. 라이브러리로는 sub class내에서는 orverride가 허용이 되지만, **import 라이브러리를 사용하는곳에서는 orverride를 제한할 수 있다.**

### Internal

​	접근 한정자가 지정되지 않은 경우 기본적을 사용되는 접근 수준이다. module의 소스 파일에서 사용할 수 있지만 module 외부로는 접근을 할 수 없다.

### Fileprivate

​	소스 파일에서만 접근이 가능하다. 이 말은 같은 파일내라면 extension으로 접근하여 사용이 가능하다.

### Private

​	현재 라인에서만 사용이 가능하다. 같은 소스 파일이라도 extension으로도 불가능하다.

------

## Getter / Setter

Getter, Setter 표현으로 접근 제한자에 권한을 부여 할 수 있다.

아래 소스처럼 사용한다.

```swift
class AccessControl {
    private(set) var check = false
}
```

위에 private보다 파일내에서 접근을 허용하고 싶다면, fileprivate를 사용 하면 된다.

```swift
class AccessControl {
    fileprivate(set) var check = false
}
```

------

## Unit Test

단위 테스트 대상은 자체 module이라서 **intrernal** 인 Application Module에 변수를 접근 할수 없다. 그래서 Unit Test때는 import에 @testable를 선언해 줘야한다.

```swift
@testable import AccessControl
```

