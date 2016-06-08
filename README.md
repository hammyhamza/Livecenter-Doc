
#### Step 1: (Get list of matches created by user)
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

#### Step 2: (Get goals of the selected match)
> Select a match from the list of the matches and pass its id to get match detail data, goals and ticker.

```swift
//For example select the first match in the array 
let selectedMatch = matches[0]

//Now get the Goals for the selected Match by passing its id.
Livecenter.sharedInstance.api.getMatchGoals(matchId: selectedMatch.id) { (goals, error) -> Void in
    // handle the response or error
}
```
