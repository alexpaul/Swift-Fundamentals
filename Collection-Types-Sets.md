# Sets Exercises 

## Question One
Create a new array `numbersWithNoDuplicates` that has all of the elements from numbers without any duplicates.  It should be in the same order as the original.

```swift 
let numbers = [1,1,2,4,4,4,6,6,7,8]

var numbersWithNoDuplicates = [Int]()

// expected output: [1, 2, 4, 6, 7, 8]

// Your code here
```

<details>
  <summary>Solution</summary>
  
```swift 
let numbers = [1,1,2,4,4,4,6,6,7,8]

var numbersWithNoDuplicates = [Int]()

var set: Set<Int> = []

for num in numbers {
  if !set.contains(num) {
    numbersWithNoDuplicates.append(num)
    set.insert(num)
  }
}

print(numbersWithNoDuplicates) // [1, 2, 4, 6, 7, 8]
```

</details>

***

## Questions Two

Create a new array `scoresThatAppearOnce` that has all the elements from scores that appear exactly once.  It should be in the same order as the original.

```swift 
let scores = [1, 77, 83, 32, 77, 77, 83, 32, 99]

var scoresThatAppearOnce = [Int]()

// expected output: [1, 99]

// Your code here

```

<details>
  <summary>Solution</summary>
  
```swift 
let scores = [1, 77, 83, 32, 77, 77, 83, 32, 99]

var scoresThatAppearOnce = [Int]()

var visited: Set<Int> = []

var freqDict = [Int: Int]()
scores.forEach { freqDict[$0, default: 0] += 1 }

for score in scores {
  if freqDict[score] == 1 {
    scoresThatAppearOnce.append(score)
  }
}

print(scoresThatAppearOnce) // [1, 99]
```

</details>

***

## Question Three

a.
Given `arrOne` and `arrTwo`, create a variable `arrThree` which is equal to the UNION of `arrOne` and `arrTwo`.  It should not contain any duplicate elements.  Sort `arrThree` from smallest to greatest.

```swift 
let arrOne = [1,2,3,4,5]
let arrTwo = [3,4,5,6,7]

var arrThree: [Int] = []

// expected output: [1, 2, 3, 4, 5, 6, 7]

// Your code here
```

<details>
  <summary>Solution</summary>
  
```swift 
let arrOne = [1,2,3,4,5]
let arrTwo = [3,4,5,6,7]

var arrThree: [Int] = []

arrThree = Array(Set(arrOne).union(Set(arrTwo))).sorted()

print(arrThree) // [1, 2, 3, 4, 5, 6, 7]
```

</details>

b.
Given `arrFour` and `arrFive`, create a variable `arrSix` with is equal to the INTERSECTION of `arrFour` and `arrFive`.  If should not contain any duplicate elements.  Sort `arrSix` from smallest to greatest.

```swift 
let arrFour = [1,2,3,4,5]
let arrFive = [3,4,5,6,7]

var arrSix: [Int] = []

// expected output: [3, 4, 5]

// Your code here
```

<details>
  <summary>Solution</summary>
  
```swift 
let arrFour = [1,2,3,4,5]
let arrFive = [3,4,5,6,7]

var arrSix: [Int] = []

arrSix = Array(Set(arrFour).intersection(Set(arrFive))).sorted()

print(arrSix) // [3, 4, 5]
```

</details>

***

## Question Four

Given the 4 arrays of Ints below, create a new array, sorted in ascending order, that contains all the values without duplicates.

```swift 
let numsOne = [2, 4, 5, 6, 8, 10, 12]
let numsTwo = [1, 2, 3, 4, 5, 6]
let numsThree = [5, 6, 7, 8, 9, 10, 11, 12]
let numsFour = [1, 3, 4, 5, 6, 7, 9]

var allNumsWithNoDuplicates: [Int] = []

// expected output: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]

// Your code here
```

<details>
  <summary>Solution</summary>
  
```swift 
let numsOne = [2, 4, 5, 6, 8, 10, 12]
let numsTwo = [1, 2, 3, 4, 5, 6]
let numsThree = [5, 6, 7, 8, 9, 10, 11, 12]
let numsFour = [1, 3, 4, 5, 6, 7, 9]

var allNumsWithNoDuplicates: [Int] = []

allNumsWithNoDuplicates = Array(Set(numsOne + numsTwo + numsThree + numsFour)).sorted()

print(allNumsWithNoDuplicates) // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]
```

</details>

***

## Question Five

Roy wanted to increase his typing speed for programming contests. His friend suggested that he type the sentence `The quick brown fox jumps over the lazy do` repeatedly. This sentence is known as a `pangram` because it contains every letter of the alphabet.

After typing the sentence several times, Roy became bored with it so he started to look for other pangrams.

Given a sentence, determine whether it is a pangram. Ignore case.

Full question on [HackerRank](https://www.hackerrank.com/challenges/pangrams/problem)

<details>
  <summary>Solution</summary>
  
```swift 
func pangrams(s: String) -> String {
  let alphabets = Set("abcdefghijklmnopqrstuvwxyz")
  let set = Set(s.replacingOccurrences(of: " ", with: "").lowercased())
  guard set.count == 26 else {
    return "not pangram"
  }
  return alphabets == set ? "pangram" : "not pangram"
}

pangrams(s: "We promptly judged antique ivory buckles for the next prize") // pangram
pangrams(s: "We promptly judged antique ivory buckles for the prize") // not pangram
```

</details>


