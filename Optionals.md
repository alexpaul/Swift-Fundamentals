# Optionals Exercises

## Question 1

a. Given the variable `userNameOne` below, print *"The username is Test User"*.  Use *Optional Binding* (`if let`) to print the name.

```swift
var userNameOne: String? = "Test User"
```

<details> 
    <summary>Solution</summary> 

```swift 
var userNameOne: String? = "Test User"
if let name = userNameOne {
  print("The username is \(name)") // The username is Test User
}
```

</details> 

b. Given the variable `userNameTwo` below, print *"The username is undefined"*.  Use the *nil coalescing operator* (`??`).

```swift
var userNameTwo: String? = nil
```

<details> 
    <summary>Solution</summary> 

```swift 
var userNameTwo: String? = nil
print(userNameTwo ?? "The username is undefined.") // The username is undefined.
```

</details> 

## Question 2

a. Given the variables `rectOneWidth` and `rectOneHeight` below, print "The area of rectOne is 50".  Use *Optional Binding* (`if let`) to print the area.

```swift
var rectOneWidth: Double? = 5
var rectOneHeight: Double? = 10
```

<details> 
    <summary>Solution</summary> 

```swift 
var rectOneWidth: Double? = 5
var rectOneHeight: Double? = 10

if let rectOneWidth = rectOneWidth,
   let rectOneHeight = rectOneHeight {
  print("The are of rectOne is \(rectOneWidth * rectOneHeight)") // The are of rectOne is 50.0
}
```

</details> 

b. Given the variables `rectTwoWidth` and `rectTwoHeight` below, print "The are of rectTwo is not able to be calculated".  Use *Optional Binding* (`if let`) to print this message.

```swift
var rectTwoWidth: Double? = nil
var rectTwoHeight: Double? = nil
```

<details> 
    <summary>Solution</summary> 

```swift 
var rectTwoWidth: Double? = nil
var rectTwoHeight: Double? = nil

if let rectTwoWidth = rectTwoWidth,
   let rectTwoHeight = rectTwoHeight {
  print("The area of rectTwo is \(rectTwoWidth * rectTwoHeight)")
} else {
  print("The area of rectTwo is not able to be calculated.")
}
```

</details> 

## Question 3

a. Given the variables `userOneName`, `userOneAge`, and `userOneHeight` below, write code that prints "Hello Anne!  You are 15 years old and 5.8 feet tall" (1 foot = 12 inches).  Use optional binding.


```swift
var userOneName: String? = "Anne"
var userOneAge: Int? = 15
var userOneHeight: Double? = 70
```

<details> 
    <summary>Solution</summary> 

```swift 
var userOneName: String? = "Anne"
var userOneAge: Int? = 15
var userOneHeight: Double? = 70

if let userOneName = userOneName,
   let userOneAge = userOneAge,
   let userOneHeight = userOneHeight {
  let height = String(format: "%.1f", Double(userOneHeight) / Double(12.0))
  print("Hello \(userOneName)! You are \(userOneAge) years old and \(height) feet tall.")
  // Hello Anne! You are 15 years old and 5.8 feet tall.
}
```

</details> 

b. Given the variables `userTwoName`, `userTwoAge` and `userTwoHeight` below, write code that prints "Hello user!  You are 15 years old and I don't know how tall you are".  Use optional binding

```swift
var userTwoName: String? = nil
var userTwoAge: Int? = 15
var userTwoHeight: Double? = nil
```

<details> 
    <summary>Solution</summary> 

```swift 
var userTwoName: String? = nil
var userTwoAge: Int? = 15
var userTwoHeight: Double? = nil

if let userTwoName = userTwoName,
   let userTwoAge = userTwoAge,
   let userTwoHeight = userTwoHeight {
  let height = String(format: "%.1f", Double(userTwoHeight) / Double(12.0))
  print("Hello \(userTwoName)! You are \(userTwoAge) years old and \(height) feet tall.")
} else {
  print("Hello user! You are 15 years old and I don't know how tall you are.")
  // Hello user! You are 15 years old and I don't know how tall you are.
}
```

</details> 

## Question 4

Give the variable `favoriteNumber`, write code that either prints "Your favorite number is " followed by the number, or "I don't know what your favorite number is"

`favoriteNumber` is of type Int? and will either be `nil` or a random number between 0 and 10.  It will change each time you run your Playground.

```swift
var favoriteNumber = Bool.random() ? Int.random(in: 0...10) : nil
```

<details> 
    <summary>Solution</summary> 

```swift 
var favoriteNumber = Bool.random() ? Int.random(in: 0...10) : nil

if let favoriteNumber = favoriteNumber {
  print("Your favorite number is \(favoriteNumber)")
} else {
  print("I don't know what your favorite number is.")
}
```

</details> 


## Question 5

Given the variables `numOne`, `numTwo` and `numThree`, write code that prints "The sum of all the numbers is " followed by their sum.  If a number is `nil`, don't add it to the sum.  If all numbers are `nil`, the sum is zero.

```swift
var numOne = Bool.random() ? Int.random(in: 0...10) : nil
var numTwo = Bool.random() ? Int.random(in: 0...10) : nil
var numThree = Bool.random() ? Int.random(in: 0...10) : nil
```

<details> 
    <summary>Solution</summary> 

```swift 
var numOne = Bool.random() ? Int.random(in: 0...10) : nil
var numTwo = Bool.random() ? Int.random(in: 0...10) : nil
var numThree = Bool.random() ? Int.random(in: 0...10) : nil

var sum = 0
if numOne == nil && numTwo == nil && numThree == nil {
  print("The sum is zero.")
} else {
  if let numOne = numOne,
     let numTwo = numTwo,
     let numThree = numThree {
    print("The sum of all the numbers is \(numOne + numTwo + numThree).")
  }
  if let numOne = numOne {
    sum += numOne
  }
  if let numTwo = numTwo {
    sum += numTwo
  }
  if let numThree = numThree {
    sum += numThree
  }
  print("The sum is \(sum).")
}
```

</details> 

## Question 6

a. Given the variable `numbers` below, write code that prints "The sum of all the numbers is " followed by their sum.  If a number is `nil`, don't add it to the sum.  If all numbers are `nil`, the sum is zero.

```swift
var numbers = [Int?]()

for _ in 0..<10 {
    numbers.append(Bool.random() ? Int.random(in: 0...100) : nil)
}
```

<details> 
    <summary>Solution</summary> 

```swift 
var numbers = [Int?]()

for _ in 0..<10 {
    numbers.append(Bool.random() ? Int.random(in: 0...100) : nil)
}

var totalSum = 0
for num in numbers {
  totalSum += (num ?? 0)
}
```

</details> 

b. Using the same variable, find the average of all non-nil values.

<details> 
    <summary>Solution</summary> 

```swift 
let nonNilValues = numbers.compactMap { $0 }

let nonNilValuesSum = nonNilValues.reduce(0, +)
print("The average of all the non nil values is \(nonNilValuesSum / nonNilValues.count)")
```

</details> 
