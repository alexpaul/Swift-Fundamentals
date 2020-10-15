# The Basics. Basic Operators. Exercises

## 1. Variable Declarations


Which of the following variables/constants are declared correctly?  Select all that apply.

```swift
a. let nameOfPrincipal: Character = "Mrs. Watkins"

b. var temperatureOutside: Int = 90.7

c. var isSummer: String = false

d. let whiteHouseAddress: Int + String = 1600 + "Pennsylvania Ave"

e. var peopleAtParty: Double = "95"
```

<details> 
  <summary>Solution</summary>
  
a. error - "Mrs. Watkins" is a String type and not a Character  
b. error - 90.7 is a Double and not an Int  
c. error - false is a Bool value and not a String   
d. error - syntax error Int + String is error  
e. error - "95" is a String and not a Double  

</details>

***
## 2. Boolean Evaluations 1

Which of the following expressions evaluate to true?

```swift
a. !(4 + 3 < 2 * 4)

b. !(1 + 1 != 2) && !(3 >= 3)

c. (3 < 2 || (0 < 1 && 3 >= 3)) && true

d. !!(!!true && !!false)

e. true && (true && (true && (true || false)))
```

<details>
  <summary>Solution</summary>
 
```swift
 a. !(4 + 3 < 2 * 4) - answer is false

 b. !(1 + 1 != 2) && !(3 >= 3) - answer is false

 c. (3 < 2 || (0 < 1 && 3 >= 3)) && true - answer is true

 d. !!(!!true && !!false) - error

 e. true && (true && (true && (true || false))) answer is true
```
 
</details>

***

## 3. Sum

You are given two variables a and b, compute their sum, store it in a variable named sum, then print the result.

```swift

Example 1
Input:
var a = 1
var b = 2

Expected values:
sum = 3

Output: 
3

Example 2
Input:
var a = 13
var b = 22

Expected values: 
sum = 35

Output:
35
```

<details>
  <summary>Solution</summary>
 
```swift
 var a = 1
 var b = 2
 var sum = a + b
 print(sum) // 3

 a = 13
 b = 22
 sum = a + b
 print(sum) // 35
```
 
</details>

***
## 4. Seconds in Year

Determine the number of seconds in a year and store the number in a variable named secondsInAYear.

```swift
Hint:
The number of seconds in a year is 365 times the number of seconds in a day.
The number of seconds in a day is 24 times the number of seconds in a hour.
The number of seconds in a hour is 60 times the number of seconds in a minute, which is 60.
```

<details>
  <summary>Solution</summary>
 
```swift
 let secondsInAYear = 365 * (24 * (60 * 60))
 print(secondsInAYear) // 31536000
```
 
</details>

***
## 5. Number of Pixels

Your are given the width and height of a screen in pixels. Calculate the total number of pixels on the screen and store the result in a variable named numberOfPixels.

```swift
var width = 1920 
var height = 1080

Example 1
Input: 
var width = 4
var height = 3

Expected values:
numberOfPixels = 12

Example 2
Input:
var width = 1920
var height = 1080

Expected values:
numberOfPixels = 2073600

Hint:
Consider a 5x3 screen like this:
*****
*****
*****

The number of pixels on this screen is 5+5+5 = 5*3
```

<details>
  <summary>Solution</summary>
 
```swift
 var width = 4
 var height = 3
 var numberOfPixels = width * height
 print(numberOfPixels) // 12

 width = 1920
 height = 1080
 numberOfPixels = width * height
 print(numberOfPixels) // 2073600
```
 
</details>

***
## 6. Sum and Difference

You are given the sum and the difference of two numbers. Find out the values of the original numbers and store them in variables a and b.

```swift
var sum = 16 // a + b 
var diff = 4 // a - b

Example 1
Input: 
var sum = 16 
var dif = 4

Expected values:
a = 10
b = 6

Example 2
Input:
var sum = 2 
var dif = 0

Expected values:
a = 1
b = 1

Hint:
sum + diff = a + a + b - b
sum + diff = 2 * a
```

<details>
  <summary>Solution</summary>
 
```swift
 var sum = 16
 var diff = 4

 //sum + diff = 2 * a
 var a = (sum + diff) / 2
 print(a) // 10

 // sum = a + b
 var b = sum - a
 print(b) // 6

 sum = 2
 diff = 0
 a = (sum + diff) / 2
 print(a) // 1

 b = sum - a
 print(b) // 1
```
 
</details>

***
## 7. Swap Values

Given two variable a and b, swap their values. That is the new value of a will become the old value of b and vice versa.

```swift
var a = 1
var b = 2

Example 1
Input: 
a = 2
b = 1

Hint:
Just assigning a to the value of b and b to the value of a will not work.

var a = 1
var b = 2

a = b // a will have the value 2. The original value of a is lost
b = a // b will remain the same
```

<details>
  <summary>Solution</summary>
 
```swift
 var a = 1
 var b = 2

 let temp = a
 a = b
 b = temp

 print(a) // 2
 print(b) // 1
```
 
</details>

***
## 8. Find last number

You are given a number a. Print the last digit of a.

```swift
var a = 123

Example 1
Input: 
var a = 123

Output:
3

Example 2
Input: 
var a = 337

Output:
7

Hint:
Use the remainder % operator.
```

<details>
  <summary>Solution</summary>
 
```swift
 var lastDigit = 123
 while lastDigit > 10 {
   lastDigit %= 10
 }
 print(lastDigit) // 3

 lastDigit = 337
 while lastDigit > 10 {
   lastDigit %= 10
 }
 print(lastDigit) // 7
```
 
</details>

***
## 9. Dog Years

You are given Rocky’s age in dog years. Print Rocky’s age in human years. You know that 1 human year is 7 dog years.

```swift

Example 1
Input: 
var rockysAgeInDogYears = 50

Output:
7

```

<details>
  <summary>Solution</summary>
 
```swift
 var rockysAgeInDogYears = 50
 print(rockysAgeInDogYears / 7) // 7
```
 
</details>

***
## 10. Alice's Age

x years from now Alice will be y times older than her brother Bob. Bob is 12 years old. How old is Alice?

```swift
var x = 3
var y = 2
var bob = 12

var alice = ?

Example 1
Input: 
var x = 3
var y = 2
var bob = 12

Expected values: 
alice = 27

Example 2
Input: 
var x = 1
var y = 3
var bob = 12

Expected values: 
alice = 38

Hint:
alice + x = y * (bob + x)
Solve for alice

```

<details>
  <summary>Solution</summary>
 
```swift
 var bob = 12
 var x = 3
 var y = 2
 var alice = y * (bob + x) - x
 print(alice) // 27

 bob = 12
 x = 1
 y = 3
 alice = y * (bob + x) - x
 print(alice) // 38
```
 
</details>

***
## 11. Trading Oranges for Apples

You have x apples. Bob trades 3 oranges for 5 apples. He does not accept trades with cut fruit. How many oranges can you get from Bob and how many apples will you have left? The number of apples you will have left should be stored in a variable named apples. The number of oranges you will have after the trade should be stored in a variable named oranges.

```swift
var x = 17

Example 1
Input: 
var x = 17

Expected values: 
apples = 2
oranges = 9

Example 2
Input: 
var x = 25

Expected values: 
apples = 0
oranges = 15

Hint:
Use the division(/) and the remainder(%) operator

```

<details>
  <summary>Solution</summary>

```swift
 var x = 17
 var applesUsed = 0

 var apples = x % 5 // 2 apples left
 var oranges = (x / 5 ) * 3 // 9 oranges acquired from trade

 x = 25
 applesUsed = 0

 apples = x % 5 // 0
 oranges = (x / 5 ) * 3 // 15
```

</details>

***
## 12. Boy and Girl Percentages

A class consists of `numberOfBoys` boys and `numberOfGirls` girls.

Print the percentage of boys in the class followed by the percentage of girls in the class. 
The percentage should be printed rounded down to the nearest integer. For example 33.333333333333 will be printed as 33.

```swift
var numberOfBoys = 20
var numberOfGirls = 60

Example 1
Input: 
var numberOfBoys = 20  
var numberOfGirls = 60

Output:
25 // percentage of boys
75 // percentage of girls

```

<details>
  <summary>Solution</summary>

```swift
 let boys = 60
 let girls = 20
 let total = boys + girls
 let percentageBoys = (boys * 100) / total
 let percentageGirls = (girls * 100) / total

 print(percentageBoys)
 print(percentageGirls)
```

</details>

***
## 13. Boolean Evaluations 2

Which of the following expressions evaluate to true?

```swift
a. false || true
b. false && true
c. !false
d. !!!true
e. !(true && true)

```

<details>
  <summary>Solution</summary>

```swift
 a. false || true - evaluates to true
 b. false && true - evaluates to false
 c. !false - evaluates to true
 d. !!!true - error
 e. !(true && true) - evaluates to false
```

</details>

***
## 14. Boolean Evaluations 3

Which of the following expressions evaluate to true?

```swift
a. 9 == 2
b. "Hello!" == "Hello!"
c. 19.0 >= 19.0
d. 9 > 7 && 7 < 10

```

<details>
  <summary>Solution</summary>

```swift
 a. 9 == 2 - evaluates to false
 b. "Hello!" == "Hello!" - evaluates to true
 c. 19.0 >= 19.0 - evaluates to true
 d. 9 > 7 && 7 < 10 - evaluates to true
```

</details>

## 15. Class Average

You are given three grades obtained by 3 students, which are stored in variables `grade1`, `grade2`, `grade3` and all of type `Double`.
Create a variable called `yourGrade` of type `Double` and give it a value.
Print `"above average"` if your grade is greater than the class average or `"below average"` otherwise.

```swift
var grade1 = 7.0
var grade2 = 9.0
var grade3 = 5.0
```

<details>
  <summary>Solution</summary>

```swift
 var grade1 = 7.0
 var grade2 = 9.0
 var grade3 = 5.0
 var youGrade = 8.0

 let classAverage = (grade1 + grade2 + grade3 + youGrade) / 4

 print("Class average is \(classAverage)")

 if youGrade > classAverage {
   print("above average")
 } else {
   print("below average")
 }
```

</details>

***
## 16. Even or Odd

You are given a number. Print even if the number is even or odd otherwise.

```swift
let number = 2
```

<details>
  <summary>Solution</summary>

```swift
let number = 2

if number % 2 == 0 {
  print("even") // even 
} else {
  print("odd")
}
```

</details>

***
