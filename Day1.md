
# Swift Basics: Variables, Types, and Syntax

## Introduction to Variables
Swift is a type-safe language, which means every variable must have a specific, well-defined type. 

## Variable Declaration

### Basic String Variable
```swift
var greeting = "Hello, playground"
```

### Numeric Variables
```swift
var age = 45
var population = 8_000_000  // Underscores for readability
```

## String Formatting

### Multiline Strings
```swift
var multilinestr = """
this is
multiline
string
"""
```
**Important:** The opening and closing quotes for multiline strings must be on their own lines.

### Single-Line Multiline Strings
```swift
var singleLineMulti = """
this is \
actually \
one line
"""
```
The `\` allows you to create a multiline string that's interpreted as a single line.

## Data Types

### Doubles and Booleans
```swift
var thisIsDouble = 3.1415
var isTrue = true
```

### Type Conversion
**Note:** Swift is strict about type mixing. You cannot directly add different types:
```swift
var myDouble = 3.4
var myInt = 3
// var sum = myDouble + myInt  // This would cause a compilation error
```

## String Interpolation
```swift
var score = 88
var str = "My score is \(score)"
var result = "The test results are: \(str)"
```
String interpolation allows you to embed variables or expressions directly in strings.

## Constants
```swift
let pi = 3.14  // Cannot be changed after initial assignment
```

## Type Annotations
Swift can infer types, but you can also explicitly declare them:
```swift
var thisInt: Int = 3
var thisDouble: Double = 3.14
var myString: String = "Hello"
var myBool: Bool = true

var myArray: [Int] = [1, 2, 3, 4, 5]
var mySingleArray: [Int] = [1]
```

## Key Takeaways
- Swift is a type-safe language
- Use `var` for variables that can change
- Use `let` for constants
- Underscores can improve numeric literal readability
- String interpolation provides a powerful way to embed values in strings
- You can explicitly declare types or rely on type inference
