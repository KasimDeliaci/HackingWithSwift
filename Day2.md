# Swift Complex Data Types 🚀

## Introduction
Swift provides several powerful data types for managing collections of data, each with unique characteristics and use cases.

## 📝 Arrays
Arrays are ordered collections of values stored in a continuous memory space.

```swift
var beatles = ["John Lennon", "Paul McCartney", "George Harrison", "Ringo Starr"]
```

### Key Array Characteristics
- 0-indexed (first item at index 0)
- Can access elements by index
- ⚠️ Accessing non-existent index causes a crash

### Array Type Annotations
```swift
let stringArray: [String] = ["Hello", "World"]
let intArray: [Int] = Array(1...10)
let doubleArray: [Double] = Array(repeating: 0.0, count: 10)
let boolArray: [Bool] = Array(repeating: false, count: 10)
```

### Array Manipulation
```swift
beatles.append("Jimi Hendrix")     // Add to end
beatles.insert("Pete Best", at: 3) // Insert at specific position
```

## 🧰 Sets
Sets are unordered collections of unique values with some powerful features.

```swift
var colors = Set(["Red", "Blue", "Yellow", "Red"])
```

### Set Insertion Mechanism
The `insert()` method returns a tuple with two important pieces of information:

```swift
let (inserted, memberAfterInsert) = colors.insert("Orange")
```

**Detailed `insert()` Method Breakdown:**
- `inserted`: A boolean value 
  - `true` if the item was successfully added (new)
  - `false` if the item already existed in the set
- `memberAfterInsert`: The actual item that was inserted or already present

**Practical Example:**
```swift
let (wasInserted, finalValue) = colors.insert("Purple")
print(wasInserted)        // true (Purple was new)
print(finalValue)         // "Purple"

let (duplicateInserted, existingValue) = colors.insert("Purple")
print(duplicateInserted)  // false (Purple already existed)
print(existingValue)      // "Purple"
```

### Set Characteristics
- Eliminates duplicates automatically
- Unordered
- Extremely efficient for:
  - Membership checking
  - Removing duplicates
  - Performing set operations (union, intersection)

## 🔒 Tuples
Tuples are immutable collections that group multiple values into a single compound value.

### Basic Tuple Creation
```swift
var name = (first: "Kasim", last: "Deliaci")
```

### Accessing Tuple Values
```swift
print(name.0)        // Accessing by index: "Kasim"
print(name.first)    // Accessing by name: "Kasim"
```

### Tuple Flexibility and Limitations

#### Allowed Operations
```swift
// Modify individual values
name.first = "Yunus"    // ✅ Allowed
name.last = "Yilmaz"    // ✅ Allowed
```

#### Restricted Operations
```swift
// ❌ NOT Allowed: Cannot change structure or types
// name = (first: "Kasim", age: 21)  // Compilation Error!
// name.middleName = "Can"           // Cannot add new elements
```

### Tuple Use Cases
```swift
// Returning multiple values from a function
func getUserInfo() -> (name: String, age: Int, isActive: Bool) {
    return ("John Doe", 30, true)
}

let (username, userAge, userActive) = getUserInfo()
```

## 📖 Dictionaries
Dictionaries store key-value pairs for flexible data representation.

```swift
let heights = [
    "Taylor Swift": 1.78,
    "Ed Sheeran": 1.74,
    "Bruno Mars": 1.65
]
print(heights["Taylor Swift"])
```

### Dictionary Features
- Access values using keys
- Return `nil` for non-existent keys
- Provide default values

```swift
let favoriteIceCream = [
    "Kasim": "Chocolate",
    "Yunus": "Vanilla"
]

// Safe dictionary access
let flavor = favoriteIceCream["Mustafa", default: "Unknown flavor"]
```

### Dictionary Methods
```swift
var scores = ["Alice": 95, "Bob": 80]
scores.removeValue(forKey: "Bob")  // Removes and returns the value
scores.updateValue(100, forKey: "Alice")  // Updates value, returns old value
```

## 🌈 Empty Collections
Creating empty collections with type annotations:

```swift
var teams = [String]()
var numbers: [Int] = []
var players: Set<String> = []
var scores: [String: Int] = [:]
```

## 🏷️ Enumerations (Enums)
Enums define groups of related values with additional capabilities.

### Basic Enum
```swift
enum Result {
    case win
    case lost
    case draw
}
let result = Result.win
```

### Enum with Associated Values
We may want to store additional information about the cases.
```swift
enum Activity {
    case bored
    case running(destination: String)
    case talking(topic: String)
    case playing(volume: Int, instrument: String)
}

let running = Activity.running(destination: "Park")
let playing = Activity.playing(volume: 11, instrument: "Guitar")

// Pattern matching with enums
switch running {
case .running(let destination):
    print("Running to \(destination)")
default:
    break
}
```

### Enum Raw Values
we can have rawvalues for our cases making it more meaningful for everybody
```swift
enum Planet: Int {
    case mercury = 1  // Explicitly set first value, for dynamic creation
    case venus
    case earth
    case mars
}

let earthRawValue = Planet.earth.rawValue  // 3
let specificPlanet = Planet(rawValue: 2)   // venus
```
⚠️ if you dont explicitly set the first value, it will count from 0

## 🚀 Key Takeaways
- Arrays: Ordered, indexed collections
- Sets: Unique, unordered collections
- Tuples: Fixed-size, potentially named collections
- Dictionaries: Key-value pair collections
- Enums: Structured, type-safe grouping of related values

