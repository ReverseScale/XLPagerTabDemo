# XLPagerTabDemo
XLPagerTabStrip demo for swift

![](https://img.shields.io/badge/platform-iOS-red.svg) ![](https://img.shields.io/badge/language-Objective--C-blue.svg) ![](https://img.shields.io/badge/download-2.9MB-yellow.svg) ![](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)


## 🤖 Requirements

* iOS 9.0+
* Xcode 9.0+
* Swift


## 🚀 Getting started


## 🎨 Why test the UI?

| List Page | Show Table Page | None Page | 
| ------------- | ------------- | ------------- | 
| ![](http://og1yl0w9z.bkt.clouddn.com/18-7-10/21563862.jpg) | ![](http://og1yl0w9z.bkt.clouddn.com/18-7-10/82626740.jpg) | ![](http://og1yl0w9z.bkt.clouddn.com/18-7-10/94251213.jpg) | 



### 🎯 Installation

#### Install

```
pod 'XLPagerTabStrip', '~> 8.0.1'
```

run 'pod install' in file

## 🛠 Configuration

### Main

Controller：

InstagramExampleViewController.swift

ChildController：

ChildExampleViewController.swift

TableChildExampleViewController.swift

View:

PostCell.swift

PostCell.xib

Data:

DataProvider.swift

#### Setup

```swift
@IBOutlet weak var shadowView: UIView!
let blueInstagramColor = UIColor(red: 37/255.0, green: 111/255.0, blue: 206/255.0, alpha: 1.0)

// MARK: - PagerTabStripDataSource
override func viewControllers(for pagerTabStripController: PagerTabStripViewController) -> [UIViewController] {
    let child_1 = TableChildExampleViewController(style: .plain, itemInfo: "FOLLOWING")
    let child_2 = ChildExampleViewController(itemInfo: "YOU")
    return [child_1, child_2]
}
```

#### Style

```swift
override func viewDidLoad() {
    // change selected bar color
    settings.style.buttonBarBackgroundColor = .white
    settings.style.buttonBarItemBackgroundColor = .white
    settings.style.selectedBarBackgroundColor = blueInstagramColor
    settings.style.buttonBarItemFont = .boldSystemFont(ofSize: 14)
    settings.style.selectedBarHeight = 2.0
    settings.style.buttonBarMinimumLineSpacing = 0
    settings.style.buttonBarItemTitleColor = .black
    settings.style.buttonBarItemsShouldFillAvailableWidth = true
    settings.style.buttonBarLeftContentInset = 0
    settings.style.buttonBarRightContentInset = 0

    changeCurrentIndexProgressive = { [weak self] (oldCell: ButtonBarViewCell?, newCell: ButtonBarViewCell?, progressPercentage: CGFloat, changeCurrentIndex: Bool, animated: Bool) -> Void in
        guard changeCurrentIndex == true else { return }
        oldCell?.label.textColor = .black
        newCell?.label.textColor = self?.blueInstagramColor
    }
    super.viewDidLoad()
}
```



## 📝 App Submission

XLPagerTabStrip：https://github.com/xmartlabs/XLPagerTabStrip

## ⚖ License

```
MIT License

Copyright (c) 2017 ReverseScale

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 😬 Contributions

* WeChat : WhatsXie
* Email : ReverseScale@iCloud.com
* Blog : https://reversescale.github.io
