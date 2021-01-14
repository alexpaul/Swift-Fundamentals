# Struct Exercises 

## Question 1

Take a look at this struct that represents an alien:

```swift
struct Alien {
 var name: String
 var height: Double
 var homePlanet: String
}
let bilbo = Alien(name: "Bilbo", height: 1.67, homePlanet: "Venus")
```

Will these three lines of code run? If so, why not?

```swift
bilbo.name = "Jake"
bilbo.height = 1.42
bilbo.homePlanet = "Saturn"
```

<details> 
 <summary>Solution</summary>
 
No it won't compile. The `Alien` struct is a value type and it's underlying properties are immutable by default, if a created instance is a constant those properties cannot be mutated. In order to mutate the properties of an `Alien` instance it must be marked with a `var`. 
 
</details> 

Change the declaration of `bilbo` so that the above three lines of code **do** work:

<details> 
 <summary>Solution</summary>
 
```swift 
struct Alien {
  var name: String
  var height: Double
  var homePlanet: String
}

// changing the bilbo instance from a let to a var will now compile
var bilbo = Alien(name: "Bilbo", height: 1.67, homePlanet: "Venus")

bilbo.name = "Jake"
bilbo.height = 1.42
bilbo.homePlanet = "Saturn"
```
 
</details> 

***

## Question 2

Given this bit of code that uses the `Alien` struct:

```swift
var charles = Alien(name: "Charles", height: 2.25, homePlanet: "Pluto")
var charlesFromJupiter = charles
charlesFromJupiter.homePlanet = "Jupiter"
```

What will the value of `charles.homePlanet` be after the above code run? What about the value of `charlesFromJupiter.homePlanet`? Why?

<details> 
 <summary>Solution</summary>
 
The value of `charles.homePlanet` will be `Pluto`.    
The value of `charlesFromJupiter.homePlanet` will be `Jupiter` because `charlesFromJupiter` now has its own copy of `charles` and since its a value type can change it's own properties and that won't affect the original copy of `charles`. 
 
</details> 

***

## Question 3

Here's a struct that represents a bank account:

```swift
struct BankAccount {
  var owner: String
  var balance: Double
  
  func deposit(_ amount: Double) {
    balance += amount
  }
  
  func withdraw(_ amount: Double) {
    balance -= amount
  }
}
```

Does this code work? Why or why not?

<details> 
 <summary>Solution</summary>

The code above does not work since the object is a struct (value-type, immutable by default) we have to mark any functions that modify internal properties with an explicit `mutating` keyword. 
 
</details> 

Fix the `BankAccount` struct so it does work.

<details> 
 <summary>Solution</summary>
 
```swift 
struct BankAccount {
  var owner: String
  var balance: Double
  
  mutating func deposit(_ amount: Double) {
    balance += amount
  }
  
  mutating func withdraw(_ amount: Double) {
    balance -= amount
  }
}
```
 
</details> 

Given the code below (which should incorporate any fixes you made):

```swift
var joeAccount = BankAccount(owner: "Joe", balance: 100.0)
var joeOtherAccount = joeAccount
joeAccount.withdraw(50.0)
```

What will the value of `joeAccount.balance` be after the above code runs? What about the value of `joeOtherAccount.balance`? Why?

<details> 
 <summary>Solution</summary>
 
`joeAccount.balance` will be `50.0`.   
`joeOtherAccount.balance` will be `100.0` since this is a value-type and it has its own copy, modifications to the `joeAccount` instance won't affect `joeOtherAccount` 's balance so it will remain `100.0` thank God that would be quite a shaddy bank. 
 
</details> 

***

## Question 4

a. Write a struct called `Person` that has 3 properties of type `String`: a first name, a last name and a middle name. Have the middle name be optional. Create 2 instances of a `Person`, one with a middle name and one without. Print one of their first names.

<details> 
 <summary>Solution</summary>
 
```swift 
struct Person {
  let firstName: String
  let lastName: String
  let middleName: String?
}

let bob = Person(firstName: "Bob", lastName: "Marley", middleName: "Nestor")
let heather = Person(firstName: "Heather", lastName: "Li", middleName: nil)

print(bob.firstName)
```
 
</details> 


b. Write a computed property in `Person` called `fullName` that will return a formatted string of an instance's full name. Call this property on both the instances you created in part a.

<details> 
 <summary>Solution</summary>
 
```swift 
struct Person {
  let firstName: String
  let lastName: String
  let middleName: String?
  
  var fullName: String {
    let middleName = self.middleName == nil ? " " : " \(self.middleName ?? "") "
    return firstName + middleName + lastName
    
    // alternatively you can use an if let/else
    /*
    if let middleName = self.middleName {
      return "\(firstName) \(middleName) \(lastName)"
    } else {
      return "\(firstName) \(lastName)"
    }
    */
  }
}

let bob = Person(firstName: "Bob", lastName: "Marley", middleName: "Nestor")
let heather = Person(firstName: "Heather", lastName: "Li", middleName: nil)

print(bob.fullName)
print(heather.fullName)
```
 
</details> 

***

## Question 5

a. Create a struct called `Book` that has properties `title`, `author` and `rating`, of type `String`, `String`, and `Double` respectively. Create some instances of `Book`.

<details> 
 <summary>Solution</summary>
 
```swift 
struct Book {
  let title: String
  let author: String
  let rating: Double
}

let goodToGreat = Book(title: "Good To Great", author: "Jim Collins", rating: 8)
let unbroken = Book(title: "Unbroken", author: "Laura Hillenbrand", rating: 9)
let pragmaticProgrammer = Book(title: "The Pragmmatic Programmer", author: "Andrew Hunt", rating: 9)
```
 
</details> 


b. Add a computed property to `Book` called `isGood` that returns `true` if its rating is greater than or equal to 7 and test this new functionality with one of the created instances above. 

<details> 
 <summary>Solution</summary>
 
```swift 
struct Book {
  let title: String
  let author: String
  let rating: Double
  
  var isGood: Bool {
    return rating >= 7
  }
}

let goodToGreat = Book(title: "Good To Great", author: "Jim Collins", rating: 8)
let unbroken = Book(title: "Unbroken", author: "Laura Hillenbrand", rating: 9)
let pragmaticProgrammer = Book(title: "The Pragmmatic Programmer", author: "Andrew Hunt", rating: 9)

print(pragmaticProgrammer.isGood) // true
```
 
</details> 

***

## Question 6

There are three common scales that are used to measure temperature: Celsius, Fahrenheit, and Kelvin:

C = (F - 32) / 1.8
F = 1.8 * C + 32
K = C + 273

a. Make a struct called `FreezingPoint` that has three static properties: `celsius`, `fahrenheit`, and `kelvin`. Give them all values equal to the freezing point of water.

<details> 
 <summary>Solution</summary>
 
```swift 
struct FreezingPoint {
  static let celsius: Double = 0 // freezing point of water
  static let fahrenheit: Double = 1.8 * celsius + 32
  static let kelvin: Double = celsius + 273
}

print(FreezingPoint.celsius) // 0.0
print(FreezingPoint.fahrenheit) // 32.0
print(FreezingPoint.kelvin) // 273.0
```
 
</details> 


b. Make a struct called `Celsius` that has one property: `celsius`, and two methods `getFahrenheitTemp`, and `getKelvinTemp`. Make the values of `fahrenheit` and `kelvin` correct values, converted from the `celsius` property.

```swift
var tenDegreesCelsius = Celsius(celsius: 10.0)
tenDegreesCelsius.celsius //returns 10.0
tenDegreesCelsius.getKelvinTemp() //returns 283.0
tenDegreesCelsius.getFahrenheitTemp() //returns 50.0
```

<details> 
 <summary>Solution</summary>
 
```swift 
struct Celsius {
  let celsius: Double
  
  func getFahrenheitTemp() -> Double {
    return 1.8 * celsius + 32
  }
  
  func getKelvinTemp() -> Double {
    return celsius + 273
  }
}

var tenDegreesCelsius = Celsius(celsius: 10.0)
print(tenDegreesCelsius.celsius) //returns 10.0
print(tenDegreesCelsius.getKelvinTemp()) //returns 283.0
print(tenDegreesCelsius.getFahrenheitTemp()) //returns 50.0
```
 
</details> 

c. Give the `Celsius` struct a computed property called `isBelowFreezing` that returns a `Bool` (true if the temperature is below freezing) and test your new property on the `tenDegreesCelsius` instance. 

<details> 
 <summary>Solution</summary>
 
```swift 
struct Celsius {
  let celsius: Double
  
  var isBelowFreezing: Bool {
    return celsius <= 0
  }
  
  func getFahrenheitTemp() -> Double {
    return 1.8 * celsius + 32
  }
  
  func getKelvinTemp() -> Double {
    return celsius + 273
  }
}

var tenDegreesCelsius = Celsius(celsius: 10.0)

print(tenDegreesCelsius.isBelowFreezing) // false
```
 
</details> 

***

## Question 7

Create a struct called `RGBColor` that has 3 properties, `red`, `green`, `blue` that are all of type `Double`.

Given the below array of color dictionaries, create an array of `RGBColor`.

```swift
let colorDictArray: [[String: Double]] = [["red": 1.0, "green": 0.0, "blue": 0.0],
 ["red": 0.0, "green": 1.0, "blue": 0.0],
 ["red": 0.0, "green": 0.0, "blue": 1.0],
 ["red": 0.6, "green": 0.9, "blue": 0.0],
 ["red": 0.2, "green": 0.2, "blue": 0.5],
 ["red": 0.5, "green": 0.1, "blue": 0.9],]
```

```swift
// Test cases 

/* 
print(colors.count) // 6

print(colors.first?.red ?? 0.0) // 1.0
print(colors.last?.blue ?? 0.0) // 0.9
*/
```

<details> 
 <summary>Solution</summary>
 
```swift 
struct RGBColor {
  let red: Double
  let green: Double
  let blue: Double
}

let colorDictArray: [[String: Double]] = [["red": 1.0, "green": 0.0, "blue": 0.0],
                                          ["red": 0.0, "green": 1.0, "blue": 0.0],
                                          ["red": 0.0, "green": 0.0, "blue": 1.0],
                                          ["red": 0.6, "green": 0.9, "blue": 0.0],
                                          ["red": 0.2, "green": 0.2, "blue": 0.5],
                                          ["red": 0.5, "green": 0.1, "blue": 0.9],]


var colors: [RGBColor] = []
for dict in colorDictArray {
  if let redValue = dict["red"],
     let greenValue = dict["green"],
     let blueValue = dict["blue"] {
    colors.append(RGBColor(red: redValue, green: greenValue, blue: blueValue))
  }
}

print(colors.count) // 6

print(colors.first?.red ?? 0.0) // 1.0
print(colors.last?.blue ?? 0.0) // 0.9
```
 
</details> 

***

## Question 8

Create a struct called `Movie` that has properties for `name` (`String`), `year` (`Int`), `genre` (`String`), `cast` (`[String]`), and `description` (`String`) which is a property of the `CustomStringConvertible` protocol. Create an instance of your `Movie` class. 

```swift 
// Sample Input: 
let theBanker = Movie(name: "The Banker", year: 2020, genre: "Drama", cast: ["Anthony Markie", "Samuel L. Jackson", "Nicholas Hoult", "Nia Long"])

// Output: 
print(theBanker)
The Banker is a Drama released in 2020 with the following cast members: Anthony Markie, Samuel L. Jackson, Nicholas Hoult and Nia Long
```

<details> 
 <summary>Solution</summary>
 
```swift 
struct Movie: CustomStringConvertible {
  let name: String
  let year: Int
  let genre: String
  let cast: [String]
  var description: String {
    var castMembers = ""
    for (index, actor) in cast.enumerated() {
      var endStr = index == cast.count - 1 ? "" : ", "
      if index == cast.count - 2 { endStr = " and " }
      castMembers += actor + endStr
    }
    return "\(name) is a \(genre) released in \(year) with the following cast members: \(castMembers)"
  }
}

let theBanker = Movie(name: "The Banker", year: 2020, genre: "Drama", cast: ["Anthony Markie", "Samuel L. Jackson", "Nicholas Hoult", "Nia Long"])

print(theBanker)
// The Banker is a Drama released in 2020 with the following cast members: Anthony Markie, Samuel L. Jackson, Nicholas Hoult and Nia Long
```
 
</details> 

***

## Question 9

Create a function outside of your `Movie` struct called `makeMovie` that takes in a dictionary of type `[String: Any]`, like `dieHardDict` below, and returns an `optional Movie`. Use `dieHardDict` to create an instance of a `Movie`.

```swift
let dieHardDict: [String: Any] = ["name": "Die Hard",
 "year" : 1987,
 "genre": "action",
 "cast": ["Bruce Willis", "Alan Rickman"],
 "description": "John Mclain saves the day!"]
```

```swift 
// Input 1: 
makeMovie(dict: dieHardDict)

// Output: 
// Die Hard is a action released in 1987 with the following cast members: Bruce Willis and Alan Rickman.

// Input 2: 
makeMovie(dict: [:])

// Output: 
// Movie was not able to be created.
```

<details> 
 <summary>Solution</summary>
 
```swift 
struct Movie: CustomStringConvertible {
  let name: String
  let year: Int
  let genre: String
  let cast: [String]
  var description: String {
    var castMembers = ""
    for (index, actor) in cast.enumerated() {
      var endStr = index == cast.count - 1 ? "" : ", "
      if index == cast.count - 2 { endStr = " and " }
      castMembers += actor + endStr
    }
    return "\(name) is a \(genre) released in \(year) with the following cast members: \(castMembers)."
  }
}

func makeMovie(dict: [String: Any]) -> Movie? {
  guard let name = dict["name"] as? String,
     let year = dict["year"] as? Int,
     let genre = dict["genre"] as? String,
     let cast = dict["cast"] as? [String]
  else {
    return nil
  }
  return Movie(name: name, year: year, genre: genre, cast: cast)
}

let dieHardDict: [String: Any] = ["name": "Die Hard",
 "year" : 1987,
 "genre": "action",
 "cast": ["Bruce Willis", "Alan Rickman"],
 "description": "John Mclain saves the day!"]

if let movie = makeMovie(dict: dieHardDict) {
  print(movie)
} else {
  print("Movie was not able to be created.")
}
```
 
</details> 

***

## Question 10

Given the below array of movie dictionaries, use your function from the last question to create a `Array` of `Movie` 's.

```swift
// movies is an Array of Dictionaries
// each element of movies is a Dictionary with the keys
// 'name','year', 'genre', 'cast' and 'description'
var moviesArray: [[String:Any]] = [
 [
 "name": "Minions",
 "year": 2015,
 "genre": "animation",
 "cast": ["Sandra Bullock", "Jon Hamm", "Michael Keaton"],
 "description": "Evolving from single-celled yellow organisms at the dawn of time, Minions live to serve, but find themselves working for a continual series of unsuccessful masters, from T. Rex to Napoleon. Without a master to grovel for, the Minions fall into a deep depression. But one minion, Kevin, has a plan."
 ],
 [
 "name": "Shrek",
 "year": 2001,
 "genre": "animation",
 "cast": ["Mike Myers", "Eddie Murphy", "Cameron Diaz"],
 "description": "Once upon a time, in a far away swamp, there lived an ogre named Shrek whose precious solitude is suddenly shattered by an invasion of annoying fairy tale characters. They were all banished from their kingdom by the evil Lord Farquaad. Determined to save their home -- not to mention his -- Shrek cuts a deal with Farquaad and sets out to rescue Princess Fiona to be Farquaad\"s bride. Rescuing the Princess may be small compared to her deep, dark secret."
 ],
 [
 "name": "Zootopia",
 "year": 2016,
 "genre": "animation",
 "cast": ["Ginnifer Goodwin", "Jason Bateman", "Idris Elba"],
 "description": "From the largest elephant to the smallest shrew, the city of Zootopia is a mammal metropolis where various animals live and thrive. When Judy Hopps becomes the first rabbit to join the police force, she quickly learns how tough it is to enforce the law."
 ],
 [
 "name": "Avatar",
 "year": 2009,
 "genre": "action",
 "cast": ["Sam Worthington", "Zoe Saldana", "Sigourney Weaver"],
 "description": "On the lush alien world of Pandora live the Na\"vi, beings who appear primitive but are highly evolved. Because the planet\"s environment is poisonous, human/Na\"vi hybrids, called Avatars, must link to human minds to allow for free movement on Pandora. Jake Sully, a paralyzed former Marine, becomes mobile again through one such Avatar and falls in love with a Na\"vi woman. As a bond with her grows, he is drawn into a battle for the survival of her world."
 ],
 [
 "name": "The Dark Knight",
 "year": 2008,
 "genre": "action",
 "cast": ["Christian Bale", "Heath Ledger", "Aaron Eckhart"],
 "description": "With the help of allies Lt. Jim Gordon and DA Harvey Dent, Batman has been able to keep a tight lid on crime in Gotham City. But when a vile young criminal calling himself the Joker suddenly throws the town into chaos, the caped Crusader begins to tread a fine line between heroism and vigilantism."
 ],
 [
 "name": "Transformers",
 "year": 2007,
 "genre": "action",
 "cast": ["Shia LaBeouf", "Megan Fox", "Josh Duhamel"],
 "description": "The fate of humanity is at stake when two races of robots, the good Autobots and the villainous Decepticons, bring their war to Earth. The robots have the ability to change into different mechanical objects as they seek the key to ultimate power. Only a human youth, Sam Witwicky can save the world from total destruction."
 ],
 [
 "name": "Titanic",
 "year": 1997,
 "genre": "drama",
 "cast": ["Leonardo DiCaprio", "Kate Winslet", "Billy Zane"],
 "description": "The ill-fated maiden voyage of the R.M.S. Titanic; the pride and joy of the White Star Line and, at the time, the largest moving object ever built. She was the most luxurious liner of her era -- the \"ship of dreams\" -- which ultimately carried over 1,500 people to their death in the ice cold waters of the North Atlantic in the early hours of April 15, 1912."
 ],
 [
 "name": "The Hunger Games",
 "year": 2012,
 "genre": "drama",
 "cast": ["Jennifer Lawrence", "Josh Hutcherson", "Liam Hemsworth"],
 "description": "Katniss Everdeen voluntarily takes her younger sister\"s place in the Hunger Games, a televised competition in which two teenagers from each of the twelve Districts of Panem are chosen at random to fight to the death."
 ],
 [
 "name": "American Sniper",
 "year": 2014,
 "genre": "drama",
 "cast": ["Bradley Cooper", "Sienna Miller", "Kyle Gallner"],
 "description": "Navy S.E.A.L. sniper Chris Kyle\"s pinpoint accuracy saves countless lives on the battlefield and turns him into a legend. Back home to his wife and kids after four tours of duty, however, Chris finds that it is the war he can\"t leave behind."
 ]
]
```

```swift 
// Test cases: 

print(movies.count) // 9

print(movies.first?.name ?? "") // Minions
print(movies.last?.name ?? "") // American Sniper
```

<details> 
 <summary>Solution</summary>
 
```swift 
let movies = moviesArray.compactMap(makeMovie)

print(movies.count) // 9

print(movies.first?.name ?? "") // Minions
print(movies.last?.name ?? "") // American Sniper
```
 
</details> 

***

## Question 11

Using the Room struct below, write code that demonstrates that it is a value type.

```swift
struct Room {
  var maxOccupancy: Int
  var length: Double
  var width: Double
}
```

<details> 
 <summary>Solution</summary>
 
```swift 
struct Room {
  var maxOccupancy: Int
  var length: Double
  var width: Double
}

let flexSpace = Room(maxOccupancy: 200, length: 100, width: 100)
var classroomOne = flexSpace
classroomOne.maxOccupancy = 40
classroomOne.length = 20
classroomOne.width = 10

print(flexSpace.maxOccupancy) // 200, classroomOne is a copy and cannot change the properties of flexSpace
```
 
</details> 

***

## Question 12

a. Given the Point object below, complete the `distance` method so that it returns the distance between a given point.

The equation for the distance formula can be found [here](https://www.mathsisfun.com/algebra/distance-2-points.html) and is give by:

```swift
let horizontalDistance = pointOneXValue - pointTwoXValue
let verticalDistance = pointOneYValue - pointTwoYValue
let distanceBetweenTwoPoints = sqrt(horizontalDistance * horizontalDistance + verticalDistance * verticalDistance)
```

`sqrt` is a method in Swift that gives the square root.  `import Foundation` to use this method.

```swift
struct Point {
  let x: Double
  let y: Double
  func distance(to point: Point) -> Double {
    //Code in your answer here
  }
}

let pointOne = Point(x: 0, y: 0)
let pointTwo = Point(x: 10, y: 10)

print(pointOne.distance(to: pointTwo)) //Prints 14.142135623730951
```

<details> 
 <summary>Solution</summary>
 
```swift 
struct Point {
  let x: Double
  let y: Double
  func distance(to point: Point) -> Double {
    let horizontalDistance = self.x - point.x
    let verticalDistance = self.y - point.y
    let distanceBetweenTwoPoints = sqrt(horizontalDistance * horizontalDistance + verticalDistance * verticalDistance)
    return distanceBetweenTwoPoints
  }
}

let pointOne = Point(x: 0, y: 0)
let pointTwo = Point(x: 10, y: 10)

print(pointOne.distance(to: pointTwo)) // 14.142135623730951
```
 
</details> 


b. Given the above Point object above, and Circle object below, add a `contains` method that returns whether or not a given point is on the circle

```swift
struct Circle {
  let radius: Double
  let center: Point
}

let pointOne = Point(x: 0, y: 0)
let circleOne = Circle(radius: 5, center: pointOne)
let pointTwo = Point(x: 5, y: 0)
let pointThree = Point(x: 4, y: 0)
let pointFour = Point(x: sqrt(12.5), y: sqrt(12.5))
circleOne.contains(pointTwo) //true
circleOne.contains(pointThree) // false
circleOne.contains(pointFour) //true
```

<details> 
 <summary>Solution</summary>
 
```swift 
struct Circle {
  let radius: Double
  let center: Point
  
  func contains(_ point: Point) -> Bool {
    // 1.
    // find the distance from the origin
    let distanceFromOrigin = center.distance(to: point)
    
    // 2.
    // distance needs to be less than the radius
    return distanceFromOrigin <= radius
  }
}

let pointOne = Point(x: 0, y: 0)
let circleOne = Circle(radius: 5, center: pointOne)
let pointTwo = Point(x: 5, y: 0)
let pointThree = Point(x: 6, y: 0)
let pointFour = Point(x: sqrt(12.5), y: sqrt(12.5))
circleOne.contains(pointTwo) //true
circleOne.contains(pointThree) // false
circleOne.contains(pointFour) //true
```
 
</details> 

c. Add another method to `Circle` that returns a random point on the circle

Hint: Given the radius of a circle and the x value of a point on the circle, the y value of the point is defined by:

```
√(r^2) - (x^2)
```

```swift
circleOne.contains(circleOne.getRandomPoint()) // should always be true
```

<details> 
 <summary>Solution</summary>
 
```swift 
struct Point {
  let x: Double
  let y: Double
  func distance(to point: Point) -> Double {
    let horizontalDistance = self.x - point.x
    let verticalDistance = self.y - point.y
    let distanceBetweenTwoPoints = sqrt(horizontalDistance * horizontalDistance + verticalDistance * verticalDistance)
    return distanceBetweenTwoPoints
  }
}

struct Circle {
  let radius: Double
  let center: Point
  
  func contains(_ point: Point) -> Bool {
    // 1.
    // find the distance from the origin
    let distanceFromOrigin = center.distance(to: point)
    
    // 2.
    // distance needs to be less than the radius
    return distanceFromOrigin <= radius
  }
  
  func getRandomPoint() -> Point {
    let randomX = Double.random(in: -radius...radius)
    let y = sqrt((radius * radius) - (randomX * randomX))
    let point = Point(x: randomX, y: y)
    return point
  }
}

let pointOne = Point(x: 0, y: 0)
let circleOne = Circle(radius: 5, center: pointOne)
let pointTwo = Point(x: 5, y: 0)
let pointThree = Point(x: 6, y: 0)
let pointFour = Point(x: sqrt(12.5), y: sqrt(12.5))
circleOne.contains(pointTwo) //true
circleOne.contains(pointThree) // false
circleOne.contains(pointFour) //true

print(circleOne.contains(circleOne.getRandomPoint())) // should always be true
```
 
</details> 

***

## Question 13

a. Create a struct called HangmanModel with 3 properties `targetWord: String`, `numberOfIncorrectGuesses: Int` and `guessedLetters: [Character]`.

<details> 
 <summary>Solution</summary>
 
```swift 
struct HangmanModel {
  var targetWord: String = ""
  var numberOfIncorrectGuesses: Int = 0
  var guessedLetters: [Character] = []
}
```
 
</details> 

b. Add a method called `playerWon` that returns whether all of the characters in `targetWord` are in `guessedLetters`

```swift
var model = HangmanModel()
model.targetWord = "hello"
model.guessedLetters = ["h","e","o","l"]
model.playerWon //true
```

<details> 
 <summary>Solution</summary>
 
```swift 
extension HangmanModel {
  func playerWon() -> Bool {
    var targetWord = Set(self.targetWord)
    for char in guessedLetters {
      if targetWord.contains(char) {
        if let index = targetWord.firstIndex(of: char) {
          targetWord.remove(at: index)
        }
      }
    }
    return targetWord.isEmpty
  }
}

var model = HangmanModel()
model.targetWord = "hello"
model.guessedLetters = ["h","e","o","l", "l"]
print(model.playerWon()) //true
```
 
</details> 

c. Add a method called `printDisplayVersionOfWord` that prints the `targetWord` replacing characters that are not in `guessedLetters` with "\_"

```
var model = HangmanModel()
model.targetWord = "hello"
model.guessedLetters = ["h","l"]
model.printDisplayVersionOfWord
//prints h_ll_
```

<details> 
 <summary>Solution</summary>
 
```swift 
extension HangmanModel {
  func printDisplayVersionOfWord() {
    let chars = Set(guessedLetters)
    var maskedWord: [Character] = Array(repeating: "_", count: targetWord.count)
    for (index, char) in targetWord.enumerated() { // O(n)
      if chars.contains(char) { // O(1)
        maskedWord[index] = char
      }
    }
    print(maskedWord.map{ String($0) }.joined())
  }
}

var model = HangmanModel()
model.targetWord = "hello"
model.guessedLetters = ["h","l"]
model.printDisplayVersionOfWord() // h_ll_
```
 
</details> 

d. Add a method called `guess(_:)` that takes in a character as input, and updates `guessedLetters` and `numberOfIncorrectGuesses` as appropriate.

```swift
var model = HangmanModel()
model.targetWord = "hello"
model.guess("h")
model.guess("a")
model.guessedLetters // ["h", "a"]
model.numberOfIncorrectGuesses // 1
```

<details> 
 <summary>Solution</summary>
 
```swift 
extension HangmanModel {
  mutating func guess(_ char: Character) {
    if !targetWord.contains(char) && !guessedLetters.contains(char) {
      numberOfIncorrectGuesses += 1
    }
    let allChars = Array(targetWord.filter { $0.lowercased() == String(char) })
    guessedLetters.append(contentsOf: allChars)
  }
}

var model = HangmanModel()
model.targetWord = "hello"
model.guess("h")
model.guess("a")

print(model.guessedLetters) // ["h", "a"]
print(model.numberOfIncorrectGuesses) // 1
```
 
</details> 

e. Have `guess(_:)` also print out the current display version of the word, the number of incorrect guesses and if the player has won.

<details> 
 <summary>Solution</summary>
 
```swift 
extension HangmanModel {
  mutating func guess(_ char: Character) {
    if !targetWord.contains(char) && !guessedLetters.contains(char) {
      numberOfIncorrectGuesses += 1
    }
    let allChars = Array(targetWord.filter { $0.lowercased() == String(char) })
    guessedLetters.append(contentsOf: allChars)
    
    /*
     print out the current display version of the word, the number of incorrect guesses and if the player has won.
     */
    printDisplayVersionOfWord()
    print("Number of incorrect guesses: \(numberOfIncorrectGuesses)")
    print("Game status: \(playerWon())")
  }
}

var model = HangmanModel()
model.targetWord = "hello"
model.guess("h")
model.guess("a")
model.guess("l")
model.guess("o")
model.guess("e")

print(model.guessedLetters) // ["h", "a"]
print(model.numberOfIncorrectGuesses) // 1
```
 
</details> 


