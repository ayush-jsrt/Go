# Go

Go is a compiled language. Some of its feautres would be:
  - compiled
  - runs in native binaries
  - it has a garbage collector
  - comparable to languages like rust and c++.

Here's a simple example of a Go program that demonstrates basic syntax, variables, functions, conditionals, and loops:

```go

import (
	"fmt"
)

// Function to add two integers
func add(a int, b int) int {
	return a + b
}

// Function to check if a number is even
func isEven(n int) bool {
	return n%2 == 0
}

func main() {
	fmt.Println("Welcome to Go!")

	// Variables
	var name string = "Ayush"
	age := 25 // Short variable declaration

	fmt.Printf("Name: %s, Age: %d\n", name, age)

	// Calling a function
	sum := add(10, 20)
	fmt.Println("Sum:", sum)

	// Loop and condition
	for i := 1; i <= 5; i++ {
		if isEven(i) {
			fmt.Printf("%d is even\n", i)
		} else {
			fmt.Printf("%d is odd\n", i)
		}
	}
}
```

### How to run:

  - Save it to a file, e.g.,`main.go`.
  - Run it using:

```sh
CopyEditgo run main.go
```

Want a specific kind of example (web server, concurrency, file handling, etc.)?









<br><br>

## Running a Go program
When you run a Go program using the`go`command, several things can happen depending onwhich subcommandyou use. The`go`command is the entry point to the Go toolchain. Here’s a quick overview of what happens with common usages:

### 🔹 go run 

Purpose:Compiles and runs the Go program in one step.

What happens:

  - The Go compiler compiles the`.go`file(s) into a temporary binary.
  - The temporary binary is executed.
  - After execution, the temporary binary is deleted.

> ✅ You use this during development to quickly test programs.

### 🔹 go build  or go build in a directory

Purpose:Compiles the program into a binary, but does not run it.

What happens:

  - The Go compiler compiles the code.
  - It produces an executable binary (e.g.,`main.exe`on Windows,`main`on Linux/Mac).
  - No execution happens.

> ✅ Use this to build binaries for deployment or testing.

### 🔹 go install

Purpose:Builds and installs the binary into your`$GOPATH/bin`or module-aware`bin`directory.

What happens:

  - The code is compiled.
  - The binary is placed in the system's Go bin path.
  - You can run the binary globally if that path is in your`$PATH`.

> ✅ Use this to install tools or your own programs for global access.

### 🔹 go test

Purpose:Runs unit tests in your Go project.

What happens:

  - Test files (`*_test.go`) are compiled into a test binary.
  - That binary is run, and the test output is shown.

> ✅ Great for testing functions and packages.

### 🔹 go mod tidy / go mod init / go mod download

Purpose:Manage Go modules and dependencies.

Each does:

  - `go mod init`: Initializes a Go module.
  - `go mod tidy`: Adds/removes required dependencies.
  - `go mod download`: Downloads dependencies.

### Summary Table

| Command | Compiles | Executes | Installs Binary |
|---|---|---|---|
| go run | ✅ | ✅ | ❌ |
| go build | ✅ | ❌ | ❌ (just creates binary) |
| go install | ✅ | ❌ | ✅ |
| go test | ✅ | ✅ | ❌ |









<br><br>

## Keywords

Go (Golang) has a small and clean set of25 keywords. These arereserved wordsand cannot be used as names for variables, functions, or anything else.

### ✅ Go Keywords (25 total):

#### 1. Control flow
```
if       else      switch    case
for      fallthrough    default
```

#### 2. Declarations and Definitions
```
var      const     func     type
import   package
```

#### 3. Concurrency
```
go       select     chan     defer
```

#### 4. Structuring and Error Handling
```
return   break     continue
```

#### 5. Interface and Pointers
```
interface     map      range
```









<br><br>

## Predeclared Types

These are built into the language and can be used directly, but they are not reserved keywords(you can technically shadow them, but it's discouraged).

#### 🔹 Numeric Types

  - `int`,`int8`,`int16`,`int32`,`int64`
  - `uint`,`uint8`,`uint16`,`uint32`,`uint64`,`uintptr`
  - `float32`,`float64`
  - `complex64`,`complex128`

#### 🔹 Boolean Type

  - `bool`→ Values:`true`or`false`

#### 🔹 String Type

  - `string`→ UTF-8 encoded text

#### 🔹 Other Types

  - `byte`→ alias for`uint8`
  - `rune`→ alias for`int32`, used for Unicode code points
  - `error`→ interface type for errors
