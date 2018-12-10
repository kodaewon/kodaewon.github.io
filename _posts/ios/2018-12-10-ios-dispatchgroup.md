---
layou: post
title: "순차적인 결과을 한곳에 모으고 싶을때 DispatchGroup"
date: 2018-12-10
category: ios
tags: [iOS, swift, Dispatch, Thread]
---

# 여러개에 작업을 순차적으로 하고싶을때

<!-- more -->

앱을 만들다보면 여러개에 데이터를 순차적으로 해결하고싶다. 그러나 통신 및 completion 으로는 해결하지 못한다.

서로가 멀티쓰레드를 사용하고있어서 이다. 이를 한곳에 모일 좋은 방법을 찾다보니 DispatchGroup 이라는게 있다.

(세마포어라는 애도 있다.) 

### DispatchGroup 사용예

```swift
let group = DispatchGroup()
group.enter()
self.apiList(list_type: "a") {
    group.leave()
}

group.enter()
self.apiList(list_type: "b") {
    group.leave()
}

group.notify(queue: .main) {
    self.collectionView.reloadData()
}
```

enter()와 leave()라는 걸로 열고 닫고 하는방식을 한다. 당연 leave()를 하지 않은상태에서는 해당 쓰레드는 대기 상태가 된다. notify()는 위에 작업이 끝날때를 기다리며 끝난 동시에 비동기로 해당 쓰레드를 실행한다.

비동기가 있다면 동기도 있다 그것은 wait()이다.  notify() 동일한 방식으로 사용된다.

```swift
group.wait(timeout: .distantFuture)
```

timeout은 끝난후 시간을 설정하여 실행시간을 조절할수있다.



쓰레드에 익숙하다면 이  DispatchGroup 사용방법은 간단할 것이다.