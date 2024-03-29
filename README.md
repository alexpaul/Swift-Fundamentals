# Swift Fundamentals

Swift fundamentals with exercises.

> Attention developer: Please read the Swift Language Guide on a topic or watch the YouTube complimentary video before going onto the `Exercises` section below.

<a href="https://www.buymeacoffee.com/alexpaulnyc" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174"></a>

# [YouTube Playlist - Swift Fundamentals](https://youtube.com/playlist?list=PLjdVqs-1R8wHFc6iVGkXJgEZ6BRW-S3L_)

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
   
   [Video: Swift, The Basics](https://youtu.be/wrtuio49fHM)
   
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
   
   [Video - Swift Basic Operators](https://youtu.be/Y2ThBhbc71Q)
   
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
   
   1. [Video - Strings and Characters](https://youtu.be/VTES2xGtS1s)
   2. [Strings and Characters code examples](https://repl.it/@alexpaul/StringsAndCharacters#main.swift)
   
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
   
   #### Arrays
   1. [Video - Arrays](https://youtu.be/nV8yvXoJOBo)
   2. [Arrays code examples](https://repl.it/@alexpaul/Collection-Types-Arrays#main.swift)
   
   #### Sets
   1. [Video - Sets](https://youtu.be/ug2RYDrJnuo)
   2. [Sets code examples](https://repl.it/@alexpaul/Collection-Types-Sets#main.swift)
   
   #### Dictionaries
   1. [Video - Dictionaries](https://youtu.be/Gd_de-TNAwQ)
   2. [Dictionaries code examples](https://repl.it/@alexpaul/Collection-Types-Dictionaries#main.swift)
   
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
   
   1. [Video: Control Flow](https://youtu.be/AWnnAeK18NI)
   2. [Control Flow code examples](https://repl.it/@alexpaul/Control-Flow#main.swift)
    
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
   
   1. [Video: Functions](https://youtu.be/E3lmXVUdj38)
   2. [Functions code examples](https://repl.it/@alexpaul/Functions#main.swift)
   
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
   
   1. [Video: Closures](https://youtu.be/Q0fahJeV4Zo)
   2. [Closures code examples](https://repl.it/@alexpaul/Closures#main.swift)

   
## 8. [Enumerations](https://docs.swift.org/swift-book/LanguageGuide/Enumerations.html)

   ```swift 
   enum AppError: Error {
     case decodingError(Error) 
     case badURL(String)
     case badStatusCode(String)
   }
   ```
   
   #### Glossary
   
   * `CaseIterable`
   * Associated Values
   * Raw Values 
   * Implicitly assigned Raw Values 
   
   ##### Introduction to `enums`
   1. [Video: Enumerations](https://youtu.be/XXaaYV1_d-Y)
   2. [Enums code examples](https://repl.it/@alexpaul/Enumerations#main.swift)
   
   ##### Methods and Properties in `enums`
   1. [Video: Enums - Methods and Properties](https://youtu.be/AGxEa4G0ADk)
   1. [Code examples](https://repl.it/@alexpaul/Enums-Methods-and-Properties#main.swift)

   
## 9. [Structures](https://docs.swift.org/swift-book/LanguageGuide/ClassesAndStructures.html)

   ```swift 
   struct Venue {
     let address: String 
     let name: String 
     let latitude: Double
     let longitude: Double
   }
   ```
   
   #### Glossary 
   
   * Memberwise Initializer 
   * Value type 
   * `mutating func`
   * Immutable 
   
   
## 10. [Classes](https://docs.swift.org/swift-book/LanguageGuide/ClassesAndStructures.html)

   ```swift    
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
   
   #### Glossary 
   
   * inheritance 
   * deintializers
   * reference type 
   * pointer 
   * retain cycle 
   * identity operator `===`


## 11. [Properties](https://docs.swift.org/swift-book/LanguageGuide/Properties.html)

   ```swift 
   var fullName: String {
     return firstName + " " + lastName
   }
   ```
   
   #### Glossary 
   
   * stored property 
   * computed property 
   * `lazy` property 
   * setter 
   * getter 
   * propety observer
   * property wrappers
   * Type property 
   * Instance property

## 12. [Methods](https://docs.swift.org/swift-book/LanguageGuide/Methods.html)

   Instance Method 
   ```swift 
   struct Person {
     let name: String 
     
     func info() {
       print("My name is \(name)")
     }
   }
   
   let person = Person(name: "Alex")
   person.info() // instance method
   ```
   
   Type Method
   ```swift 
   struct Person {
     let name: String 
     
     static func getRaces() -> [String] {
       return ["Black", "Asian", "White", "LatinX"]
     }
     
     func info() {
       print("My name is \(name)")
     }
   }
   
   Person.getRaces() // type method
   ```
   
   #### Glossary 
   
   * Type method 
   * Instance method 
   * `self`
   * `mutating func`
   * `@discardableResult`

## 13. [Subscripts](https://docs.swift.org/swift-book/LanguageGuide/Subscripts.html)

   ```swift 
   struct Person {
     subscript(_ address: String) -> String {
       return geocode(address)
     }
   }

   let person = Person() 
   print(person["105 Broadway, New York, NY"]) // 11249
   ```

## 14. [Inheritance](https://docs.swift.org/swift-book/LanguageGuide/Inheritance.html)

   ```swift 
   class VenueCell: UICollectionViewCell {
     // VenueCell inherits all functions and properties from its Parent class, UICollectionViewCell
   }
   ```
   
   #### Glossary 
   
   * Overriding 
   * Subclassing 
   * `final`
   * Base class 
   * Super class


## 15. [Initialization](https://docs.swift.org/swift-book/LanguageGuide/Initialization.html)

   ```swift 
   class Node {
     var value: Int 
     var next: Node? 
     init(_ value: Int) {
       self.value = value
     }
   }
   ```
   
   #### Glossary 
   
   * Default initializers 
   * Memberwise initializers 
   * Designated initializers
   * Convenient initializers 
   * Failable initializers 
   * Required initializers 

## 16. [Deinitialization](https://docs.swift.org/swift-book/LanguageGuide/Deinitialization.html#)

   > `deint` only works within classess 

   ```swift 
   class ItemViewController: UIViewController {
     deinit {
       // do any cleanup code or remove any notifications or listeners e.g Firebase listener
     }
   }
   ```

## 17. [Optional Chaining](https://docs.swift.org/swift-book/LanguageGuide/OptionalChaining.html)

   ```swift 
   struct Person {
     var name: String
     var phone: Phone?  

     struct Phone {
       var work: String? 
       var home: String?
     }
   }

   let person = Person(name: "Alice", phone: Person.Phone(work:"917-457-3498", home: nil))

   if let workPhone = person.phone?.work {
     print("\(person.name)'s work phone number is \(workPhone)'")
     // Alice's work phone number is 917-457-3498
   } else {
     print("\(person.name) does not have a work phone number.")
   }
   ```

## 18. [Error Handling](https://docs.swift.org/swift-book/LanguageGuide/ErrorHandling.html#)

   ```swift 
   enum AppError: Error {
     case badYear
     case noData 
     case serverError
   }

   func currentYear(_ year: Int) throws {
     if year == 2020 {
       throw AppError.badYear
     }
     print("Fingers crossed this is a great year for us all.")
   }

   do {
     try currentYear(2020)
   } catch {
     print(error) // badYear
   }

   do {
     try currentYear(2021) // Fingers crossed this is a great year for us all.
   } catch {
     print(error)
   }
   ```
   
   ##### Glossary 
   
   * throw 
   * throws 
   * do-catch 
   * `try`, `try?` and `try!`
   * Error
   
## 19. Type Casting 

   Downcasting 
   
   ```swift 
   class Person {
     func info() {
       print("This is a person.")
     }
   }

   class Fellow: Person {
     override func info() {
       print("This person is a fellow.")
     }
   }

   class Singer: Person {
     override func info() {
       print("This person is a singer.")
     }
   }

   let heather = Fellow()
   let bob = Singer()
   let people = [bob, heather]

   if let person = people[0] as? Singer { // downcast from Person object to a Singer object
     person.info() // This person is a singer.
   }
   ```
   
   Type checking 
   
   ```swift 
   let objects: [Any] = ["Alex", true, 2021]

   if objects[0] is String {
     print("\(objects[0]) is a String object.") // Alex is a String object.
   }

   if objects[1] is Bool {
     print("\(objects[1]) is a Bool instance.") // true is a Bool instance.
   }
   ```

   #### Glossary 
   
   * downcasting 
   * `as!`, `as?`, `as`
   * type checking
   

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
1. [Enumerations](https://github.com/alexpaul/Swift-Fundamentals/blob/main/Enumerations-Exercises.md)
1. [Structs](https://github.com/alexpaul/Swift-Fundamentals/blob/main/Structs.md)


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
