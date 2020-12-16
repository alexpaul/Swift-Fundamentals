# Swift Fundamentals

Swift fundamentals with exercises.

> Attention developer: Please read the Swift Language Guide on a topic or watch the YouTube complimentary video before going onto the `Exercises` section below.

# [YouTube Playlist - Swift Fundamentals](https://www.youtube.com/watch?v=B77J3WIhDAw&list=PLjdVqs-1R8wHFc6iVGkXJgEZ6BRW-S3L_)

# Table of Contents 

## 1. [The Basics](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html)

   ```swift 
   let swiftIntroduced = "2014"
   ```
   
   #### Glossary
   
   * Type Safety
   * Variables 
   * Constants 
   * Type Annotation 
   * Type Inference 
   * String 
   * Int 
   * Float
   * Double 
   * Boolean 
   * Tuples
   * Optionals 
   * Optional Binding 
   * nil-coalescing
   
## 2. [Basic Operators](https://docs.swift.org/swift-book/LanguageGuide/BasicOperators.html)

   ```swift 
   9 % 4 // 1 
   ```
   
   #### Glossary 
   
   * Arithmetic operators: `+, *, -, /`
   * Remainder or modulo operator `%` 
   * Ternary operator `(condition) ? :`
   * Unary operator 
   * Binary operator 
   * Assignment opeator
   * Compound statements 
   * Comparison operators `>, <, <=, >=, ==, !=`
   * Closed-range 
   * Half-open range 
   * One-sided range 
   * Logical operators `&&, ||, !a`
   
   
## 3. [Strings and Characters](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html)

   ```swift 
   let char: Character = "🚀"
   ```
   
   #### Glossary 

   * String literal 
   * Multi-line String 
   * Special characters / escape characters 
   * Sring initialization syntax
   * Value types 
   * Character 
   * Concatenaton
   * String interpolation 
   * Unicode
   * String.Index
   * Substrings
   * Prefix and Suffix
   
## 4. [Collection Types](https://docs.swift.org/swift-book/LanguageGuide/CollectionTypes.html)

   ```swift 
   let languages = ["C", "Java", "Objective-C", "Swift", "JavaScript"]
   ```
   
     
   #### Glossary
   
   * Array
   * Iterate 
   * Dictionary
   * Set
   * enumerated()
   
## 5. [Control Flow](https://docs.swift.org/swift-book/LanguageGuide/ControlFlow.html)

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
   
     
   #### Glossary
   
   * switch 
   * control transfer statements: continue, break, fallthrough
   * labeled statements 
   * for-in loop 
   * while 
   * repeat-while 
   * iterate 
   * enumerated()
    
## 6. [Functions](https://docs.swift.org/swift-book/LanguageGuide/Functions.html)

   ```swift 
   func developerStatus() -> String {
     return "Always learning!"
   }
   ```
   
     
   #### Glossary
   
   * input 
   * output 
   * variadic parameters 
   * in-out parameters 
   * guard 
   * return 
   * parameter 
   * implicit return 
   * argument 
   
## 7. [Closures](https://docs.swift.org/swift-book/LanguageGuide/Closures.html)

   ```swift 
   let add: (Int, Int) -> Int = { $0 + $1 }
   add(12, 7) // 19
   ```
   
     
   #### Glossary
   
   * trailing closure syntax 
   * shorthand-syntax
   * capturing values 
   * reference type 
   * @escaping closure 
   * implicit return 
   * multiple trailing closures 

   
## 8. [Enumerations](https://docs.swift.org/swift-book/LanguageGuide/Enumerations.html)

   ```swift 
   enum AppError: Error {
     case decodingError(Error) 
     case badURL(String)
     case badStatusCode(String)
   }
   ```
   
## 9. [Structures and Classes](https://docs.swift.org/swift-book/LanguageGuide/ClassesAndStructures.html)

   ```swift 
   struct Venue {
     let address: String 
     let name: String 
     let latitude: Double
     let longitude: Double
   }
   
   class Person {
     let name: String 
     let age: Int
     init(name: String, age: Int) {
       self.name = name 
       self.age = age
     }
   }
   
   class Fellow: Person {
     // inherits all properies and methods of the Person parent class    
   }
   ```

## Exercises

Complete the exercise in Swift Playground or an online IDE like [repl.it](https://repl.it) . 

1. [The Basics, Basic Operators](https://github.com/alexpaul/Swift-Fundamentals/blob/main/The-Basics-Basic-Operators-Exercises.md)
1. [Strings and Characters](https://github.com/alexpaul/Swift-Fundamentals/blob/main/Strings-and-Characters-Exercises.md)
1. [Collection Types - Arrays](https://github.com/alexpaul/Swift-Fundamentals/blob/main/Collection-Types-Arrays.md)
1. [Collection Types - Dictionaries](https://github.com/alexpaul/Swift-Fundamentals/blob/main/Collection-Types-Dictionaries.md)
1. [Collection Types - Sets](https://github.com/alexpaul/Swift-Fundamentals/blob/main/Collection-Types-Sets.md)
1. [Control Flow](https://github.com/alexpaul/Swift-Fundamentals/blob/main/Control-Flow.md)
1. [Optionals](https://github.com/alexpaul/Swift-Fundamentals/blob/main/Optionals.md)
1. [Functions](https://github.com/alexpaul/Swift-Fundamentals/blob/main/Functions.md)
1. [Closures](https://github.com/alexpaul/Swift-Fundamentals/blob/main/Closures.md)


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
