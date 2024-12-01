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

### Set Insertion: A Closer Look
The `insert()` method is particularly interesting because it returns a tuple with two valuable pieces of information:

```swift
let (inserted, memberAfterInsert) = colors.insert("Orange")
```

**Deep Dive into `insert()` Method:**
- `inserted`: A boolean value 
  - `true` if the item was successfully added (didn't already exist)
  - `false` if the item was already in the set
- `memberAfterInsert`: The actual item that was inserted or already existed

**Example Demonstration:**
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
Tuples are fixed-size collections with potential named elements.

```swift
var name = (first: "Kasim", last: "Deliaci")
print(name.0)        // "Kasim"
print(name.first)    // "Kasim"
name.0 = "Yunus"     // Allowed
```

**⚠️ Warning:** Cannot change tuple structure or types after creation

### Tuple Advanced Usage
```swift
// Multiple return values
func getUserInfo() -> (name: String, age: Int, isActive: Bool) {
    return ("John Doe", 30, true)
}

let (username, userAge, _) = getUserInfo()
```

## 📖 Dictionaries
Dictionaries store key-value pairs for flexible data representation.

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
// Useful dictionary operations
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

### Enum with Associated Values
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
```swift
enum Planet: Int {
    case mercury = 1  // Explicitly set first value
    case venus
    case earth
    case mars
}

let earthRawValue = Planet.earth.rawValue  // 3
let specificPlanet = Planet(rawValue: 2)   // venus
```

## 🚀 Advanced Considerations
- Use `Set` when order doesn't matter and uniqueness is key
- Prefer tuples for small, fixed collections of related values
- Leverage enum associated values for complex state representations

**Pro Tip:** Each collection type has its strengths. Choose wisely based on your specific use case!
