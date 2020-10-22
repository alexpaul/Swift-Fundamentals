# Strings and Characters Exercises 

## Question 1

Write code that prints out all the numbers from 1 to 10 as a single string.

<details>
 <summary>Solution</summary>
 
```swift 
var str = ""
for num in 1...10 {
  str += "\(num)"
}
print(str) // 12345678910
```
 
</details>

***

## Question 2

Write code that prints out all the even numbers from 5 to 51 as a single string.

<details>
 <summary>Solution</summary>
 
```swift 
var str = ""
for num in 5...51 where num % 2 == 0 {
  str += "\(num) "
}
print(str)
// 6 8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38 40 42 44 46 48 50
```
 
</details>

***

## Question 3

Write code that prints out every number ending in 4 between 1 and 60 as a single string.

<details>
 <summary>Solution</summary>
 
```swift 
var str = ""
for num in 1...60 where num % 10 == 4 {
  str += "\(num) "
}
print(str)
// 4 14 24 34 44 54
```
 
</details>

***

## Question 4

Print each character in the string `"Hello world!"`

<details>
 <summary>Solution</summary>
 
```swift 
let str = "Hello world!"
for char in str {
  print(char)
}
/*
 H
 e
 l
 l
 o
  
 w
 o
 r
 l
 d
 !
*/
```
 
</details>

***

## Question 5

Print out the last character in the string below. You cannot use the Character literal "!" (i.e you must access `myStringSeven`'s characters).

`let myStringSeven = "Hello world!"`

<details>
 <summary>Solution</summary>
 
```swift 
let myStringSeven = "Hello world!"

let lastCharIndex = myStringSeven.index(before: myStringSeven.endIndex)
print(myStringSeven[lastCharIndex]) // !
```
 
</details>

***

## Question 6

You are given a string stored in the variable `aString`. Create new string named `replacedString` that contains the characters of the original string with all the occurrences of the character `"e"` replaced by `"*"`.

```swift
var aString = "Replace the letter e with *"
// Your code here
 ```

Example:

Input:
`let aString = "Replace the letter e with *"`

Expected values:
`replacedString = "R*plac* th* l*tt*r * with *"`

<details>
 <summary>Solution</summary>
 
```swift 
let aString = "Replace the letter e with *"

var replacedString = ""
for char in aString {
  if char == "e" {
    replacedString += "*"
    continue
  }
  replacedString.append(char)
}

print(replacedString) // R*plac* th* l*tt*r * with *
```
 
</details>

***
## Question 7

You are given a string stored in variable `aString`. Create a new string called `reverse` that contains the original string in reverse order. Print the reversed string. You cannot used built-in reverse. 

```swift
let aString = "this string has 29 characters"
var reverse = ""

// Your code here
```

Example:
Input:
`let aString = "Hello"`

Output:
`"olleH"`

<details>
 <summary>Solution</summary>
 
```swift 
let aString = "Hello"
var reverse = ""
for char in aString {
  reverse = String(char) + reverse
}
print(reverse) // olleH
```
 
</details>


## Question 8

You are given a string stored in variable `aString`. Print `true` if `aString` is a palindrome, and `false` otherwise. A **palindrome** is a string which reads the same backward or forward.

```swift
let str1 = "anutforajaroftuna"

// Your code here
```

Example 1:
Input:
`let str1 = "anutforajaroftuna"`

Output:
`true`

Example 2:
Input:
`let str2 = "Hello"`

Output:
`false`

<details>
 <summary>Solution</summary>
 
```swift 
let str1 = "anutforajaroftuna"
let str2 = "Hello"
var reverse = ""

for char in str1 {
  reverse = String(char) + reverse
}

print(reverse == str1) // true
```
 
</details>

***
## Question 9

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

```swift
let problem = "split this string into words and print them on separate lines"

// Your code
```

Example:
Input:
`let problem ="split this string into words and print them on separate lines"`

Output:
```swift
split
this
string
into
words
and
print
them
on
separate
lines
```

<details>
 <summary>Solution</summary>
 
```swift 
let problem = "split this string into words and print them on separate lines"

let words = problem.split(separator: " ")

for word in words {
  print(word)
}

/*
 split
 this
 string
 into
 words
 and
 print
 them
 on
 separate
 lines
*/
```
 
</details>

***
## Question 10

You are given a string stored in variable `problem`. Write code that prints the longest word in the string.

```swift
let problem = "find the longest word in the problem description"

// Your code here
```

Example:
Input:
`let problem = "find the longest word in the problem description"`

Output:
`description`

Hint: Keep track of the longest word you encounter and also keep track of its length.

<details>
 <summary>Solution</summary>
 
```swift
let problem = "find the longest word in the problem description"
let words = problem.split(separator: " ")
var largestWord = ""

for word in words {
  if word.count > largestWord.count {
    largestWord = String(word)
  }
}

print(largestWord) // description
```
 
</details>

***
## Question 11

Given a string in English, create a tuple containing the number of vowels and consonants.

```swift
let vowels = "aeiou"
let consonants = "bcdfghjklmnpqrstvwxyz"
let input = "Count how many vowels I have!"
```

<details>
 <summary>Solution</summary>
 
```swift 
let vowels = Set("aeiou")
let consonants = Set("bcdfghjklmnpqrstvwxyz")
let input = "Count how many vowels I have!"

var vowelsConsonantsCount: (vowels: Int, consonants: Int) = (0, 0)

for char in input.lowercased() {
  if vowels.contains(char) {
    vowelsConsonantsCount.vowels += 1
    continue
  }
  if consonants.contains(char) {
    vowelsConsonantsCount.consonants += 1
  }
}

print(vowelsConsonantsCount)
// (vowels: 8, consonants: 13)
```
 
</details>

***
## Question 12

Given a string of words separated by a `" "`. Write code that prints out the length of the last word.

If there is no last word print out `"No last word"`.

Example:
Input: `"How are you doing this Monday?"`

Output: `7`

<details>
 <summary>Solution</summary>
 
```swift 
let str = "How are you doing this Monday?"

let words = str.split(separator: " ")

if let lastWord = words.last {
  print(lastWord.count) // 7
} else {
  print("No last word")
}
```
 
</details>

***

## Question 13

Given a string `testString` create a new variable called `condensedString` that has any consecutive spaces in `testString` replaced with a single space.

```swift
let testString = "  How   about      thesespaces  ?  "
var condensedString = ""

// Output: " How about thesespaces ? "
```

<details>
 <summary>Solution</summary>
 
```swift 
let testString = "  How   about      thesespaces  ?  "

var condensedString = ""
var previousChar: Character = "*"

for char in testString {
  if previousChar == " " && char == " " {
    continue
  }
  condensedString.append(char)
  previousChar = char
}

print(condensedString) // " How about thesespaces ? "
```
 
</details>

***
## Question 14

Given a string with multiple words. Reverse the string word by word. You cannot use built-in `reverese` or `swapAt`.

Example:

Sample Input: `"Swift is the best language"`

Sample Output: `"language best the is Swift"`

<details>
 <summary>Solution</summary>
 
```swift 
let str = "Swift is the best language"

var words = str.split(separator: " ")

var reverseWords = [String]()

for (index, _) in words.enumerated() where index < words.count / 2 {
  let temp = words[index]
  words[index] = words[words.count - 1 - index]
  words[words.count - 1 - index] = temp
}

print(words.joined(separator: " ")) // language best the is Swift
```
 
</details>

***
## Question 15

Given a string with multiple words. Write code that prints how many of them are palindromes.

Note: Feel free to use functions if you are already familiar with them. 

Example:

Sample Input: `"danaerys dad cat civic bottle"`

Sample Output: `2`

<details>
 <summary>Solution</summary>
 
```swift 
func isPalindrome(_ inputStr: String) -> Bool {
  var reverse = ""
  for char in inputStr {
    reverse = String(char) + reverse
  }
  return reverse == inputStr
}

let str = "danaerys dad cat civic bottle"
let words = str.split(separator: " ")
var palindromeCount = 0

for word in words {
  if isPalindrome(String(word)) {
    palindromeCount += 1
  }
}

print(palindromeCount) // 2

```
 
</details>

***
## Question 16

You are given a string representing an **attendance record** for a student. The record only contains the following three characters:

`'A' : Absent.`

`'L' : Late.`

`'P' : Present.`

If a student has more than one 'A' or more than 2 continuous 'L's that student should not be rewarded. Print true if student is to be rewarded and False if they shouldn't.

Example:

Sample Input: `"PPALLP"`

Sample Output: `true`

<details>
 <summary>Solution</summary>
 
#### Solution 1

```swift 
let attendance = "PPALLP"

var absentCount = 0, lateCount = 0
var previousChar: Character = "*"
var isRewarded = true
for char in attendance {
  if char == "A" {
    absentCount += 1
    if absentCount > 1 {
      isRewarded = false
      break
    }
  }
  if char == "L" {
    lateCount += 1
    if previousChar == "L" {
      if lateCount > 2 {
        isRewarded = false
        break
      }
    }
  } else {
    lateCount = 0
  }
  previousChar = char
}

print(isRewarded) // true
```

#### Solution 2 

```swift
func awardAttendance(_ str: String) -> Bool {
  if str.contains("LLL") || (str.filter { $0 == "A" }.count > 1) {
    return false
  }
  return true
}
```
 
</details>

***
## Question 17

Given a tuple with two strings. The first string is a **ransom note**, the second string being the characters from a magazine. Determine whether or not you can construct the ransom note using the characters from the magazine.

Each letter from the magazine can only be used once. You can assume all letters are lowercased.

Examples:

Sample Input1: `("a", "b")`

Sample Output1: `False`

Sample Input2: `("aa", "aab")`

Sample Output2: `True`

<details>
 <summary>Solution</summary>
 
```swift 
let note: (ransomNote: String, magazine: String) = ("aa", "aab")
var magazine = note.magazine
var canCreateRansomNote = true

for char in note.ransomNote {
  if magazine.contains(char) {
    if let index = magazine.firstIndex(of: char) {
      magazine.remove(at: index)
    }
  } else {
    canCreateRansomNote = false
    break
  }
}

print(canCreateRansomNote) // true
```
 
</details>

***
