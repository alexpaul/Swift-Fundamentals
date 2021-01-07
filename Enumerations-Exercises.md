# Enumeration exercies 

## Question One

a. Define an enumeration called iOSDeviceType with member values iPhone, iPad, appleWatch. Create a variable called myiPad and initialize it to .iPad.

<details>
  <summary>Solution</summary> 
 
```swift 
enum iOSDeviceType {
  case iPhone
  case iPad
  case appleWatch
}
let myiPad = iOSDeviceType.iPad
```
  
</details> 

b. Adjust your code above so that iPhone and iPad have associated values of type String which represents the model number.  Create an instance of a .iPhone("12") and assign it to a variable called myPhone

<details>
  <summary>Solution</summary> 
 
```swift 
enum iOSDeviceType {
  case iPhone(String)
  case iPad(String)
  case appleWatch
}
let myPhone = iOSDeviceType.iPhone("12")
```
  
</details> 

***

## Question Two

Write a function named `getPosition(startingAt:afterSteps:)` that takes an array of Steps, and a starting location of `(Int, Int)` and returns an `(Int, Int)` tuple representing the final position.

A step .up will increase the y coordinate by 1.
A step .down will decrease the y coordinate by 1.
A step .right will increase the x coordinate by 1.
A step .left will decrease the x coordinate by 1.

```swift
enum Step {
    case up
    case down
    case left
    case right
}

let startingLocation = (x: 0, y: 0)
let steps: [Step] = [.up, .up, .left, .down, .left]

// expected output: (x: -2, y: 1)
```

<details>
  <summary>Solution</summary> 
 
```swift 
enum Step {
  case up
  case down
  case left
  case right
}

func getPosition(startingAt location: (x: Int, y: Int), afterSteps steps: [Step]) -> (x: Int, y: Int) {
  var finalLocation = location
  for step in steps {
    switch step {
    case .up:
      finalLocation.y += 1
    case .down:
      finalLocation.y -= 1
    case .left:
      finalLocation.x -= 1
    case .right:
      finalLocation.x += 1
    }
  }
  return finalLocation
}

let startingLocation = (x: 0, y: 0)
let steps: [Step] = [.up, .up, .left, .down, .left]

let endPosition = getPosition(startingAt: startingLocation, afterSteps: steps)

print(endPosition) // (x: -2, y: 1)
```
  
</details> 

***

## Question Three

You are given a `Coin` enumeration which describes different coin values. Write a function called `getTotalValue(from:)` that takes in an array of tuples of type `(number: Int, coin: Coin)`, and returns the total value of all coins in cents.

```swift
enum Coin: Int {
    case penny = 1
    case nickle = 5
    case dime = 10
    case quarter = 25
}

let coinArr: [(Int, Coin)] = [(10, .penny),
                              (15, .nickle),
                              (3, .quarter),
                              (20, .penny),
                              (3, .dime),
                              (7, .quarter)]
let total = getTotalValue(from: coinArr)

// expected total: 385
```

<details>
  <summary>Solution</summary> 
 
```swift 
func getTotalValue(from values: [(number: Int, coin: Coin)]) -> Int {
  var cents = 0
  for value in values {
    let coinValue = value.coin.rawValue
    let number = value.number
    cents += number * coinValue
  }
  return cents
}

let coinArr: [(Int, Coin)] = [(10, .penny),
                              (15, .nickle),
                              (3, .quarter),
                              (20, .penny),
                              (3, .dime),
                              (7, .quarter)]
let total = getTotalValue(from: coinArr)
print(total) // 385
```
  
</details> 

***

## Question Four

Write an enum called `Day` to represent the days of the week with a raw value of type `String`.
Write a method inside `Day` that returns whether or not it is a weekday (Monday - Friday).

```swift 
// Sample expected outputs 

let day = Day.saturday
day.isWeekday() // false

let anotherDay = Day.wednesday
anotherDay.isWeekday() // true
```

<details>
  <summary>Solution</summary> 
 
```swift 
enum Day: String {
  case monday, tuesday, wednesday, thursday, friday, saturday, sunday
  
  func isWeekday() -> Bool {
    switch self {
    case .monday, .tuesday, .wednesday, .thursday, .friday:
      return true
    default:
      return false
    }
  }
}

let day = Day.saturday
day.isWeekday() // false

let anotherDay = Day.wednesday
anotherDay.isWeekday() // true
```
  
</details> 

***

## Question Five

Define an enumeration named `HandShape` with three members: `.rock`, `.paper`, `.scissors`.
Define an enumeration named `MatchResult` with three members: `.win`, `.draw`, `.lose`.

Write a function called `matchResult(fromPlayerOneShape:andPlayerTwoShape:)` that takes two `HandShapes` and returns a `MatchResult`. It should return the outcome for the first player (the one with the first hand shape).

Rock beats scissors, paper beats rock, scissor beats paper

```swift 
let games: [(playerOne: HandShape, playerTwo: HandShape)] = [(.rock, .paper),
                                           (.paper, .paper),
                                           (.scissors, .rock),
                                           (.rock, .scissors)]
                                           
// expected output: 
/*
 lose
 draw
 lose
 win
*/
```

<details>
  <summary>Solution</summary> 
 
```swift 
enum HandShape {
  case rock, paper, scissors
}

enum MatchResult {
  case win, draw, lose
}

func matchResult(fromPlayerOneShape playerOne: HandShape, andPlayerTwoShape playerTwo: HandShape) -> MatchResult {
  if playerOne == playerTwo {
    return .draw
  }
  if playerOne == .rock && playerTwo == .scissors ||
      playerOne == .paper && playerTwo == .rock ||
      playerOne == .scissors && playerTwo == .paper
      {
    return .win
  }
  return .lose
}

let games: [(playerOne: HandShape, playerTwo: HandShape)] = [(.rock, .paper),
                                           (.paper, .paper),
                                           (.scissors, .rock),
                                           (.rock, .scissors)]
for game in games {
  let result = matchResult(fromPlayerOneShape: game.playerOne, andPlayerTwoShape: game.playerTwo)
  print(result)
}

/*
 lose
 draw
 lose
 win
*/
```
  
</details> 
