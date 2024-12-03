
# Swift Closures: Functions as First-Class Citizens 🚀

## 📝 Introduction to Closures
Swift lets us use functions just like any other type such as strings and integers. This means you can:
- Create a function and assign it to a variable
- Call that function using the variable
- Pass that function into other functions as parameters

These self-contained blocks of functionality are called closures.

## 🔍 Basic Closure Syntax

### Creating Basic Closures
```swift
let driving = {
    print("I'm driving in my car")
}

// Call the closure like a function
driving()
```

## 📥 Closures with Parameters
To make a closure accept parameters, list them inside parentheses just after the opening brace, then use the `in` keyword to indicate the start of the main closure body.

```swift
let flying = { (place: String) in
    print("I'm going to \(place) by plane")
}

// Call without parameter labels
flying("Istanbul")
```

**⚠️ Important Difference:** One of the key distinctions between functions and closures is that you don't use parameter labels when calling closures.

## 🔄 Closures with Return Values
To include a return value in a closure, use `-> TypeName` before the `in` keyword, then use `return` just like in a normal function:

```swift
let drivingWithReturn = { (place: String) -> String in
    return "I'm going to \(place) in my car"
}

let message = drivingWithReturn("Istanbul")
print(message)
```

## 🎭 Closures as Function Parameters
If you want to pass a closure into a function so it can be run inside that function, you would specify the parameter type as `() -> Void`. This means a closure that takes no parameters and returns nothing.

```swift
let swimming = {
    print("I am swimming in the sea.")
}

func travel(action: () -> Void) {
    print("I am gonna swim in the sea")
    action()
    print("I am sunbathing.")
}

// Call the function with a closure
travel(action: swimming)
```

## 🏁 Trailing Closure Syntax
If the last parameter to a function is a closure, Swift provides a special syntax called trailing closure syntax. Instead of passing the closure as a parameter, you pass it directly after the function call, inside braces.

```swift
func travelTrailing(action: () -> Void) {
    print("Trailing Closures are")
    action()
    print("amazing!")
}

// Trailing closure syntax
travelTrailing { // notice we didnt parameters when calling
    print("I am swimming in the sea.")
}
```

## 🏁 Key Takeaways
- Closures are self-contained code blocks
- Can be assigned to variables
- Accept parameters and return values
- Can be passed as function parameters
- Provide concise, inline function definitions

## 🌟 Pro Developer Tips
- Use closures for short, one-time use functions
- Leverage trailing closure syntax for readability
- Practice using closures with different parameter and return types
- Consider closures for callbacks and completion handlers
- Keep closure logic concise and focused

## ⚠️ Common Pitfalls
- Avoid complex, long closures
- Be mindful of capturing variables (memory management)
- Remember closures don't use parameter labels
- Watch out for potential retain cycles with closures

**Don't forget to check out the extra section: [Parameter Passing Mechanism](https://github.com/KasimDeliaci/HackingWithSwift/blob/main/Contents/Day5_Param_Passing_Mechanism.md) to have a better understanding of parameter passing in swift**

