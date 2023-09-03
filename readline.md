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

print("Enter N integers")
var nPositiveIntegers = [Int]()
if let value = readLine() {
    let stripped = value.split(separator: " ")
    nPositiveIntegers = convertStringToIntegers(stripped)
}

print("\(nPositiveIntegers.count) integers were entered: \(nPositiveIntegers)")
```
