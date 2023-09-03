# Readline 

## Using `readline`

```swift
print("Enter N positive integers")
var nPositiveIntegers = [Int]()
if let value = readLine() {
    let stripped = value.split(separator: " ")
    var nums = [Int]()
    for str in stripped {
        if let num = Int(str) {
            nums.append(num)
        } else {
            print("Invalid input")
        }
    }
    nPositiveIntegers = nums
}

print("\(nPositiveIntegers.count) integers were entered: \(nPositiveIntegers)"
```
