# Readline 

## Using `readline`

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
print("Enter N integers")
var nPositiveIntegers = [Int]()
if let value = readLine() {
    let stripped = value.split(separator: " ")
    nPositiveIntegers = convertStringToIntegers(stripped)
}
print("\(nPositiveIntegers.count) integers were entered: \(nPositiveIntegers)")

// Input 2
print("Enter three integers")
if let value = readLine() {
    let stripped = value.split(separator: " ")
    let nums = convertStringToIntegers(stripped)
    let prefix = nums.prefix(3)
    print("The three integers are \(prefix)")
}
```
