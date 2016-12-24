
<p align="center" >
<img src="https://raw.githubusercontent.com/willpowell8/LocalizationKit_iOS/master/page/LocalizationLogo.png" alt="LocalizationKit" title="LocalizationKit">
</p>
# LocalizationKit
[![CI Status](http://img.shields.io/travis/Will Powell/LocalizationKit.svg?style=flat)](https://travis-ci.org/Will Powell/LocalizationKit)
[![Version](https://img.shields.io/cocoapods/v/LocalizationKit.svg?style=flat)](http://cocoapods.org/pods/LocalizationKit)
[![License](https://img.shields.io/cocoapods/l/LocalizationKit.svg?style=flat)](http://cocoapods.org/pods/LocalizationKit)
[![Platform](https://img.shields.io/cocoapods/p/LocalizationKit.svg?style=flat)](http://cocoapods.org/pods/LocalizationKit)

Localization kit is a powerful to localize texts and translation management tool. I am a developer and invariably I get the questions 'Can you just change this text?' or 'Can you add another language?' I have designed this framework so you can manage these translations and texts without having to recompile, resubmit and without the need to use developers. Essentially take out all of the pain.

## How does it work
Localization Kit quickly and easily integrates into your app using Cocoapods. Then it connects to services from [LocalizationKit.com](http://www.localizationkit.com/app/) which are free to use and manage. Then as you create items in your iOS app the text keys become available instantly in the online web UI. From there you can change the text and it is reflected within app in realtime (as you type any key).

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Installation

LocalizationKit is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:
```ruby
pod "LocalizationKit"
```

Then go to LocalizationKit.com/app/ and create a new app on the left handside using your name. Then take the code generated currently in the url after #/app/...KEY HERE...

Then put the following into your app delegate:

At the top:
```ruby
import LocalizationKit
```
and in the didFinishLaunchingWithOptions the following with your key:
```ruby
Localization.start(appKey: "[[KEY]]")
```

###Enabling Live Update
One of the most powerful features of LocalizationKit is the capability to edit the text in realtime on the device. You can start the live service in the following ways:
####At Initialization
```ruby
Localization.start(appKey: "bed920eb-9802-4a2c-a8c0-69194729d69d", live:true)
```

####From within Settings Bundle
Make sure you create a settings bundle with boolean object named live_localization
```ruby
Localization.start(appKey: "bed920eb-9802-4a2c-a8c0-69194729d69d", useSettings:true)
```
####Toggle it within app
```ruby
Localization.liveEnabled = true
```

##Using in Xcode
Localization kit has support for Xcode UI development. The process is as simple as:
- install the cocoapod
- open storyboard or xib file
- select component eg UILabel or drag on standard component UILabel
- open attribute selector
- set a Localize Key
- run app and the key will be available online
<img src="https://raw.githubusercontent.com/willpowell8/LocalizationKit_iOS/master/page/iOS_Localization_IBInspector_Xcode_1_1.png" alt="LocalizationKit" title="LocalizationKit">
</p>

##Manual Use
You can always use Localization without using the storyboard integration by calling the get function with id string and default text and it will return a localized string.
```ruby
let resultText = Localization.get("localization Key", alternate:"default label text")
```
##Localization Keys
Localization Keys are the unique identifiers that allow you to assign localization to the correct part within your app. You can use any string as a device identifier, however the application has some features to make live easier if you use dot separation methodology: ie. Product.Details.Label

##Other Functions

####Reset to device language
```ruby
Localization.resetToDeviceLanguage()
```

## Author

Will Powell - [LinkedIn](https://www.linkedin.com/in/willpowelluk) | [Blog](http://www.willpowell.co.uk)

## License

LocalizationKit is available under the MIT license. See the LICENSE file for more info.
