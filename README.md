
#### Step 1: Get list of matches created by user
```swift
//create an array to store list of matches
    var matches = [Match]()

Livecenter.sharedInstance.api.getMatchList { (matches, error) -> Void in
    
    //Check if response is not nil
    if let listOfMatches = matches{
    	
    	//pass the list of matches to the array matches
        self.matches = listOfMatches
    }
}
```
> matches is an array of [Match](https://football.newsroom.co/sdk/ios/Structs/Match.php)

#### Step 2: Get detail Data of the selected match
> Select a match from the list of the matches and pass its id to get match detail Data.

```swift
//For example select the first match in the array 
let selectedMatch = matches[0]

//Now get MatchData for the selected Match by passing its id.
Livecenter.sharedInstance.api.getMatchData(matchId: selectedMatch.id) { (matchData, error) -> Void in
    // handle the response or error
}
```
> matchData is an object of [MatchData](https://football.newsroom.co/sdk/ios/Classes/MatchData.php)

#### Step 3: Get goals of the selected match

```swift
//Now get Goals for the selected Match by passing its id.
Livecenter.sharedInstance.api.getMatchGoals(matchId: selectedMatch.id) { (goals, error) -> Void in
    // handle the response or error
}
```
> goals is an array of [Goal](https://football.newsroom.co/sdk/ios/Structs/Goal.php)

#### Step 4: Get tickers of the selected match

```swift
//Now get Tickers for the selected Match by passing its id.
Livecenter.sharedInstance.api.getMatchTicker(matchId: selectedMatch.id) { (tickers, error) -> Void in
    // handle the response or error
}
```
> tickers is an array of [Ticker](https://football.newsroom.co/sdk/ios/Structs/Goal.php)
