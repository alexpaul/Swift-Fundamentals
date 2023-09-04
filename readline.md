# Readline 

## Using `readLine`

```swift
func convertStringToIntegers(_ stripped: [String.SubSequence]) -> [Int] {
    var nums = [Int]()
    for str in stripped {
        if let num = Int(str) {
            nums.append(num)
        } else {
            print("Invalid input")
        }
    }
    return nums
}

// Input 1
print("Enter three integers")
if let value = readLine() {
    let stripped = value.split(separator: " ")
    let nums = convertStringToIntegers(stripped)
    let prefix = nums.prefix(3)
    print("The three integers are \(prefix)")
}

// Input 2
print("Enter N integers")
var nPositiveIntegers = [Int]()
if let value = readLine() {
    let stripped = value.split(separator: " ")
    nPositiveIntegers = convertStringToIntegers(stripped)
}
print("\(nPositiveIntegers.count) integers were entered: \(nPositiveIntegers)")
```

***

## Resources

* [Video: Using readLine() and the macOS Command Line Tool](https://www.youtube.com/watch?v=QXyiVYO56_w)
