# 🏛️ Swift Advanced Structs: Initialization, Lazy Properties, and Access Control

## 📘 Introduction to Advanced Struct Concepts
Swift provides powerful features that go beyond basic struct creation, allowing for more sophisticated type design, initialization strategies, and property management. This guide explores advanced techniques to create more intelligent and efficient structs.

## 🏗️ Initializers: Customizing Object Creation
Initializers are special methods that provide flexible ways to create struct instances. By default, Swift provides a memberwise initializer, but you can create custom initializers to set up your struct with specific logic.

```swift
struct User {
    var username: String
    
    init() {
        username = "Default User"
        print("created a user")
    }
}
```

**🔑 Key Insights:**
- Initializers don't use the `func` keyword
- Must ensure all properties have a value before initialization completes
- Creating a custom initializer removes the default memberwise initializer

## 🔍 Understanding `self` Keyword
The `self` keyword helps distinguish between property names and parameter names, preventing ambiguity in initializers.

```swift
struct Person {
    var name: String

    init(name: String) {
        print("\(name) was born!")
        self.name = name  // self.name refers to the property
    }
}
```

**💡 Pro Tip:** Use `self` to clearly indicate you're referring to the struct's property when parameter names match property names.

## 💤 Lazy Properties: On-Demand Initialization
Lazy properties are a performance optimization technique that delays property creation until it's first accessed.

```swift
struct FamilyTree {
    init() {
        print("Creating family tree!")
    }
}

struct Human {
    var name: String
    lazy var familyTree = FamilyTree()

    init(name: String) {
        self.name = name
    }
}

var ed = Human(name: "Ed")
// FamilyTree is not created until ed.familyTree is accessed
ed.familyTree  // Now the FamilyTree is initialized
```

**⚠️ Important:**
- Lazy properties are created only when first accessed
- Useful for expensive computations or resources
- Helps optimize memory and performance

## 📊 Static Properties and Methods
Static properties and methods belong to the struct itself, not to individual instances.

```swift
struct Student {
    static var classSize = 0
    var name: String

    init(name: String) {
        self.name = name
        Student.classSize += 1
    }
}

let kasim = Student(name: "Kasım")
let taylor = Student(name: "Taylor")

print(Student.classSize)  // Prints total number of students
```

**🌟 Key Features:**
- Shared across all struct instances
- Accessible directly through the struct name
- Useful for tracking class-wide information

## 🔒 Access Control
Swift provides access control to restrict property and method visibility.

```swift
struct Teacher {
    private var id: String

    init(id: String) {
        self.id = id
    }

    func identify() -> String {
        return "Teacher ID: \(id)"
    }
} // Now only methods inside Person can read the id property
```

**Access Control Levels:**
- `private`: Accessible only within the struct
- `fileprivate`: Accessible within the same source file
- `internal` (default): Accessible within the module
- `public`: Accessible from any module
- `private(set)`: Property can be read publicly but only set privately

## 🏆 Pro Developer Tips
- Use lazy properties for resource-intensive initializations
- Leverage static properties for shared information
- Implement custom initializers for complex setup logic
- Use access control to protect sensitive data
- Keep initializers simple and focused

## 🏁 Key Takeaways
- Custom initializers provide flexibility
- `self` helps resolve naming conflicts
- Lazy properties optimize performance
- Static members provide struct-level information
- Access control ensures data protection

## ⚠️ Common Pitfalls
- Overcomplicating initializers
- Misusing lazy properties
- Ignoring access control best practices
- Creating unnecessary static properties

