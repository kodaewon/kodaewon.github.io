---
layout: post
title: "리액트 시작하기"
date: 2018-10-08
category: react
tags: [ReactNative]
---
# 리액트 첫걸음(설치하기)
<!-- more -->

*설치환경은 Mac으로 포스팅



# ReactNative 설치하기

ReactNative 설치에는 node.js 설치가 필요하다. 

사이트에서 설치 하셔도 되고, 터미널에서 설치하도 무방하다

```
npm install node
```



그후에는 react-navtive를 설치를한다. 

```
npm install -g react-native-cli
-- 권한관려 오류일때는
sudo npm install -g react-native-cli
```



설치가 완료되었다면, 이제는 프로젝트 생성을 하면된다.

프로젝트는 생성은 Xcode를 열어서 하는게 아니라 명령어로 프로젝트를 생성을 한다.

일단 설치할 폴더로 이동을 한후에 해당 명령어를 사용한다.

```
react-native init first
```

나는 first라는 프로젝트를 생성했다. 해당 명령어 실행시에는 first라는 폴더와 함께 안에 프로젝트  파일들이 생성이 된다.



해당 폴더에 보면

xcode 프로젝트 파일이 있을거다. 그거로 해서 실행을 시뮬레이터로 실행시켜도 되고 명령어로 해당 폴더로 간 후에 명령어로 실행시켜도 된다.

```
react-native run-ios
```



그럼 Wellcome To React Navite로 첫화면이 맏이 할 것이다.

--------------------------

main.jsbundle로 프로젝트가 실행이 안될경우가 있다. 이런경우에는 설치시에 main.jsbundle이 생성이 안되서 그렇다 해당 명령어 실행 후 다시 실행해보면 잘 될것이다.

```
react-native bundle --entry-file index.js --platform ios --dev false --bundle-output ios/main.jsbundle --assets-dest ios
```

