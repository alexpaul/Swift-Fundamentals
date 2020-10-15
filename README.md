# Swift Fundamentals

Swift fundamentals with exercises.

> Attention developer: Read the Swift Language Guide on a topic before going onto the `Exercises` section.

## Table of Contents 

1. [The Basics](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html)
   ```swift 
   let swiftIntroduced = "2014"
   ```
1. [Basic Operators](https://docs.swift.org/swift-book/LanguageGuide/BasicOperators.html)
   ```swift 
   9 % 4 // 1 
   ```
1. [Strings and Characters](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html)
   ```swift 
   let char: Character = "🚀"
   ```
1. [Collection Types](https://docs.swift.org/swift-book/LanguageGuide/CollectionTypes.html)
   ```swift 
   let languages = ["C", "Java", "Objective-C", "Swift", "JavaScript"]
   ```
1. [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html)
    ```swift
   print("Please enter a number between 1 and 20 ?")
   var input = Int(readLine() ?? "") ?? 2

   if !(1...20).contains(input) {
     input = 2 
   }

   repeat {
     print("Swift is awesome! 😎")
     input -= 1
   } while input > 0
    ```
1. [Functions](https://docs.swift.org/swift-book/LanguageGuide/Functions.html)
   ```swift 
   func developerStatus() -> String {
     return "Always learning!"
   }
   ```
1. [Closures](https://docs.swift.org/swift-book/LanguageGuide/Closures.html)
   ```swift 
   let add: (Int, Int) -> Int = { $0 + $1 }
   add(12, 7) // 19
   ```


## Exercises

Complete the exercise in Swift Playground or an online IDE like [repl.it](https://repl.it) . 

1. [The Basics, Basic Operators](https://github.com/alexpaul/Swift-Fundamentals/blob/main/The-Basics-Basic-Operators-Exercises.md)


## Projects 

To evaluate your Swift fundamentals work on any of the following projects as a command line macOS application. 

* Black Jack 
* Mad Libs Generator
* Rock, Paper, Scissors
* Tic Tac Toe 
* Hangman 
* Calculator
* Trivia Game
* Text-Based Adventure Game
