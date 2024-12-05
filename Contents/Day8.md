
# 🏗️ Swift Structs: Building Custom Types and Beyond

## 📘 Introduction to Structs in Swift
Structs are custom data types that allow you to create your own complex types with properties and methods. They provide a powerful way to organize and encapsulate related data and behaviors in Swift, serving as fundamental building blocks for creating more sophisticated and organized code.

## 🧱 Creating Basic Structs
Structs let you define custom types with properties, following these key principles:
- Use CamelCase for struct names
- Define properties that describe the type's characteristics
- Create instances with specific property values

```swift
struct Sport {
    var name: String
}

var tennis = Sport(name: "Tennis")
print(tennis.name)  // Prints: Tennis

// Modifying properties
tennis.name = "Lawn Tennis"
print(tennis.name)  // Prints: Lawn Tennis
```

**💡 Pro Tip:** Properties are variables or constants that define the characteristics of a struct instance.

## 🧮 Computed Properties
Computed properties dynamically calculate their value based on other properties, allowing for intelligent, context-aware data generation.

```swift
struct Car {
    var name: String
    var isFast: Bool

    var engine: String {
        if isFast {
            return "\(name) has bigger engine"
        } else {
            return "\(name) has smaller engine"
        }
    }
}

let myCar = Car(name: "BMW", isFast: true)
print(myCar.engine)  // Dynamically generates engine description
```

## 🚨 Property Observers
Property observers allow you to run code before or after a property's value changes, enabling powerful tracking and side-effect management.

```swift
struct Progress {
    var task: String
    var amount: Int {
        didSet {
            print("\(task) is now \(amount)% complete")
        }
    }
}
```

**⚠️ Key Observation:**
- `didSet`: Triggers after the value changes
- `willSet`: Triggers before the value changes

## 🛠️ Struct Methods
Methods are functions defined within structs that can interact with the struct's properties, adding behavior to your custom types.

```swift
struct City {
    var population: Int

    func collectTaxes() -> Int {
        return population * 1000
    }
}

var istanbul = City(population: 16_000_000)
print(istanbul.collectTaxes())  // Calculates tax revenue
```

## 🔄 Mutating Methods: Deep Dive

### Understanding Struct Mutability

When you create a struct in Swift, the language takes a cautious approach to modifications. By default, methods cannot change a struct's properties if the struct instance is declared as a constant. However, Swift does not not if you are gonna declare it as variable so it takes the safe approach requires you to have a mutating keyword to change properties.

```swift
struct Person {
    var name: String

    // Mutating method is required to change properties
    mutating func makeAnonymous() {
        name = "Anonymous"
    }
}
```

### Why Mutating Methods Exist

**🔍 Key Insights:**
- Swift doesn't know in advance whether a struct will be used with constants or variables
- The default safe approach prevents unintended modifications
- The `mutating` keyword explicitly allows property changes

### Detailed Mutation Constraints

```swift
struct Person {
    var name: String

    // This method requires 'mutating' to change the property
    mutating func makeAnonymous() {
        name = "Anonymous"
    }
}

// Only works with variable instances
var person = Person(name: "John")
person.makeAnonymous()  // Allowed

// This would cause a compile-time error
let constantPerson = Person(name: "Jane")
// constantPerson.makeAnonymous()  // Not allowed!
```

**🚨 Critical Observations:**
- Mutating methods can ONLY be called on variable struct instances
- The `mutating` keyword stops method calls on constant structs
- Even if the method doesn't actually change anything, marking it `mutating` prevents its use on constants

**⚠️ Mutation Pitfalls**
- Overusing mutating methods can lead to less predictable code
- Creating complex mutation logic can make code harder to understand
- Always consider whether mutation is the best approach

## 🧪 Built-in Struct Methods: Strings and Arrays

### String Methods
```swift
var myStr = "You are all I need."
print(myStr.count)           // Length of string
print(myStr.uppercased())    // Uppercase conversion
print(myStr.hasPrefix("You"))// Prefix check
```

### Array Methods
```swift
var myArray: [Int] = [1, 2, 3, 4, 5]
print(myArray.count)         // Array length
print(myArray.first!)        // First element
myArray.append(6)            // Add element
myArray.remove(at: 2)        // Remove element at index
```

## 🏆 Pro Developer Tips
- Use structs for simple data models
- Leverage computed properties for dynamic calculations
- Utilize property observers for state tracking
- Prefer immutability when possible
- Use `mutating` methods sparingly
- Consider alternative design patterns if you find yourself frequently mutating structs

## 🌟 Key Takeways
- Custom type creation
- Encapsulation of data and behavior
- Computed properties
- Method definition
- Immutability support
- Flexible property observation

## ⚠️ Common Pitfalls
- Overusing mutating methods
- Creating overly complex structs
- Forgetting struct immutability constraints
- Unnecessary mutations
- Complex mutation logic
