# Readline 

## Using `readline`

```swift
print("Enter N integers")
var nPositiveIntegers = [Int]()
if let value = readLine() {
    let stripped = value.split(separator: " ")
    nPositiveIntegers = convertStringToIntegers(stripped)
}

print("\(nPositiveIntegers.count) integers were entered: \(nPositiveIntegers)")
```
