# Functions Exercises

## Question 1.

Write a function named `doubleNumber(_:)` that takes in a `Double` and returns that number times two

```swift
//Your function here

// input: 99 
// output: 198

// input: 3.0
// output: 6.0
```

<details> 
    <summary>Solution</summary> 
    
```swift 
func double(_ number: Double) -> Double {
  return number * 2
}

print(double(99)) // 198.0
```

</details> 

***

## Question 2.

Write a function named `smallest(of:and:)` that takes in two `Double`s and returns the smaller number. Don't use the built-in `max()` function. 

```swift 
// input: 2.3, 2.03
// output: 2.03

// input: 8.0, 3.0
// output: 3.0
```

```swift
// Your function here

```

<details> 
    <summary>Solution</summary> 
    
```swift 
func smallest(of num1: Double, and num2: Double) -> Double {
  let result = num1 < num2 ? num1 : num2
  return result
}

print(smallest(of: 2.3, and: 2.03)) // 2.03
print(smallest(of: 8.0, and: 3.0)) // 3.0
```

</details> 

***

## Question 3.

Write a function named `smallestValue(in:)` that takes in an array of `Double`s and returns the smallest `Double`. Don't use `.min()`

```swift 
// input: [1.0,2,3,4,5,5]
// output: 1.0

// input: [-4,-59,-348,-34,-4]
// output: -348
```

<details> 
    <summary>Solution</summary> 
    
```swift 
func smallestValue(in arr: [Double])  -> Double {
  guard var smallest = arr.first else { return 0 }
  for num in arr {
    if num < smallest {
      smallest = num
    }
  }
  return smallest
}

print(smallestValue(in: [1.0,2,3,4,5,5])) // 1.0
print(smallestValue(in: [-4,-59,-348,-34,-4])) // -348
```

</details> 

***

## Question 4.

Write a function named `occurrences(of:in:)` that counts how many `Character`s in a `String` match a specific character.

```swift 
// input: "hello", "l"
// output: 2 

// input: "Now with some spaces", " "
// output: 3
```

<details> 
    <summary>Solution</summary> 
    
```swift 
func occurrences(of char: Character, in str: String) -> Int {
  let characters = str.filter { $0 == char }
  return characters.count
}

print(occurrences(of: "l", in: "hello")) // 2
print(occurrences(of: " ", in: "Now with some spaces")) // 3
```

</details> 

***

## Question 5.

Write a function called `removeNils(from:)` that takes an array of optional `Int`s and returns an array with them unwrapped with any nil values removed.

```swift 
// input: [1, nil, 9, nil, 10, nil]
// output: [1, 9, 10]

// input: [1, 2, 3]
// output: [1, 2, 3]

// input: [nil]
// output: []

// input: []
// output: []
```

```swift
// Your function here
```

<details> 
    <summary>Solution</summary> 
    
```swift 
func removeNils(from arr: [Int?]) -> [Int] {
  let results = arr.compactMap { $0 }
  return results
}

print(removeNils(from: [1, nil, 9, nil, 10, nil])) // [1, 9, 10]
print(removeNils(from: [1, 2, 3])) // [1, 2, 3]
print(removeNils(from: [nil])) // []
print(removeNils(from: [])) // []
```

</details> 

***

## Question 6.

Write a function named `average(of:)` that returns the average of an array of `Double`s. 

```swift 
// input: [1,2,3,4,5]
// output: 3

// input: [1.5, 2.25, 4.5, -1.5]
// output: 1.6875
```

<details> 
    <summary>Solution</summary> 
    
```swift 
func average(of numbers: [Double]) -> Double {
  let results = numbers.reduce(0.0, +)
  return results / Double(numbers.count)
}

print(average(of: [1,2,3,4,5])) // 3
print(average(of: [1.5, 2.25, 4.5, -1.5])) // 1.6875
```

</details> 

***

## Question 7.

Write a function named `frequencyDictionary(of:)` that takes a `String` as input and returns a dictionary that maps each `Character` to its number of occurrances. 

```swift 
// input: "hello"
// output: ["h": 1, "e": 1, "l": 2, "o": 1]

// input: "aaaaaAAA"
// output: ["a": 5, "A":3]

// input: "More words"
// output: ["M": 1, "o": 2, "r": 2, "e": 1, " ": 1, "w": 1, "d": 1, "s": 1]
```

<details> 
    <summary>Solution</summary> 
    
```swift 
func frequencyDictionary(of str: String) -> [Character: Int] {
  var dict = [Character: Int]()
  for char in str {
    if let count = dict[char] {
      dict[char] = count + 1
    } else {
      dict[char] = 1
    }
  }
  return dict
}

print(frequencyDictionary(of: "hello")) // ["o": 1, "l": 2, "e": 1, "h": 1]
print(frequencyDictionary(of: "aaaaaAAA")) // ["a": 5, "A": 3]
print(frequencyDictionary(of: "More words")) // ["o": 2, " ": 1, "w": 1, "d": 1, "M": 1, "r": 2, "e": 1, "s": 1]
```

</details> 

***

## Question 8.

Write a function named `value(_:isGreaterThanAverageOf:)` that takes in an array of `Double`s and a `Double` and returns whether the `Double` is greater than the average.

```swift 
// input: 4.0, [1.0,2,3,4,5]
// output: true 

// input: 3, [1,2,3,4,5]
// output: false 

// input: 100.8, [1,42,1,541,42,5]
// output: false 
```

```swift
// Your function here
```

<details> 
    <summary>Solution</summary> 
    
```swift 
func value(_ num: Double, isGreaterThanAverageOf numbers: [Double]) -> Bool {
  let average = numbers.reduce(0.0, +) / Double(numbers.count)
  let result = num > average ? true : false
  return result
}

print(value(4.0, isGreaterThanAverageOf: [1.0,2,3,4,5])) // true
print(value(3, isGreaterThanAverageOf: [1,2,3,4,5])) // false
print(value(100.8, isGreaterThanAverageOf: [1,42,1,541,42,5])) // false
```

</details> 

*** 

## Question 9.

Write a function that finds the second smallest Int an an array of Ints

```swift 
// input: [1, 2, 3, 4]
// output: 2

// input: [2, 1, 3, 4]
// output: 2
```

```swift
// Your function here
```

<details> 
    <summary>Solution</summary> 
    
```swift 
func secondSmallest(of numbers: [Int]) -> Int {
  guard var smallest = numbers.first else { return 0 }
  var secondSmallest = Int.max
  for num in numbers {
    if num < smallest {
      secondSmallest = smallest
      smallest = num
    }
    else if num < secondSmallest && num != smallest {
      secondSmallest = num
    }
  }
  return secondSmallest
}

print(secondSmallest(of: [1, 2, 3, 4])) // 2
print(secondSmallest(of: [2, 1, 3, 4])) // 2
```

</details> 

***

## Question 10.

Write a program that outputs the string representation of numbers from 1 to n.

But for multiples of three it should output “Fizz” instead of the number and for the multiples of five output “Buzz”. For numbers which are multiples of both three and five output “FizzBuzz”.

[LeetCode - 412. Fizz Buzz](https://leetcode.com/problems/fizz-buzz/)

```swift
// Example 

/*
n = 15,

Return:
[
    "1",
    "2",
    "Fizz",
    "4",
    "Buzz",
    "Fizz",
    "7",
    "8",
    "Fizz",
    "Buzz",
    "11",
    "Fizz",
    "13",
    "14",
    "FizzBuzz"
]
*/
```

<details> 
    <summary>Solution</summary> 
    
```swift 
func fizzBuzz(_ n: Int) -> [String] {
  var arr = [String]()
  for i in 1...n {
    if i % 3 == 0 && i % 5 == 0 {
      arr.append("FizzBuzz")
    }
    else if i % 3 == 0 {
      arr.append("Fizz")
    }
    else if i % 5 == 0 {
      arr.append("Buzz")
    }
    else {
      arr.append(i.description)
    }
  }
  return arr
} 

print(fizzBuzz(9)) // ["1", "2", "Fizz", "4", "Buzz", "Fizz", "7", "8", "Fizz"]
print(fizzBuzz(15)) // ["1", "2", "Fizz", "4", "Buzz", "Fizz", "7", "8", "Fizz", "Buzz", "11", "Fizz", "13", "14", "FizzBuzz"]
```

</details> 
