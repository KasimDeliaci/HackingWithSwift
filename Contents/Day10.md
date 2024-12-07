# 🚀 Swift Classes: A Deep Dive into Object-Oriented Programming

## 📝 Introduction to Swift Classes
Classes in Swift are a fundamental building block of object-oriented programming, offering powerful features that distinguish them from structs. They provide a way to create complex, reusable types with advanced capabilities like inheritance, reference semantics, and more.

## 🔍 Key Differences from Structs
Swift classes introduce several crucial distinctions that make them unique:
1. No automatic memberwise initializer
2. Support for inheritance
3. Reference type semantics
4. Deinitializers
5. Ability to modify properties in constant instances

## 🏗️ Creating Classes: Basic Structure

### 1. Class Declaration and Initialization
Unlike structs, classes require explicit initialization. Swift forces you to provide a complete initializer that sets all properties.

```swift
class Dog {
    var name: String
    var breed: String

    init(name: String, breed: String) {
        self.name = name
        self.breed = breed
    }
}
```

**🔑 Key Insight:** 
- No automatic memberwise initializer
- Must provide a custom initializer
- `self` keyword used to distinguish between parameter and property names

## 🌳 Inheritance: Extending Class Functionality

### Building on Existing Classes
Classes can inherit from other classes, creating a hierarchical structure of types.

```swift
class Puppy: Dog {
    init(name: String) {
        // Call parent class initializer with a default breed
        super.init(name: name, breed: "Poodle")
    }
}
```

**💡 Important Notes:**
- Always call `super.init()` in child class initializers
- Can add new properties and methods
- Inherits all properties and methods from parent class

## 🔄 Method Overriding
Classes allow you to replace parent class methods with custom implementations.

```swift
class Animal {
    func makeNoise() {
        print("Some generic animal sound")
    }
}

class Cat: Animal {
    // Must use 'override' keyword
    override func makeNoise() {
        print("Meow!")
    }
}
```

**⚠️ Compiler Requirement:** 
- `override` keyword is mandatory
- Prevents accidental method replacements
- Provides clear intent in code

## 🔒 Final Classes
Prevent inheritance and further modification of a class.

```swift
final class ImmutableClass {
    let identifier: String
    
    init(identifier: String) {
        self.identifier = identifier
    }
}
```

**🛡️ Use Cases:**
- Prevent unintended subclassing
- Optimize performance
- Ensure class behavior remains consistent

## 📋 Reference vs. Value Semantics

### Shared Instance Behavior
Unlike structs, class instances are reference types, meaning multiple variables can point to the same instance.

```swift
class Singer {
    var name = "Taylor Swift"
}

var singer1 = Singer()
var singer2 = singer1

singer2.name = "Ed Sheeran"
print(singer1.name) // Prints: Ed Sheeran
print(singer2.name) // Prints: Ed Sheeran
```

**🌐 Key Characteristics:**
- Changing one reference affects all references
- Shared memory location
- Different from value types (structs)

## 💀 Deinitializers
Special method called when a class instance is about to be destroyed.

```swift
class Person {
    var name: String
    
    init(name: String) {
        self.name = name
        print("\(name) is alive!")
    }
    
    deinit {
        print("\(name) is being removed from memory")
    }
}
```

**🔍 Deinitializer Insights:**
- No parameters or return values
- Used for cleanup operations
- Called automatically by Swift's ARC (Automatic Reference Counting)

## 🔧 Mutability Flexibility

### Constant Instances with Mutable Properties
Unlike structs, class instances allow property changes even when declared as constants.

```swift
class Actor {
    var name = "Nicole Kidman"
}

let nicole = Actor()
nicole.name = "Tom Cruise" // Allowed!
```

**💡 Important Distinction:**
- Properties can be changed in constant class instances
- No need for `mutating` keyword
- Provides more flexibility compared to structs

## 🏆 Key Takeways
- Reference type semantics
- Support for inheritance
- Method overriding
- Deinitializer support
- Flexible mutability
- Complex object modeling

## ⚠️ Pro Developer Tips
1. Prefer structs unless you need class-specific features
2. Be cautious with reference semantics to avoid unexpected mutations
3. Use `final` to prevent unnecessary inheritance
4. Always use `override` when replacing parent methods
5. Understand ARC and potential retain cycles
6. Consider protocol-oriented programming as an alternative
