# Variables

In Swift, variables provide a way to store data that can change during the execution of a program. This data can either be input by the user or displayed on the screen. Swift uses the keyword **`var`** to declare variables.

## Declaring a Variable

To create a variable, use the following syntax:

```swift
var variableName
```

- **`var`**: A keyword that tells Swift to create a new variable.
- **`variableName`**: A developer-defined name that describes the purpose of the variable.

## Intializing a Variable

You can assign an initial value to a variable when you declare it. For example:

```swift
var myName = "Maged Elesseily"
```

- **`=`**: The assignment operator that stores the value in the variable.
- **`" "`**: Double quotes indicate a string value ([**explained later in this branch**](https://github.com/MagedGDEV/SwiftInsights/tree/variables#strings)).

After this code, the variable **`myName`** holds the value **`"Maged Elesseily"`**.

## Changing the Value of a Variable

Variables are mutable, meaning their value can be updated after they are created:

```swift
var status
status = "Available"
status = "Busy"
```

- **`var status`**: Declares a variable named **`status`**.
- **`status = "Available"`**: Initializes status with the value **`"Available"`**.
- **`status = "Busy"`**: Updates the value of status to **`"Busy"`**.

>[!WARNING]
> Using **`var`** again after **`status`** has been created would give an error as you are trying to create a new variable with a variable name that already exists

### Rules for Naming Variables

When naming variables in Swift, follow these rules:

1. Variable names **must start with a letter (or an underscore _)** and can contain letters, numbers, and underscores.
2. **No spaces** are allowed in variable names. Use naming conventions to improve readability.
3. **Case Sensitivity**: Variable names are case-sensitive. For example, myName and myname are treated as two different variables.
4. **Avoid Reserved Words**: Do not use Swift keywords (like var, let, func) as variable names.

### Naming Conventions in Swift

Using proper naming conventions makes your code easier to read and understand. The preferred naming style in Swift is **camelCase**:

- **Camel Case**: The first word starts in lowercase, and subsequent words begin with an uppercase letter.
Examples: **`myName`**, **`totalScore`**, **`isLoggedIn`**.

Other common conventions:

- **`Pascal Case`**: Every word starts with an uppercase letter, e.g., **`MyName`**. (Not typical for variables in Swift but used for class names.)
- **`Snake Case`**: Words are separated by underscores, e.g., **`my_name`**. (Rarely used in Swift.)

#### Optional Use of Semicolons in Swift

Swift does not require a semicolon (**`;`**) at the end of each line, making the code cleaner and easier to read. However, semicolons can be used in two specific scenarios:

1. Combining Multiple Statements on One Line

    Semicolons allow you to place multiple statements on a single line for better readability or to save space.

    ```swift
    var story = "This is a long story"; var author = "Maged Elesseily"
    ```

2. Treating Two Lines of Code as One Statement

    When a line of code is split into two or more parts, semicolons help Swift recognize them as a single logical statement.

    ```swift
    var longSentence = 
    "it's easier to read when split over multiple lines.";
    ```

## Constants

In Swift, you can store data in a **constant** when you are certain that the value will never change. This is done using the **`let`** keyword.

**Syntax:**

```swift
let character = "Harry"
```

Here, **`let`** creates a constant called **`character`**, and assigns it the value **`"Harry"`**. Once set, **`character` cannot be changed** throughout the program.

### Important Points for constants

1. **Initialization is Required**

    Unlike variables, **constants must be initialized at the time of declaration.** You cannot declare a constant and assign a value to it later:

    ```swift
    let character  // Error: Constant 'character' must have an initial value
    character = "Harry"  // Error: Cannot assign to value: 'character' is a 'let' constant
    ```

2. **Immutable**

    Once a constant is initialized, its value **cannot be changed**. Trying to modify it will result in a compiler error:

    ```swift
    let character = "Harry"
    character = "Hermione"  // Error: Cannot assign to value: 'character' is a 'let' constant
    ```

3. **Memory and Performance Benefits**

- **Memory Optimization:** Constants don't need memory flagged for potential changes, unlike variables. This reduces memory overhead.
- **Compiler Optimizations:** Swift can make performance improvements, such as reordering instructions, when using constants. This cannot be done with variables since their value can change.
- **Safety and Reliability:** By using constants, you eliminate the risk of accidentally changing a value that should remain constant. This makes your code more predictable and reduces the chances of bugs.

> [!NOTE]
> Swift encourages you to use constants for values that do not need to change.

## Strings

In Swift, **strings** are used to store text data, such as names, messages, or even emojis. Strings are enclosed in double quotes (**`"`**), making it easy to represent any text you need.

**Examples:**

```swift

let message = "Welcome to Swift!"  // A simple string
let emojiText = "Coding is fun 😎"  // Emojis are valid in strings
```

### Handling Special Cases in Strings

1. **Including Double Quotes**

    If your string needs to include double quotes inside it, use a **backslash (`\`)** to escape them:

    ```swift
    let quote = "She said, \"Swift makes coding fun!\""
    ```

    This ensures Swift understands that the quotes are part of the text and not the end of the string.

2. **Creating Multiline Strings**

    To span a string across multiple lines, use **three double quotes (""")**. Ensure the opening and closing quotes are on their own lines:

    ```swift
    let multilineString = """
    This is a multiline string.
    You can write across several lines.
    """
    ```

### Common String Operations in Swift

1. **Get the Length of a String**

    Use the **`.count`** property to find how many characters are in a string:

    ```swift
    let name = "Swift"
    print(name.count)  // Output: 5
    ```

2. **Convert to Uppercase**

    Use the **.uppercased()** method to convert all letters to uppercase:

    ```swift
    let lowercase = "hello"
    print(lowercase.uppercased())  // Output: "HELLO"
    ```

#### You might be wondering, what is the `print()` function?

In some cases, you will want to check the value stored in a variable or returned by a function. This is where the **`print()`** function becomes incredibly useful. It outputs the value to the console or terminal, allowing you to see what's happening in your program. This makes it an essential tool for debugging and understanding your code's behavior.

#### Why `.count` vs. `.uppercased()`?

- **`.count`** is a property that provides information (length of the string). It doesn’t require parentheses.
- **`.uppercased()`** is a method that performs an action (converts to uppercase). It requires parentheses to execute.
This distinction will be discussed further as you explore Swift.

There are many string operations available in Swift, which we will explore in more detail in future branches and applications.

## Integers

In Swift, just like storing strings, you can store whole numbers, which are known as **integers**. Integers can be both positive and negative and have a vast range in Swift.

### Declaring, Initializing, and Updating Integers

Declaring and initializing integers works just like strings, and you can also update their value if they are mutable:

```swift
var score = 10   // Declare and initialize
score = 20       // Update the value
print(score)     // Output: 20
```

If the value should not change, use let to create a constant:

```swift
let highScore = 100  // Immutable constant
```

#### Writing Large Numbers

Large numbers can be difficult to read, so Swift allows you to use underscores (_) to make them more readable. These underscores are purely for visual clarity and do not affect the actual value of the number. Swift completely ignores them when interpreting the value:

```swift
let bigInt = 100_000_000  // Easier to read than 100000000
```

However, improper use of underscores can lead to confusion. For example:

```swift
let confusingNumber = 10__00_00  // Still valid
print(confusingNumber)           // Output: 100000
```

Even though this syntax is allowed, it can make your code harder to understand. Always use underscores consistently and sparingly to enhance readability.

### Performing Basic Arithmetic

Swift allows you to perform standard arithmetic operations, just like you learned in school:

```swift
let a = 10
let b = 5

let addition = a + b      // 15
let subtraction = a - b   // 5
let multiplication = a * b // 50
let division = a / b      // 2
```

#### Compound Assignment

You can simplify arithmetic operations by combining them with assignment using compound operators:

```swift
var number = 10

number += 5   // Adds 5 to number: now 15 similar to number = number + 5
number -= 3   // Subtracts 3: now 12
number *= 2   // Multiplies by 2: now 24
number /= 4   // Divides by 4: now 6
```

### Additional Integer Operations

Swift also provides helpful methods for integers. For example, checking if a number is a multiple of another:

```swift
let number = 9
print(number.isMultiple(of: 3))  // Output: true
print(100.isMultiple(of: 3)) // Output: false
```

This method simplifies common tasks, making your code more readable and efficient.

## Doubles

Swift allows you to store floating-point numbers, or doubles, which can represent both very large and very small decimal values (e.g., **`0.000000001`**). These numbers are treated differently from integers to ensure **type safety**.

**Example:**

```swift
let a = 1
let b = 2.0    // b is a double
let c = a + b  // Error: Cannot add integer and double directly
```

In Swift, you cannot directly mix integers and doubles. To fix this, you can either:

1. **Convert the integer to a double:**

    ```swift
    let c = Double(a) + b  // a is now treated as a double
    ```

2. **Convert the double to an integer:**

    ```swift
    let c = a + Int(b)  // b is now treated as an integer
    ```

>[!NOTE]
> Swift decides whether a number is treated as an **integer** or **double** based on whether it contains a decimal point. For example, **`1.0`** is treated as a double because it has a decimal point, even though the value might be the same as an integer **`1`**.

### Arithmetic and Compound Assignment

Doubles can be used with arithmetic operations (**`+`**, **`-`**, **`*`**, **`/`**) and compound assignments (**`+=`**, **`-=`**, **`*=`**, **`/=`**) just like integers.

```swift
var result = 10.5
result += 2.5  // result is now 13.0
```

### Precision in Doubles

Doubles, due to their floating-point nature, are not always 100% accurate. Since they are represented in binary, some decimal numbers cannot be exactly represented.

For example:

```swift
let a = 0.1
let b = 0.2
let c = a + b
print(c)  // Output: 0.30000000000000004
```

This small inaccuracy arises from the way numbers are stored in binary. **While it is usually negligible**, it can cause issues in **precise calculations**.

## Type Safety

Swift enforces **type safety**, meaning once a variable is assigned a value of a specific type, it must always hold that same type. For example:

```swift
var name = "Maged"  // name is a String
name = 10  // Error: Cannot assign an Int to a String variable
```

This helps prevent unexpected behavior in your code by ensuring that variables are always used with the correct data type.
