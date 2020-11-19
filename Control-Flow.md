# Control Flow Exercises

> In order to better prepare you for coding challenges where Xcode autocomplete may not be available and also to get you use to recoginzing compiler error without Xcode, please use [repl.it](https://www.repl.it) for the following exercises.

## Question 1

What will be printed when the code below is run?  Select all that apply.

```swift
let conditionOne = !(4 < 5) || !(3 > 8)
let conditionTwo = !(!true)

if conditionOne {
 print("A")
} else if conditionTwo {
 print("B")
}
if conditionTwo {
 print("C")
}
print("D")
```

- A
- B
- C
- D

<details> 
 <summary>Solution</summary> 

```swift 
let conditionOne = !(4 < 5) || !(3 > 8) // F || T
let conditionTwo = !(!true) // T

if conditionOne { // T
 print("A") // A
} else if conditionTwo {
 print("B")
}
if conditionTwo { // T
 print("C") // C
}
print("D") // D

// A
// C
// D
```
 
</details> 

***
## Question 2

What will the code block below print?  Select all that apply:

```swift
let appInfo = (name: "myCoolApp", version: 0.4)
switch appInfo {
 case (_, 0.0..<1.0):
 print("\(appInfo.0) hasn't released yet")
 case ("myCoolApp", _):
 print("Thanks for looking at myCoolApp!")
 default:
 print("I'm not quite sure what you are looking at")
}
```

- appInfo.0 hasn't released yet
- myCoolApp hasn't released yet
- Thanks for looking at myCoolApp!
- I'm not quite sure what you are looking at
- It will give a compile-time error

<details> 
 <summary>Solution</summary> 

```swift 
let appInfo = (name: "myCoolApp", version: 0.4) // tuple (name, version)
switch appInfo {
 case (_, 0.0..<1.0): // ignores name argument, only checks for version
 print("\(appInfo.0) hasn't released yet") // "myCoolApp hasn't released yet"
 case ("myCoolApp", _):
 print("Thanks for looking at myCoolApp!")
 default:
 print("I'm not quite sure what you are looking at")
}

// "myCoolApp hasn't released yet"
```
 
</details> 


***
## Question 3

What will be printed to the console when the code below is run?  Select all that apply.

```swift
let x: Int = 4
switch x {
case 0..<4:
 print("A")
case 5..<10:
 print("B")
case 11...:
 print("C")
default:
 print("D")
}
```

- A
- B
- C
- D

<details> 
 <summary>Solution</summary> 

```swift 
let x: Int = 4
switch x {
case 0..<4:
 print("A")
case 5..<10:
 print("B")
case 11...:
 print("C")
default:
 print("D") // D
}

// D
```
 
</details> 


***
## Question 4

What are the errors in the code below for the switch statement? Select all that apply.

```swift
let candyType : String = "skittles"

switch candyType {
case "mAndM":
 print("Melts in your mouth, not in your hand")
case "skittles":
 print("Taste the rainbow")
case "snickers":
 print("Hungry? Grab a Snickers")
}
```

- No parentheses around the conditions
- No opening and closing brackets in each of the cases
- No default case in the switch statement
- No print statement right outside the switch statement

<details> 
 <summary>Solution</summary> 

```swift 
let candyType : String = "skittles"

switch candyType {
case "mAndM":
 print("Melts in your mouth, not in your hand")
case "skittles":
 print("Taste the rainbow")
case "snickers":
 print("Hungry? Grab a Snickers")
 // swift must be exhaustive, missing default statement
}

// - No default case in the switch statement
```
 
</details> 


***
## Question 5

Given the current weather conditions (rain, sunny, snow), use a switch statement to print an appropriate message to the user

```swift
let currentWeather = "rain"

// enter code below
```

<details> 
 <summary>Solution</summary> 

```swift 
let currentWeather = "rain"

switch currentWeather {
  case "rain":
    print("Don't forget an umbrella.")
  case "sunny": 
    print("Great beach 🏖 day.") 
  case "snow": 
    print("Time for some hot chocolate.") 
  default: 
    print("Can someone please check the weather.")
}
```
 
</details> 


***
## Question 6

Given the first name and last name of a Fellow, declare a variable `fullName` and use string interpolation to concatenate the Fellow's full name and print to the console e.g The Fellow's full name is John Appleseed

```swift
let firstName = "John"
let lastName = "Appleseed"

// enter code below
```

<details> 
 <summary>Solution</summary> 

```swift 
let firstName = "John"
let lastName = "Appleseed"
var fullName = ""

fullName = "\(firstName) \(lastName)"

print("The Fellow's full name is \(fullName)")
// The Fellow's full name is John Appleseed
```
 
</details> 


***

## Question 7

Convert the if/else statement below into a switch statement.

```swift
let temperatureInFahrenheit = 34

if temperatureInFahrenheit <= 40 {
 print("It's cold out.")
} else if temperatureInFahrenheit >= 85 {
 print("It's really warm.")
} else {
 print("Weather is moderate.")
}

//Re-written statement here

```

<details> 
 <summary>Solution</summary> 

```swift 
switch temperatureInFahrenheit {
  case ...40:
    print("It's cold out.") 
  case 85...: 
    print("It's really warm.") 
  default: 
    print("Weather is moderate.")
}
```
 
</details> 


***

## Question 8

Complete the following code so that "You win!" is printed.

```swift
if {
 print("You win!")
} 
else {
 print("You lose!")
}
```

<details> 
 <summary>Solution</summary> 

```swift 
let didWin = true 

if didWin {
 print("You win!")
} 
else {
 print("You lose!")
}

// You win!
```
 
</details> 

***

## Question 9

Given a variable called numberOfSides, write code using a switch so that it prints out the name of the shape. Account for shapes with 3 to 10 sides and print an error message if out of range.

var numberOfSides = 6

```swift
Example 1:

Input:
var numberOfSides = 4

Output:
Quadilateral

Example 2:

Input:
var numberOfSides = 2

Output:
Error

```

<details> 
 <summary>Solution</summary> 

```swift 
var numberOfSides = 6

switch numberOfSides {
  case 3: 
    print("Triangle.")
  case 4: 
    print("Quadilateral") 
  case 5: 
    print("Pentagon") 
  case 6: 
    print("Hexagon") 
  case 7: 
    print("Heptagon") 
  case 8: 
    print("Octogon") 
  case 9: 
    print("Nonagon") 
  case 10: 
    print("Decagon") 
  default: 
    print("Error")
}
```
 
</details> 

***

## Question 10

Create a switch statement that will convert a number grade into a letter grade as shown below:

```swift
Numeric Score 	Letter Grade
100 	A+
90 - 99	A
80 - 89	B
70 - 79 	C
65 - 69 	D
Below 65 	F
```

<details> 
 <summary>Solution</summary> 

```swift 
let grade = 75 

switch grade {
  case 0..<65: 
    print("F")
  case 65...69: 
    print("D")
  case 70...79: 
    print("C")
  case 80...89: 
    print("B")
  case 90...99: 
    print("A")
  case 100: 
    print("A+")
  default: 
    print("Invalid Grade.")
}
```
 
</details> 

***

## Question 11

What is wrong with the block of code below?  Correct it so it behaves as expected.

```swift
let firstName = "Peter"

if firstName == "Peter" {
 let lastName = "Gabriel"
} else if firstName == "Phil" {
 let lastName = "Collins"
}
let fullName = firstName + " " + lastName
```

<details> 
 <summary>Solution</summary> 

```swift 
let firstName = "Peter"

// lastName was out of scope, we need to define it outside of if and else..if body
var lastName = ""

if firstName == "Peter" {
 lastName = "Gabriel"
} else if firstName == "Phil" {
 lastName = "Collins"
}
let fullName = firstName + " " + lastName 

print(fullName) // Peter Gabriel
```
 
</details> 

***

## Question 12

Write an if statement that prints out what decade of life someone is in (e.g "You are in your twenties). Then, write it as a switch statement.

```swift
let nameAndBirthYear: (String, Int)
```

<details> 
 <summary>Solution</summary> 

```swift 
let nameAndBirthYear: (String, Int) = ("Kim", 1999)

let currentYear = 2020
let yearsOld = currentYear - nameAndBirthYear.1

if yearsOld >= 13 && yearsOld <= 19 {
  print("You are in your teens.")
}
if yearsOld >= 20 && yearsOld <= 29 {
  print("You are in your twenties.")
}
if yearsOld >= 30 && yearsOld <= 39 {
  print("You are in your thirties.")
}
if yearsOld >= 40 && yearsOld <= 49 {
  print("You are in your fourties.")
}
if yearsOld >= 50 && yearsOld <= 59 {
  print("You are in your fiftees.")
}
if yearsOld >= 60 && yearsOld <= 69 {
  print("You are in your sixtees.")
}

// You are in your twenties. 
```

```swift
let nameAndBirthYear: (String, Int) = ("Kim", 1999)

let currentYear = 2020
let yearsOld = currentYear - nameAndBirthYear.1

switch yearsOld {
  case 13...19: 
    print("You are in your teens.")
  case 20...29: 
    print("You are in your twenties.")
  case 30...39: 
    print("You are in your thirties.")
  case 40...49: 
    print("You are in your fourties.")
  case 50...59: 
    print("You are in your fiftees.") 
  case 60...69: 
    print("You are in your sixtees.")
  default: 
    print("Not a valid range")
}

// You are in your twenties. 
```
 
</details> 

***


## Question 13

Consider the below switch statement. What should your system currently print?

```swift
let number = 42

switch number {
case 365:
 print("Days in year")
case 1024:
 print("Bytes in a Kilobyte")
case 0:
 print("Where arrays start")
case 42:
 print("The answer to life, the universe and everything")
default:
 print("Some uninteresting number")
}
```
What happens when you change number to:

-a. 365?

-b. 1024?

-c. 65?

What happens when you remove the default clause?

<details> 
 <summary>Solution</summary> 

```swift 
let number = 42

switch number {
case 365:
 print("Days in year")
case 1024:
 print("Bytes in a Kilobyte")
case 0:
 print("Where arrays start")
case 42:
 print("The answer to life, the universe and everything")
default:
 print("Some uninteresting number")
}
// "The answer to life, the universe and everything"

/*
What happens when you change number to:

-a. 365? - prints "Days in year"

-b. 1024? - prints "Bytes in a Kilobyte"

-c. 65? - Some uninteresting number

What happens when you remove the default clause?
- compiler error, the switch must be exhaustive, we need a default statement as numbers are infinite
*/
```
 
</details> 


***


## Question 14

Consider the variable below called population and the if-condition.

a. Add an else-if-condition that states if population is less than 10000 but greater than 5000, then message changes to say it's "a medium size town".

b. Add an else-condition where message changes to say it's a mid-size town.

c. Convert your final if-else statement to a switch statement.

```swift
var population: Int = 10000
var message = String()

if population > 10000 {
 message = "\(population) is a large town"
}
```

<details> 
 <summary>Solution</summary> 

```swift 
var population = 10000
var message = ""

if population > 10000 {
 message = "\(population) is a large town."
} else if population < 10000 && population > 5000 {
  // a. 
  message = "\(population) is a medium size town."
} else {
  // b.
  message = "\(population) is a mid-size town."
}

print(message)
// 10000 is a mid-size town.
```

```swift 
 var population = 10000
var message = ""

// c. 
switch population {
  case 10_001...: 
    message = "\(population) is a large town."
  case ..<10_000 where population > 5_000: 
    message = "\(population) is a medium size town."
  default: 
    message = "\(population) is a mid-size town."
}

print(message)
// 10000 is a mid-size town.
```
 
</details> 

***

## Question 15

Complete the code below so that it prints out and tells the user if the sum of the two numbers in the tuple is at least 15.

a. Using a conditional

b. Using a switch statement

```swift
let myTuple: (Int, Int) = (5, 10)
```

<details> 
 <summary>Solution</summary> 

```swift 
let myTuple: (Int, Int) = (5, 10)

// a. 

let sum = myTuple.0 + myTuple.1 
if sum >= 15 {
  print("The sum \(sum), is at least 15.")
}

// The sum 15, is at least 15.

// b. 

switch sum {
  case 15...: 
    print("The sum \(sum), is at least 15.")
  default: 
    print("\(sum) is less than 15.")
}

// The sum 15, is at least 15.
```
 
</details> 

***

## Question 16 

FizzBuzz

[LeetCode](https://leetcode.com/problems/fizz-buzz/)
