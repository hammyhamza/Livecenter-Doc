
#### Step 1:
```swift
Livecenter.sharedInstance.api.getMatchList { (matches, error) -> Void in
	// handle the response or error
}
```
 > Call the above method to get the list of matches created by User.
 
 > All the object in the array is a [Match](https://football.newsroom.co/sdk/ios/Structs/Match.php) object.
 
##### Step 2
> Select a match from the list of the matches and pass its id to get match detail data, goals and ticker.

```swift
Livecenter.sharedInstance.api.getMatchData(matchId: selectedMatch.id) { (matchData, error) -> Void in
	// handle the response or error
}
```
