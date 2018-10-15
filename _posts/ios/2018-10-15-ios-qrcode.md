---
layout: post
title: "Swift QRcode make"
date: 2018-10-15 01
category: ios
tags: [ios, swift, qrcode]
---



# Swift QR코드 생성

<!-- more -->



QR코드 생성하는 방법을 찾아보다가 알아낸 Swift로 QR코드 생성하기.

 iOS에서는 자체 라이브러리로 자기가원하는 텍스트를 가지고 QR코드를 생성할 수 있다.



아래 예제 소스로 확인하기 바란다.

```swift
func qrCodeMake(text: String) -> UIImage? {
    guard let filter = CIFilter(name: "CIQRCodeGenerator") else { return nil }
	let stringData = text.data(using: String.Encoding.utf8)
    
  	filter.setValue(stringData, forkey: "inputMessage")
	filter.setValue("H", forKey: "inputCorrectionLevel")
        
    if let outout = filter.outputImage {
        return UIImage(ciImage: outout, scale: 1.0, orientation: UIImageOrientation.down)
    } else {
        return nil
    }
}
```