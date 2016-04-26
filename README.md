## Introduction

Here are the detailed steps on how you can install Livecenter SDK in your iOS App. In case you have any trouble using or understanding this, please reach out to whoop@thoughtchimp.com


## Requirements

- iOS 8.0+ 
- Xcode 7.3+

## Installation

#### CocoaPods

To integrate LivecenterKit into your Xcode project using CocoaPods, specify it in your `Podfile`:

```ruby
platform :ios, '8.0'
use_frameworks!

pod 'LivecenterKit', :git => 'https://github.com/thoughtchimp/livecenter-ios-sdk.git'
```

Then, run the following command:

```bash
$ pod install
```

## Setting up LivecenterKit

##### Import the Livecenter kit framework

```swift
import LivecenterKit
```

##### Integrate With Your App

To initialize the Livecenter Kit with your app’s credentials, pass them to setConsumerKey: secret: in your app’s AppDelegate.

```swift
Livecenter.sharedInstance.setConsumerKey(consumerKey, secret: consumerSecret)
```

## Usage

##### Load Match List

```swift
Livecenter.sharedInstance.api.getMatchList { (matches, error) -> Void in
	// handle the response or error
}
```

 > This methods return an array of all the matches created by the User.
 > All the object in the array is a [Match](https://football.newsroom.co/sdk/ios/Structs/Match.html) object.

##### Load Match Data

```swift
Livecenter.sharedInstance.api.getMatchData(matchId: selectedMatch.id) { (matchData, error) -> Void in
	// handle the response or error
}
```

 > Details of the match can be accessed by passing the id of the selected match from the list of matches which was return in `getMatchList` function. 

##### Load Match Goals

```swift
Livecenter.sharedInstance.api.getMatchGoals(matchId: selectedMatch.id) { (goals, error) -> Void in
	// handle the response or error
}
```

##### Load Match Ticker

```swift
Livecenter.sharedInstance.api.getMatchTicker(matchId: selectedMatch.id) { (tickers, error) -> Void in
	// handle the response or error
}
```

## Display Newsroom View

##### Import the Livecenter kit framework

```swift
import LivecenterKit
```
##### Create a LivecenterView

```swift
let livecenterView = LivecenterView(frame: CGRect(x: 0, y: 110, width: 320, height: 400))

//Set its delegate
livecenterView.delegate = self

//loadLivecenter match 'Liveblog' with matchId and count
  livecenterView.loadLivecenter(matchId: matchId, livecenterType: .Liveblog, count: 10)

//loadLivecenter match 'Social' with matchId and count
  livecenterView.loadLiveCenter(matchId: matchId, livecenterType: .Social, count: 10)
```

##### Handle LivecenterView  delegate

```swift
func livecenterViewLoadFinish() {
 //livecenterView Loading Finish        
}
    
func livecenterViewEmptyPage() {
	//livecenterView Return Empty Page        
}
    
func livecenterViewLoadFailed(error: NSError) {
	//livecenter Return Error
      print(error.localizedDescription)
}
```
