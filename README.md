# All basics of Golang Language

## variables

```Golang

	// Boolean type
	var isGoFun bool = true
	fmt.Println("Boolean value:", isGoFun)

	// Integer types
	var intVal int = 42                    // Default integer type (depends on platform architecture)
	var int8Val int8 = -128                // 8-bit signed integer (-128 to 127)
	var int16Val int16 = 32767             // 16-bit signed integer (-32,768 to 32,767)
	var int32Val int32 = 2147483647        // 32-bit signed integer (-2,147,483,648 to 2,147,483,647)
	var int64Val int64 = 9223372036854775807 // 64-bit signed integer (-2^63 to 2^63-1)
	fmt.Println("Integers:", intVal, int8Val, int16Val, int32Val, int64Val)

	// Unsigned integer types
	var uintVal uint = 42                    // Default unsigned integer type (depends on platform architecture)
	var uint8Val uint8 = 255                 // 8-bit unsigned integer (0 to 255)
	var uint16Val uint16 = 65535             // 16-bit unsigned integer (0 to 65535)
	var uint32Val uint32 = 4294967295        // 32-bit unsigned integer (0 to 4,294,967,295)
	var uint64Val uint64 = 18446744073709551615 // 64-bit unsigned integer (0 to 2^64-1)
	fmt.Println("Unsigned Integers:", uintVal, uint8Val, uint16Val, uint32Val, uint64Val)

	// Floating-point types
	var float32Val float32 = 3.14  // 32-bit floating-point number
	var float64Val float64 = 3.141592653589793 // 64-bit floating-point number
	fmt.Println("Floats:", float32Val, float64Val)

	// Complex number types
	var complex64Val complex64 = 1 + 2i    // 64-bit complex number
	var complex128Val complex128 = 3.14 + 2.71i // 128-bit complex number
	fmt.Println("Complex numbers:", complex64Val, complex128Val)

	// String type
	var str string = "Hello, Go!"
	fmt.Println("String:", str)

	// Rune type (alias for int32, represents a Unicode code point)
	var runeVal rune = 'G'
	fmt.Println("Rune (character):", runeVal)

	// Byte type (alias for uint8, represents a single byte)
	var byteVal byte = 255
	fmt.Println("Byte:", byteVal)

       // normal way
       var carType string = "BMW"
       // let go give the type
       carType := "BMW"
       // one line declaration

       // normal way
       var carType string = "BMW"
       // let go give the type
       carType := "BMW"
       // one line declaration
       car,price := "BMW",20_000_000


```

## Printf and scanf


```Golang

 // Declare variables for different types
    var i int
    var f float64
    var str string
    var b bool
    var any interface{}

    // Scanning inputs
    fmt.Println("Enter an integer:")
    fmt.Scanf("%d", &i) // Scans an integer

    fmt.Println("Enter a float:")
    fmt.Scanf("%f", &f) // Scans a float

    fmt.Println("Enter a string:")
    fmt.Scanf("%s", &str) // Scans a string

    fmt.Println("Enter a boolean (true/false):")
    fmt.Scanf("%t", &b) // Scans a boolean

    fmt.Println("Enter any value (default representation):")
    fmt.Scanf("%v", &any) // Scans any value

    // Printing the values using various format specifiers
    fmt.Printf("Integer (%%d): %d\n", i)
    fmt.Printf("Float (%%f): %.2f\n", f) // prints float with 2 decimal places
    fmt.Printf("String (%%s): %s\n", str)
    fmt.Printf("Boolean (%%t): %t\n", b)
    fmt.Printf("Default representation (%%v): %v\n", any)

    // Using %T to print the type of a variable
    fmt.Printf("Type of any (%%T): %T\n", any)

```

## conditionals

```Golang
if height >4 {
	fmt.Println("Your height is more than 4")
} 
else if height <4 {
fmt.Println("Your height is more than 4")
}
else
{
	fmt.println("Your height = 4")
}
// the variable now is accessable on this if statement only
if length := len(str); length < 1 {
	fmt.Printf("Str is empty")
}

```

## switch

```go
switch x {
    case 1:
        fmt.Println("x is 1")
    case 2:
        fmt.Println("x is 2")
    case 3:
        fmt.Println("x is 3")
    default:
        fmt.Println("x is unknown")
    }

```






## functions

```Golang

func add(x, y int) int { // 10 20
	return x + y
}
func subtract(x, y int) int { // 30 40
	return x - y
}


func calculator(x1, y1 int, func1 func(x1, y1 int) int, x2, y2 int, func2 func(x2, y2 int) int, op string) int {
	switch op {
	case "+":
		return func1(x1, y1) + func2(x2, y2)
	case "-":
		return func1(x1, y1) - func2(x2, y2)
	case "*":
		return func1(x1, y1) * func2(x2, y2)
	case "/":
		// Handle division by zero
		if func2(x2, y2) == 0 {
			fmt.Println("Error: Division by zero")
			return 0
		}
		return func1(x1, y1) / func2(x2, y2)
	default:
		fmt.Println("Error: Invalid operation")
		return 0
	}
}

x1, y1 , x2 , y2 := 10, 20,30,40

fmt.Println(calculator(x1, y1, add, x2, y2, subtract, "+"))

//output 20
/*************************************/

func getname() (string, string) {
	return "Girgis", "GARMA"
}

name1 , _ :=getnames()
println(name1)



```

```diff
func explicitReturn() (age int , name string){
 	name,age := "girgis",20
-      return name , age
+ 	return 
}
println(explicitReturn()) 
// output : name , age
// both of this syntax will work


```


## struct 

```go
type user struct {
	name  string
	age   int
}

var usr user 

usr.name = "Girgis"
usr.age = 20

fmt.Println(usr)

// struct to use once

myCar := struct {
	make string
	model string
}{
	make: "tesla"
	model : "model 3"
}




```







