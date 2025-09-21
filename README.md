# Golang Notes & Codes

📌 A beginner-friendly repository to learn Go with concise notes and example codes.

---

## 📖 Table of Contents
- [Basics](basics/README.md)
  - [Variables](basics/variables.md)
  - [Functions](basics/functions.md)
- [Concurrency](concurrency/README.md)
  - [Goroutines](concurrency/goroutines.md)
  - [Channels](concurrency/channels.md)
- [Advanced](advanced/README.md)
  - [Error Handling](advanced/error-handling.md)
  - [HTTP Servers](advanced/http-servers.md)
- [Projects](projects/README.md)
  - [CLI Calculator](projects/cli-calculator/)
  - [Todo App](projects/todo-app/)

---

## 🚀 How to Run Code
```bash
go run main.go

```
# **Go Programming Notes**

---

## **1. Hello World**

The simplest Go program prints "Hello World" to the console.

```go
package main

import "fmt"

func main() {
	fmt.Println("Hello world..!")
}

```

**Explanation:**

- `package main`: Defines the package name. `main` package is required for an executable program.
- `import "fmt"`: Imports the `fmt` package used for formatted I/O.
- `func main() {}`: The entry point of the program.
- `fmt.Println()`: Prints text to the console.

**Execution in Terminal:**

```bash
PS X:\golang> go run 01_Hello_world/main.go
Hello world..!

```

---

## **2. Simple Values**

Go supports different types of simple values: integers, floats, strings, and booleans.

```go
package main

import "fmt"

func main() {
	// simple values
	fmt.Println(1)
	fmt.Println(1 + 1)
	// string
	fmt.Println("Hello World")
	// bool
	fmt.Println(true)
	fmt.Println(false)
	// floats
	fmt.Println(10.5)
	fmt.Println(10.5 + 55.5)
	fmt.Println(10.0 / 3.0)
	fmt.Println(10.0 / 3)
}

```

**Explanation:**

- Integers (`int`), floating-point numbers (`float32`, `float64`), booleans (`true/false`), and strings (`"text"`) are basic data types in Go.
- Arithmetic operations like `+` and `/` work on numeric types.

---

## **3. Variables**

Variables store values that can change during program execution.

### **3.1 Declaring Variables**

```go
package main

import "fmt"

func main() {
	var name = "golang"
	var isAdult = true
	var age = 30
	var price = 50.5

	fmt.Println("Name:", name)
	fmt.Println("Is Adult:", isAdult)
	fmt.Println("Age:", age)
	fmt.Println("Price:", price)
}

```

**Explanation:**

- `var variableName = value` declares a variable with type inferred automatically.
- `:=` is shorthand for declaring and initializing a variable:

```go
name := "golang"

```

### **3.2 Specifying Data Type**

```go
var name string
name = "Amit"

```

- If you declare a variable without initializing, **type must be specified**.

---

## **4. Constants**

Constants are immutable values.

```go
package main
import "fmt"

func main() {
	const name = "golang"
	const age = 30
	fmt.Println(age)
}

```

### **4.1 Constant Grouping**

```go
const (
	port = 5000
	host = "localhost"
)

```

- Multiple constants can be grouped for cleaner code.
- Constants cannot use `:=` shorthand.

---

## **5. Loops**

Go has only **one looping construct: `for`**.

### **5.1 Classic For Loop**

```go
for i := 0; i <= 3; i++ {
	fmt.Println(i)
}

```

### **5.2 While Loop Simulation**

```go
i := 1
for i <= 3 {
	fmt.Println(i)
	i++
}

```

### **5.3 Infinite Loop**

```go
for {
	fmt.Println("1")
}

```

### **5.4 Break and Continue**

```go
for i := 0; i <= 3; i++ {
	if i == 2 {
		continue // skips current iteration
	}
	fmt.Println(i)
}

```

```go
for i := 0; i <= 3; i++ {
	if i == 2 {
		break // exits loop
	}
	fmt.Println(i)
}

```

---

## **6. Conditional Statements**

Go supports `if`, `else if`, and `else`.

### **6.1 Basic If-Else**

```go
age := 18
if age >= 18 {
	fmt.Println("Person is an adult..!")
} else {
	fmt.Println("Person is not an adult..!")
}

```

### **6.2 If-Else If-Else**

```go
if age > 18 {
	fmt.Println("Person is an adult..!")
} else if age == 18 {
	fmt.Println("Person is turning into an adult..!")
} else {
	fmt.Println("Person is not an adult....!")
}

```

### **6.3 Inline Variable Declaration**

```go
if age := 20; age >= 18 {
	fmt.Println("person is an adult", age)
} else if age >= 12 {
	fmt.Println("person is teenager", age)
}

```

> ⚠️ Go does not have the ternary operator. Always use if-else.
> 

---

## **7. Switch Statement**

Switch is an alternative to multiple `if-else`.

### **7.1 Basic Switch**

```go
i := 3
switch i {
case 1:
	fmt.Println("one")
case 2:
	fmt.Println("two")
case 3:
	fmt.Println("three")
default:
	fmt.Println("other")
}

```

### **7.2 Multiple Conditions**

```go
switch time.Now().Weekday() {
case time.Saturday, time.Sunday:
	fmt.Println("it's weekend")
default:
	fmt.Println("it's workday")
}

```

### **7.3 Type Switch**

```go
whoAmI := func(i interface{}) {
	switch i.(type) {
	case int:
		fmt.Println("its an integer")
	case string:
		fmt.Println("its a string")
	case bool:
		fmt.Println("its a boolean")
	default:
		fmt.Println("other")
	}
}
whoAmI(55)

```

- Used to determine the **type of a variable at runtime**.

---

### ✅ **Key Points**

1. Go uses `package main` for executable programs.
2. `fmt.Println()` is used for printing output.
3. Variable declaration can use `var` or `:=`.
4. Constants cannot change once defined.
5. Only `for` loops exist; `while` can be simulated.
6. Conditional statements (`if-else`, `switch`) control flow.
7. Switch can handle types, multiple conditions, and default cases.
