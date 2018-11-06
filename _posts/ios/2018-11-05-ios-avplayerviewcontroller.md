---
layout: post
title: "AVPlayerViewController add에 따른 Done버튼"
date: 2018-11-05 00
category: ios
tags: [Objective-c, AVlayerViewController]
---



# Media Play Custom으로 하지 말자

<!-- more -->

동영상 플레이어 모음을 찾다 보니깐 거의다 Custom으로 만든거라서

난 제공하는 라이브러리로 어떻게 안될까 찾아보다가 우연치 않는 상황을 알게되었다.

바로 AVPlayerViewController가 어느 위치로 가느냐에 따라 상황이 다르다는거다.

```swift
NSURL *url = [NSURL URLWithString: @"http://techslides.com/demos/sample-videos/small.mp4"];
AVPlayer *player = [AVPlayer playerWithURL:url];
AVPlayerViewController *vw = [[AVPlayerViewController alloc] init];
vw.showsPlaybackControls = YES;
vw.player = player;
vw.view.frame = self.view.bounds;
[self.view addSubview:vw.view];
[palyer play];
```

<img width="200" height="200" src="/images/ios/avplayerviewcontroller_type1.png" ></img>