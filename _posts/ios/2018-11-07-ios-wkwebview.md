---
layout: post
title: "iOS12 UIWebView Deprecated"
date: 2018-11-07 00
category: ios
tags: [UIWebView, WKWebView, XCode10]
---



## WKWebView 사용에 익숙해지자

<!-- more -->

UIWebView만 사용해보다가 이번 업데이트때 UIWebView가 deprecated 된다는 메세지가 나왔다.

그리고 오브젝트 라이브러리(View를 드래그해서 가져올수있는곳) 보면 WKWebView

생긴것을 알수가있다. '원래 있었는지...확인은 못해봤어요 ㅎㅎ'

하지만 iOS11 아래버전을 지원한다면 사용은 하지 못한다. 코드로 사용해야한다.

##### 그리고 WKWebView를 사용해야하는 이유는  자바스크립트나 웹로드 속도가 현저히 빠르다 쿠키관리도 가능하다.

--Ex)--

```objective-c
//아래 config는 웹킷 사용시에 데이터 받아올때 사용가능하다.
WKWebViewConfiguration *configuration = [[WKWebViewConfiguration alloc] init];
    
webView = [[WKWebView alloc] initWithFrame:self.view.bounds configuration:configuration];
[webView loadRequest:url];
[webView sizeToFit];
webView.navigationDelegate = self;
webView.UIDelegate = self;
[self.view addSubview:webView];
```

이런식으로 사용하면된다. Delegate는 용어는 다르지만 UIWebVIew와 비슷하다. 