# Swift Loops and Control Flow 🔁

## 📝 Introduction to Loops
Loops are fundamental control flow structures in Swift that allow you to repeat code execution based on specific conditions. They provide powerful ways to iterate through collections, perform repetitive tasks, and create complex algorithmic patterns.

## 🔄 For Loops
For loops in Swift offer flexible iteration over ranges and collections.

### Iterating Through Ranges
```swift
let count = 1...10
for number in count {
    print("\(number)")
}
```

### Iterating Through Arrays
```swift
let myArr = ["for", "loop", "can", "traverse", "in", "array"]
for item in myArr {
    print("\(item)")
}
```

### 🚨 Ignoring Loop Variables
```swift
print("Players gonna ")

for _ in 1...5 {
    print("play")
}
```

**⚠️ Pro Tip:** Use an underscore (`_`) when you don't need the loop variable to avoid creating unnecessary values.

## 🔁 While Loops
While loops continue executing as long as a condition remains true.

```swift
var counter = 1

while counter <= 10 {
    print("\(counter)")
    counter += 1
}
```

## 🔂 Repeat-While Loops (Do-While Equivalent)
Guaranteed to execute at least once before checking the condition.

```swift
var number = 1

repeat {
    print(number) // Executed at least one time
    number += 1
} while number <= 20

print("Ready or not, here I come!")
```

**💡 Important:** The code block is always executed at least once before the condition is evaluated.

## 🛑 Exiting Loops: Break Statement
Break allows immediate exit from a loop.

```swift
var countDown = 10
while countDown >= 0 {
    print(countDown)

    if countDown == 4 {
        print("I'm scared. Let's go now!")
        break
    }

    countDown -= 1
}
print("This line will execute after countdown = 4 because of the break")
```

## 🏷️ Exiting Nested Loops
Labeled breaks provide control over nested loop structures.

```swift
outerLoop: for i in 1...10 {
    for j in 1...10 {
        let product = i * j
        print ("\(i) * \(j) is \(product)")

        if product == 50 {
            print("It's a bullseye!")
            break outerLoop
        }
    }
}
```

**⚠️ Warning:** Without labeling, a `break` only exits the innermost loop.

## ⏩ Skipping Items: Continue Statement
Skip the current iteration and move to the next.

```swift
for i in 1...10 {
    if i % 2 == 1 {
        continue
    }

    print(i) // Prints 2 4 6 8 10
}
```

## ♾️ Infinite Loops
Loops that continue until a specific condition is met.

```swift
var myCounter = 0

while true {
    print(" ")
    myCounter += 1

    if myCounter == 273 {
        break
    }
}
```

**🚨 Critical Warning:** Always include an exit condition to prevent endless execution.

## 🏁 Key Takeaways
- Swift offers multiple loop types: for, while, and repeat-while
- Use `_` to ignore loop variables
- `break` exits loops completely
- `continue` skips the current iteration
- Nested loops can be controlled with labeled breaks
- Always ensure infinite loops have an exit condition

## 🌟 Pro Developer Tips
- Choose the most appropriate loop type for your specific use case
- Use `continue` for conditional skipping
- Label nested loops for precise control flow
- Be cautious with infinite loops
- Prefer `for` loops when iterating over known collections
- Use `while` loops for conditions not directly tied to collections
- Always have a clear termination strategy for loops
