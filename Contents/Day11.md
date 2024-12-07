# 🚀 Swift Protocols and Extensions: A Comprehensive Guide

## 📝 Introduction to Protocols and Extensions
Protocols and extensions are powerful features in Swift that enable flexible, modular, and extensible code design. They provide ways to define contracts for types and add functionality to existing types without modifying their original implementation.

## 🔍 Protocols: Defining Type Contracts

### Understanding Protocols
Protocols are blueprints that define a set of properties, methods, and requirements that conforming types must implement.

```swift
protocol Identifiable {
    var id: String { get set }
}
```

**🔑 Key Insights:**
- Protocols define a contract for types
- Cannot be instantiated directly
- Types conform to protocols by implementing required methods and properties
- Can specify property access levels with `get` and `set`

**⚠️ Important Note:** 
- Protocols can have `{get}` or `{get set}`
- Cannot have only `{set}`

### Conforming to Protocols
Types can conform to protocols by implementing their requirements:

```swift
struct User: Identifiable {
    var id: String
}

func displayID(thing: Identifiable) {
    print("My ID is \(thing.id)")
}
```

## 🌳 Protocol Inheritance
Protocols can inherit from multiple other protocols, creating complex and flexible type requirements.

```swift
protocol Payable {
    func calculateWages() -> Int
}

protocol NeedsTraining {
    func study()
}

protocol HasVacation {
    func takeVacation(days: Int)
}

// Combining multiple protocols
protocol Employee: Payable, NeedsTraining, HasVacation { }
```

**💡 Unique Features:**
- Unlike class inheritance, you can inherit from multiple protocols
- Provides a way to compose complex type requirements
- Allows for modular and flexible design

## 🧩 Extensions: Extending Type Functionality

### Adding Methods to Existing Types
Extensions allow you to add new methods to existing types without modifying their original implementation.

```swift
extension Int {
    func squared() -> Int {
        return self * self
    }
}

let number = 5
print(number.squared()) // Prints: 25
```

**⚠️ Limitations:**
- Cannot add stored properties
- Can add computed properties
- Provide a way to extend type functionality

## 🔬 Protocol Extensions
Protocols let you describe what methods something should have, but don’t provide the code inside on the other hand Extensions let you provide the code inside your methods, but only affect one data type.
Protocol extensions solve the limitations of both protocols and extensions by providing default implementations for protocol methods.

```swift
extension Collection {
    func summarize() {
        print("There are \(count) of us:")
        for name in self {
            print(name)
        }
    }
}

let pythons = ["Eric", "Graham", "John", "Michael", "Terry", "Terry"]
let beatles = Set(["John", "Paul", "George", "Ringo"])

pythons.summarize()
beatles.summarize()
```

**🌐 Key Characteristics:**
- Provide default implementations for protocols
- Affect all types conforming to the protocol
- Enable protocol-oriented programming

## 🏗️ Protocol-Oriented Programming

### Default Protocol Implementations
Protocol extensions can provide default method implementations, reducing boilerplate code. 

```swift
protocol Purchasable {
    var price: Int { get set }
    func checkPrice()
}

extension Purchasable {
    func checkPrice() {
        print("My price is \(price).")
    }
}

struct Car: Purchasable {
    var price: Int
}

var car = Car(price: 1000)
car.checkPrice() // Prints: My price is 1000.
```

**💡 Advantages:**
- Reduces redundant code
- Provides a default implementation
- Types can override default implementations if needed

## 🏁 Key Takeways
- Define type contracts
- Multiple protocol inheritance
- Add methods to existing types
- Provide default implementations
- Enable modular and flexible code design
- Support protocol-oriented programming

## ⚠️ Pro Developer Tips
1. Use protocols to define clear type requirements
2. Leverage protocol inheritance for complex type compositions
3. Use extensions to add functionality without modifying original types
4. Prefer protocol extensions for providing default implementations
5. Consider protocol-oriented programming for more flexible designs
6. Be mindful of performance when using extensive protocol extensions

