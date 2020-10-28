# Collection Types - Arrays Exercises

## Question 1

Create an array of strings called `colors` that contain "orange", "red", "yellow", "turquoise", and "lavender".

Then, using array subscripting and string interpolation, print out the String `"orange, yellow, and lavender are some of my favorite colors"`.

<details> 
  <summary>Solution</summary> 
  
```swift 
var colors = ["orange", "red", "yellow", "turquoise", "lavender"]

print("\(colors[0]), \(colors[2]) and \(colors[colors.count - 1]) are some of my favorite colors")

// orange, yellow and lavender are some of my favorite colors
```
  
</details> 

***

## Question 2

Remove "Illinois" and "Kansas" from the array below.

`var westernStates = ["California", "Oregon", "Washington", "Idaho", "Illinois", "Kansas"]`


<details> 
  <summary>Solution</summary> 
  
```swift 
var westernStates = ["California", "Oregon", "Washington", "Idaho", "Illinois", "Kansas"]
westernStates = westernStates.dropLast(2)
print(westernStates) // ["California", "Oregon", "Washington", "Idaho"]
```
  
</details> 

***


## Question 3

Iterate through the array below. For each state, print out the name of the state, a colon, and whether it is or is not **in the continental United States.**

`let moreStates = ["Hawaii", "New Mexico", "Alaska", "Montana", "Texas", "New York", "Florida"]`


<details> 
  <summary>Solution</summary> 
  
```swift 
let moreStates = ["Hawaii", "New Mexico", "Alaska", "Montana", "Texas", "New York", "Florida"]

for state in moreStates {
  if state == "Hawaii" {
    print("\(state) is NOT in the continental United States.")
  } else {
    print("\(state) is in the continental United States.")
  }
}

/*
 Hawaii is NOT in the continental United States.
 New Mexico is in the continental United States.
 Alaska is in the continental United States.
 Montana is in the continental United States.
 Texas is in the continental United States.
 New York is in the continental United States.
 Florida is in the continental United States.
*/
```
  
</details> 

***


## Question 4

Print out how many non-whitespace characters are in `myString`:

`let myString = "This is good practice with Strings!"`

<details> 
  <summary>Solution</summary> 
  
```swift 
let myString = "This is good practice with Strings!"

var nonWhitespaceCount = 0
for char in myString {
  if char != " " {
    nonWhitespaceCount += 1
  }
}
print("There are \(nonWhitespaceCount) non-whitespace characters in myString")
// There are 30 non-whitespace characters in myString
```
  
</details> 

Iterate through the array below. For each sentence, print out how many non-whitespace characters are in it.

`let myFavoriteQuotes = ["To be or not to be, that is the question.", "The only source of knowledge is experience.", "Mr. Gorbachev, tear down this wall!", "Four score and twenty years ago..."]`

<details> 
  <summary>Solution</summary> 
  
```swift 
let myFavoriteQuotes = ["To be or not to be, that is the question.", "The only source of knowledge is experience.", "Mr. Gorbachev, tear down this wall!", "Four score and twenty years ago..."]


for str in myFavoriteQuotes {
  var nonWhitespaceCount = 0
  for char in str {
    if char != " " {
      nonWhitespaceCount += 1
    }
  }
  print("There are \(nonWhitespaceCount) non-whitespace characters in myString")
}

/*
 There are 32 non-whitespace characters in myString
 There are 37 non-whitespace characters in myString
 There are 30 non-whitespace characters in myString
 There are 29 non-whitespace characters in myString
*/
```
  
</details> 

***


## Question 5

Iterate through `garden` and place any 🌷 that you find into the `basket`. Replace any 🌷 that you pick up with `"dirt"`. Then print how many 🌷 are in your `basket`.

```swift
var garden = ["dirt","🌷","dirt","🌷","dirt","dirt","🌷","dirt","🌷","dirt"]
var basket = [String]()
```


<details> 
  <summary>Solution</summary> 
  
```swift 
var garden = ["dirt","🌷","dirt","🌷","dirt","dirt","🌷","dirt","🌷","dirt"]
var basket = [String]()


for (index, str) in garden.enumerated() {
  if str == "🌷" {
    basket.append("🌷")
    garden[index] = "dirt"
  }
}

print(garden)
print("The basket now has \(basket.count) flowers 🌷")

/*
 ["dirt", "dirt", "dirt", "dirt", "dirt", "dirt", "dirt", "dirt", "dirt", "dirt"]
 The basket now has 4 flowers 🌷
*/
```
  
</details> 

***


## Question 6

The below array represents an unfinished batting lineup for a baseball team. **You, the coach,** need to make some last minute changes:

- Add "Suzuki" to the end of your lineup.
- Change "Jeter" to "Tejada".
- Change "Thomas" for "Guerrero"
- Put "Reyes" to bat 8th instead.

`var battingLineup = ["Reyes", "Jeter", "Ramirez", "Pujols","Griffey","Thomas","Jones", "Rodriguez"]`


<details> 
  <summary>Solution</summary> 
  
```swift 
var battingLineup = ["Reyes", "Jeter", "Ramirez", "Pujols","Griffey","Thomas","Jones", "Rodriguez"]

battingLineup.append("Suzuki")

for (index, player) in battingLineup.enumerated() {
  if player == "Jeter" {
    battingLineup[index] = "Tejada"
  }
  if player == "Thomas" {
    battingLineup[index] = "Guerrero"
  }
}

if let index = battingLineup.firstIndex(of: "Reyes") {
  battingLineup.remove(at: index)
  battingLineup.insert("Reyes", at: 7)
}

print(battingLineup)

// ["Tejada", "Ramirez", "Pujols", "Griffey", "Guerrero", "Jones", "Rodriguez", "Reyes", "Suzuki"]
```
  
</details> 

***

## Question 7

Given an array of Ints, find out if it contains a target number.  

(The built-in `contains(_:)` function will do this, but you aren't allowed to use it for this exercise.)


```swift
var numbers: [Int]

let target: Int = 32
```

Ex.1

```swift
numbers = [4,2,6,73,32,4,2,1]

target = 32

//true
```

<details> 
  <summary>Solution</summary> 
  
```swift 
let numbers = [4,2,6,73,32,4,2,1]
let target = 32

var targetNumberFound = false
for num in numbers {
  if num == target {
    targetNumberFound = true
  }
}

print(targetNumberFound) // true
```
  
</details> 

Ex. 2

```swift
numbers = [32459,2,4,5,1,4,2,1]

target = 3

//false
```

<details> 
  <summary>Solution</summary> 
  
```swift 
let numbers = [32459,2,4,5,1,4,2,1]
let target = 3

var targetNumberFound = false
for num in numbers {
  if num == target {
    targetNumberFound = true
  }
}

print(targetNumberFound) // true
```
  
</details> 

***


## Question 8

Find the largest value in an array of Int.  Do not use the built-in `max()` method.

```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

//This creates an array of 100 numbers in between 0 and 200.  For now, you don't need to worry about how it does that.
```

<details> 
  <summary>Solution</summary> 
  
```swift 
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

print(arrayOfNumbers)

var largestValue = arrayOfNumbers[0]
for num in arrayOfNumbers {
  if num > largestValue {
    largestValue = num
  }
}

print("largest value is \(largestValue)")
// largest value is 199
```

</details> 

***


## Question 9

Find the smallest value in an array of Int.  Do not use the built in min() method.

```swift
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

//This creates an array of 100 numbers in between 0 and 200.  For now, you don't need to worry about how it does that.
```


<details> 
  <summary>Solution</summary> 
  
```swift 
let arrayOfNumbers: [Int] = (1...100).map{ _ in Int.random(in: 0...200)}.map{Int($0)}

print(arrayOfNumbers)

var smallestValue = arrayOfNumbers[0]
for num in arrayOfNumbers {
  if num < smallestValue {
    smallestValue = num
  }
}

print("smallest value is \(smallestValue)")
// smallest value is 0
```
  
</details> 

***


## Question 10

Iterate through `secondListOfNumbers`, and print out all the odd numbers.

`var secondListOfNumbers = [19,13,14,19,101,10000,141,404]`


<details> 
  <summary>Solution</summary> 
  
```swift 
var secondListOfNumbers = [19, 13, 14, 19, 101, 10000, 141, 404]

for num in secondListOfNumbers {
  if num % 2 == 1 {
    print(num, terminator: " ")
  }
}

// 19 13 19 101 141
```
  
</details> 

***

## Question 11

Iterate through `thirdListOfNumbers`, and print out the sum.

`var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]`


<details> 
  <summary>Solution</summary> 
  
```swift 
var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]
var sum = 0

for num in thirdListOfNumbers {
  sum += num
}

print(sum) // 334
```
  
</details> 

***


## Question 12

Iterate through `thirdListOfNumbers`, and print out the sum of all the even numbers.

`var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]`


<details> 
  <summary>Solution</summary> 
  
```swift 
var thirdListOfNumbers = [11, 26, 49, 61, 25, 40, 74, 3, 22, 23]
var sum = 0

for num in thirdListOfNumbers {
  if num % 2 == 0 {
    sum += num
  }
}

print(sum) // 162 
```
  
</details> 

***


## Question 13

Append every Int that appears in both `listOne` and `listTwo` to the `sharedElements` array. Then print **how many Ints** are shared.

Assumption: both arrays are of equal length. 

Constraints: you cannot use Sets

```swift
var listOne = [28, 64, 7, 96, 13, 32, 94, 11, 80, 68]
var listTwo = [18, 94, 48, 6, 42, 68, 79, 76, 13, 7]
var sharedElements = [Int]()
```


<details> 
  <summary>Solution</summary> 
  
```swift 
var listOne = [28, 64, 7, 96, 13, 32, 94, 11, 80, 68]
var listTwo = [18, 94, 48, 6, 42, 68, 79, 76, 13, 7]
var sharedElements = [Int]()


for num in listOne {
  if listTwo.contains(num) {
    sharedElements.append(num)
  }
}

print("\(sharedElements) \(sharedElements.count) are shared")

// [7, 13, 94, 68] 4 are shared
```
  
</details> 

***

## Question 14

Write code such that `noDupeList` has all the same Ints as `dupeFriendlyList`, but has no more than one of each Int.

Constraints: you cannot use Sets

```swift
var dupeFriendlyList = [4,2,6,2,2,6,4,9,2,1]
var noDupeList: [Int] = []
```


<details> 
  <summary>Solution</summary> 
  
```swift 
var dupeFriendlyList = [4,2,6,2,2,6,4,9,2,1]
var noDupeList: [Int] = []

for num in dupeFriendlyList {
  if !noDupeList.contains(num) {
    noDupeList.append(num)
  }
}

print(noDupeList)
```
  
</details> 

***


## Question 15

Find the second smallest number in an Array of Ints

`let arrayOfNumbers = [-6, 13, 0, 34, 0, 45, -12, 9, 11, 4]`

<details> 
  <summary>Solution</summary> 
  
```swift 
let arrayOfNumbers = [-6, 13, 0, 34, 0, 45, -12, 9, 11, 4]

var secondSmallest = Int.max
var smallest = Int.max

for num in arrayOfNumbers {
  if num < smallest {
    secondSmallest = smallest
    smallest = num
  } else if num < secondSmallest && num != smallest {
    secondSmallest = num
  }
}

print(smallest, secondSmallest) // -12, -6
```
  
</details> 

***


## Question 16

If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Find the sum of all the multiples of 3 or 5 below 1000.


<details> 
  <summary>Solution</summary> 
  
```swift 
```
  
</details> 

***


## Question 17

Make an array that contains all elements that appear **more than twice** in `someRepeatsAgain`.

```swift
var someRepeatsAgain = [25,11,30,31,50,28,4,37,13,20,24,38,28,14,44,33,7,43,39,35,36,42,1,40,7,14,23,46,21,39,11,42,12,38,41,48,20,23,29,24,50,41,38,23,11,30,50,13,13,16,10,8,3,43,10,20,28,39,24,36,21,13,40,25,37,39,31,4,46,20,38,2,7,11,11,41,45,9,49,31,38,23,41,16,49,29,14,6,6,11,5,39,13,17,43,1,1,15,25]
```


<details> 
  <summary>Solution</summary> 
  
```swift 
```
  
</details> 

***


## Question 18

Identify if there are 3 integers that sum to 10 in the following array. If so, print them as a triplet. If there are multiple triplets, print all possible triplets.

`var tripleSumArr = [-20,-14, -8,-5,-3,-2,1,2,3,4,9,15,20,30]`


<details> 
  <summary>Solution</summary> 
  
```swift 
```
  
</details> 

***


## Question 19

Given an array of Strings, find the the String with the most "a"s in it.

input: `["apes", "abba", "apple"]`

output: `"abba"`


<details> 
  <summary>Solution</summary> 
  
```swift 
```
  
</details> 

***


## Question 20

Given an Array of Arrays of Ints, find the Array of Ints with the largest sum:

Input: `[[2,4,1],[3,0],[9,3]]`

Output: `[9,3]`


<details> 
  <summary>Solution</summary> 
  
```swift 
```
  
</details> 

***


## Question 21

Given an Array of Tuples of type `(Int, Int)`, create an array containing all the tuples where the first Int is equal to the second Int.

Input: `[(4,2), (-3,-3), (1,1), (3,9)]`

Output: `[(-3,-3), (1,1)]`


<details> 
  <summary>Solution</summary> 
  
```swift 
```
  
</details> 

***


## Question 22

Given an Array of Bools, make a variable called `allAreTrue` that is true if all of the Bools are true and false if any of them are false.

Input: `[true, false, true, true]`

Output: `false`


<details> 
  <summary>Solution</summary> 
  
```swift 
```
  
</details> 

***

## Question 23

Given an Array of Ranges of Ints, create an array that has all the values from all the ranges in order from smallest to greatest with no duplicates.

Input: `[0..<3 , 2..<10, -4..<6, 13..<14]`

Output: `[-4,-3,-2,-1,0,1,2,3,4,5,6,7,8,9,10,13]`


<details> 
  <summary>Solution</summary> 
  
```swift 
```
  
</details> 

***


## Question 24

Given an array of Characters, create a String ignoring and uppercase Characters and spaces.  Then uppercase every other character of the String.

Input: `let arr: [Character] = ["a", "p","P","l","E"," ","S","a","u","C,"e"]`

Output: `"ApLeAuE"`


<details> 
  <summary>Solution</summary> 
  
```swift 
```
  
</details> 

***


## Question 25

Print out each element in `myMatrix`

`var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]`


<details> 
  <summary>Solution</summary> 
  
```swift 
```
  
</details> 

***


## Question 26

Print out the sum of the diagonals of `myMatrix`.

`var myMatrix = [[10, 14, 12], [91, 1, 9], [31, 3, 21]]`


<details> 
  <summary>Solution</summary> 
  
```swift 
```
  
</details> 

***

## Question 27

Using for loops, rotate `matrixToRotate` 90 degrees.

var matrixToRotate = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

![Matrix Rotation](images/rotated_matrix.jpeg)


<details> 
  <summary>Solution</summary> 
  
```swift 
```
  
</details> 

***
