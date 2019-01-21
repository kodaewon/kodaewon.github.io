---
layout: post
title: "IBInspectable, IBDesignable 알아보자"
date: 2019-01-17 01
category: ios
tags: [swift, storyboard, xib]
---



# 나만의 View를 StoryBoard에 나오게 하자!

<!-- more -->

StoryBoard, Xib 사용시하다보면 오른쪽에 값을 설정하는곳 있다. 라이브러리를 사용하다보면 Custom Class View에는 Custom으로 값을 설정하는 칸이 더 생긴다. 그것을 설정하고 활용하는 방법이 바로 **IBInspectable, IBDesignable** 이다.

ibinspectable_ibdesignable_1

스토리보드에 우리가 자주 사용하는 이쪽을 

<img src="/images/ios/ibinspectable_ibdesignable_1.png" style="width:250px;">

**inspector** 라 한다. 이 부분에 내가 원하는 값을 입력할 수 있는 폼을 나타내는게  **IBInspectable** 이고 사용 방법은 

아래와 같다.

<img src="/images/ios/ibinspectable_ibdesignable_2.png" style="width:250px;">

이렇게 입력후 다시 스토리보드에 **inspector** 부분을 본다면 들어가있는걸 확인 할수 있다.

<img src="/images/ios/ibinspectable_ibdesignable_3.png" style="width:250px;">



 **IBDesignable** 은 값을 설정 했을때, 스토리 보드에서 새로 Draw를 해주는 옵션이다. Custom으로 UIView속성을 가진 Class에 **IBDesignable** 을 붙여주면,

<img src="/images/ios/ibinspectable_ibdesignable_4.png" style="width:250px;">



방금 설정했던 값으로 그려진 View를 볼수 있게 된다.

<img src="/images/ios/ibinspectable_ibdesignable_5.png" style="width:300px;">



이렇게 해서 내가 Custom으로 만든 View를 스토리보드에서 확인 할 수 있다. 또는 라이브러리를 가져와서 사용할때 **inspector** 부분에 나오게 이러한 이유 때문인걸 할 수가 있다.