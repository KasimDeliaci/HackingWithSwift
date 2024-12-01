

# Swift Basics: Variables, Types, and Syntax

---

## Introduction to Variables
Swift is a type-safe language, which means every variable must have a specific, well-defined type.

---

## Variable Declaration

### Basic String Variable
```swift
var greeting = "Hello, playground"

Numeric Variables

var age = 45
var population = 8_000_000 // Underscores for readability

String Formatting

Multiline Strings

var multilinestr = """
this is
multiline
string
"""

Important: The opening and closing quotes for multiline strings must be on their own lines.

Single-Line Multiline Strings

var singleLineMulti = """
this is \
actually \
one line
"""

Double and Boolean Variables

Double Example

var thisISDouble = 3.1415

Boolean Example

var isTrue = true

Type Safety in Arithmetic

var myDouble = 3.4
var myInt = 3
// var sum = myDouble + myInt // Error: Cannot add Double and Int directly

String Interpolation

String interpolation allows you to include variables or expressions directly within strings.

Example

var score = 88
var str = "My score is \(score)"
var result = "The test results are: \(str)"

Constants

Constants are defined using the let keyword. Their values cannot be changed once assigned.

Example

let pi = 3.14

Type Annotations

Type annotations allow you to explicitly specify the type of a variable.

Basic Examples

var thisInt: Int = 3
var thisDouble: Double = 3.14
var myString: String = "Hello"
var myBool: Bool = true

Array Example

var myArray: [Int] = [1, 2, 3, 4, 5]
var mySingleArray: [Int] = [1]

Summary

	•	Variables: Defined using var and can be reassigned.
	•	Constants: Defined using let and cannot be changed.
	•	Multiline Strings: Use """ to span across multiple lines.
	•	Double and Boolean: Handle floating-point numbers and logical values.
	•	String Interpolation: Include variables directly within strings.
	•	Type Annotations: Specify variable types explicitly when needed.

Her başlık için ayrı bir `##` ekledim, görseldeki düzenlemeyi doğru şekilde uyguladım. Şimdi istediğiniz gibi tüm konular düzenlenmiş halde! 😊
