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

#### Ex1)

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

<img src="/images/ios/avplayerviewcontroller_type1.png" style="width:150px;"/>

^ 이미지 처럼 나오지만 영상은 플레이가 되지 않는다.

#### Ex2)

```swift
NSURL *url = [NSURL URLWithString: @"http://techslides.com/demos/sample-videos/small.mp4"];
AVPlayer *player = [AVPlayer playerWithURL:url];
AVPlayerViewController *vw = [[AVPlayerViewController alloc] init];
vw.showsPlaybackControls = YES;
vw.player = player;
vw.view.frame = self.view.bounds;
[self addChildViewController:vw];
[self.view addSubview:vw.view];
[palyer play];
```

<img src="/images/ios/avplayerviewcontroller_type2.png" style="width:150px;"/>

^ 현재 ViewController에 부모로 넣고 다시 View에 addView를 한후에는 다른 형식에 플레이모달이 나오면서

영상은 플레이가 된다. 하지만 이미지에 보면 X or Done 버튼이없다.

#### Ex3)

```swift
NSURL *url = [NSURL URLWithString: @"http://techslides.com/demos/sample-videos/small.mp4"];
AVPlayer *player = [AVPlayer playerWithURL:url];
AVPlayerViewController *vw = [[AVPlayerViewController alloc] init];
vw.showsPlaybackControls = YES;
vw.player = player;
vw.view.frame = self.view.bounds;
[self presentViewController:vw animated:true completion:^{
        [player play];
    }];
```

<img src="/images/ios/avplayerviewcontroller_type3.png" style="width:150px;"/>

^ 마지막으로 presentViewController로 했을때는 영상이 제대로 나오면서 Done버튼도 같이 나온다.

왜 이렇게 만들었는지는 이유는 모르곘지만, 상황에 따라 쓰면 될꺼같다.