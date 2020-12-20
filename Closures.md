# Closure Exercises 

## Question One
Write a function named `applyKTimes` that takes an integer `K` and a closure and calls the closure K times. The closure will not take any parameters and will not have a return value.

```swift 
// input: applyKTimes(5)
// output: 5
```

```swift 
// Your function here

var myVal = 0
applyKTimes(5) {
  myVal += 1
}

print(myVal) // 5
```

<details> 
  <summay>Solution</summary> 
  
```swift 
func applyKTimes(_ k: Int, closure: () -> ()) {
  for _ in 0..<k {
    closure()
  }
}

var myVal = 0
applyKTimes(5) {
  myVal += 1
}

print(myVal) // 5
```
</details> 

***

## Question Two
Write a function called `multiples(of:in)` that takes in an array of `Int`s and returns all of the `Int`s that are a multiple of a given number n.  Use `filter` in your function.

```swift 
// input: [1, 2, 3, 4, 6, 8, 9, 3, 12, 11], n = 3
// output: [3, 6, 9, 3, 12]
```

```swift 
// Your function here

let numbers = [1, 2, 3, 4, 6, 8, 9, 3, 12, 11]
```
<details> 
  <summay>Solution</summary> 
  
```swift 
func multiples(of num: Int, in numbers: [Int]) -> [Int] {
  numbers.filter { $0 % 3 == 0 }
}

let numbers = [1, 2, 3, 4, 6, 8, 9, 3, 12, 11]

print(multiples(of: 3, in: numbers)) // [3, 6, 9, 3, 12]
```
</details> 

***

## Question Three

Write a function called `largestValue(in:)` that finds the largest `Int` in an array of `Int`s. Use `reduce` to solve this exercise.

```swift 
// input: [4, 7, 1, 9, 6, 5, 6, 9]
// output: 9
```

```swift 
// Your function here

let moreNumbers = [4, 7, 1, 9, 6, 5, 6, 9]
```

Longer form solution 

<details> 
  <summay>Solution</summary> 
  
```swift 
func largestValue(in numbers: [Int]) -> Int {
  guard !numbers.isEmpty else { return -1 }
  let result = numbers.reduce(Int.min) { (previousResult, currentValue) -> Int in
    if previousResult > currentValue {
      return previousResult
    }
    return currentValue
  }
  return result
}

let moreNumbers = [4, 7, 1, 9, 6, 5, 6, 9]

print(largestValue(in: moreNumbers)) // 9
```
</details> 

Shorthand syntax Solution

<details> 
  <summay>Solution</summary> 
  
```swift 
func largestValue(in numbers: [Int]) -> Int {
  return arr.reduce(0) { return $0 > $1 ? $0 : $1 }  
}

let moreNumbers = [4, 7, 1, 9, 6, 5, 6, 9]

print(largestValue(in: moreNumbers)) // 9
```
</details> 

***

## Question Four

Write a function called `sortedNamesByLastName(in:)` that takes in an array of tuples of type `(String, String)` and returns an array of tuples sorted `ascending` by last name.

```swift 
// input: 
let firstAndLastTuples = [
    ("Johann S.", "Bach"),
    ("Claudio", "Monteverdi"),
    ("Duke", "Ellington"),
    ("W. A.", "Mozart"),
    ("Nicolai","Rimsky-Korsakov"),
    ("Scott","Joplin"),
    ("Josquin","Des Prez")
]

// output: 
/*
 (firstName: "Johann S.", lastName: "Bach")
 (firstName: "Josquin", lastName: "Des Prez")
 (firstName: "Duke", lastName: "Ellington")
 (firstName: "Scott", lastName: "Joplin")
 (firstName: "Claudio", lastName: "Monteverdi")
 (firstName: "W. A.", lastName: "Mozart")
 (firstName: "Nicolai", lastName: "Rimsky-Korsakov")
*/

```

```swift 
// Your function here

let firstAndLastTuples = [
    ("Johann S.", "Bach"),
    ("Claudio", "Monteverdi"),
    ("Duke", "Ellington"),
    ("W. A.", "Mozart"),
    ("Nicolai","Rimsky-Korsakov"),
    ("Scott","Joplin"),
    ("Josquin","Des Prez")
]
```

<details> 
  <summay>Solution</summary> 
  
```swift 
func sortedNamesByLastName(in names: [(firstName: String, lastName: String)]) -> [(firstName: String, lastName: String)] {
  let sortedNames = names.sorted { (name1, name2) -> Bool in
    return name1.lastName < name2.lastName
  }
  return sortedNames
}

let firstAndLastTuples = [
    ("Johann S.", "Bach"),
    ("Claudio", "Monteverdi"),
    ("Duke", "Ellington"),
    ("W. A.", "Mozart"),
    ("Nicolai","Rimsky-Korsakov"),
    ("Scott","Joplin"),
    ("Josquin","Des Prez")
]

let sortedNames = sortedNamesByLastName(in: firstAndLastTuples)
sortedNames.forEach { print($0) }

/*
 (firstName: "Johann S.", lastName: "Bach")
 (firstName: "Josquin", lastName: "Des Prez")
 (firstName: "Duke", lastName: "Ellington")
 (firstName: "Scott", lastName: "Joplin")
 (firstName: "Claudio", lastName: "Monteverdi")
 (firstName: "W. A.", lastName: "Mozart")
 (firstName: "Nicolai", lastName: "Rimsky-Korsakov")
*/
```

</details> 

***

## Question Five

Write a function called `sumOfSquaresOfOddNumbers(in:)` that returns the sum of the squares of all the odd numbers from an array of `Int`s.  Use `filter`, `map` and `reduce` in your function.

```swift 
// input: [1, 2, 3, 4, 5, 6]

// output: 35
```

```swift 
// Your function here

let evenMoreNumbers = [1, 2, 3, 4, 5, 6]
```

<details> 
  <summay>Solution</summary> 
  
```swift 
func sumOfSquaresOfOddNumbers(in numnbers: [Int]) -> Int {
  numnbers.map { $0 * $0 }
    .filter { $0 % 2 == 1 }
    .reduce(0, +)
}

let evenMoreNumbers = [1, 2, 3, 4, 5, 6]

let sum = sumOfSquaresOfOddNumbers(in: evenMoreNumbers)

print(sum) // 35
```
</details> 

***

## Quesiton 6 

Rewrite the built-in implementation of the `map` function.  
Review: `map` takes in an array of elements and performs a transformation on each element and returns a resulting array.

>Make it generic so it can works with any type. 

```swift 
// input: [1, 2, 3, 4] , square each element

// output: [1, 4, 9, 16]
```

```swift 
// input: ["ALEX", "KIM", "SAM", "TOM", "RACHEL"], lowercase each String

// output: ["alex", "kim", "sam", "tom", "rachel"]
```

<details> 
  <summary>Solution</summary> 

```swift 
func customMap<T>(_ elements: [T], closure: (T) -> T) -> [T] {
  var transforemdArray = [T]()
  for element in elements {
    transforemdArray.append(closure(element))
  }
  return transforemdArray
}

let tranformation = customMap([1, 2, 3, 4]) { (value) -> Int in
  return value * value
}

print(tranformation) // [1, 4, 9, 16]

let shorthandSyntaxTransformation = customMap([1, 2, 3, 4]) { $0 * $0 }
print(shorthandSyntaxTransformation) // [1, 4, 9, 16]
```

</details> 
