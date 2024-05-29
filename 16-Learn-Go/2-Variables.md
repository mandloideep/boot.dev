# Ch 2 - Variables

`bool

string

int int8 int16 int32 int64
uint uint8 uint16 uint32 uint64 uintptr

byte // alias for uint8

rune // alias for int32
// represents a Unicode code point

float32 float64

complex64 complex128
`

- We talked about strings and ints previously, and those two types should be fairly self-explanatory. A bool is a boolean variable, meaning it has a value of true or false. The floating point types (float32 and float64) are used for numbers that are not integers -- that is, they have digits to the right of the decimal place, such as 3.14159. The float32 type uses 32 bits of precision, while the float64 type uses 64 bits to be able to more precisely store more digits. Don't worry too much about the intricacies of the other types for now. We will cover some of them in more detail as the course progresses.

- we can only infer the varible types inside a function, outside we need to difine the variable with `var variable_name type`

- Outside of a function (in the global/package scope), every statement begins with a keyword (var, func, and so on) and so the := construct is not available.

- However, when the right hand side is a literal value (an untyped numeric constant like 42 or 3.14), the new variable will be an int, float64, or complex128 depending on its precision:

`i := 42           // int
f := 3.14         // float64
g := 0.867 + 0.5i // complex128`

- Some types can be converted like this:

`temperatureFloat := 88.26
temperatureInt := int64(temperatureFloat)
`

- Casting a float to an integer in this way truncates the floating point portion.

- Constants are declared with the const keyword. They can't use the := short declaration syntax.

`const pi = 3.14159`

- Constants can be character, string, boolean, or numeric values. They can not be more complex types like slices, maps and structs, which are types we will explain later.

- However, constants can be computed as long as the computation can happen at compile time.

For example, this is valid:

`
const firstName = "Lane"
const lastName = "Wagner"
const fullName = firstName + " " + lastName`

- `fmt.Printf` - Prints a formatted string to standard out.
- `fmt.Sprintf()` - Returns the formatted string

-

- `if` statements in Go do not use parentheses around the condition:

`if height > 4 {
    fmt.Println("You are tall enough!")
}
`

- `else if` and `else` are supported as you might expect:

`if height > 6 {
    fmt.Println("You are super tall!")
} else if height > 4 {
    fmt.Println("You are tall enough!")
} else {
    fmt.Println("You are not tall enough!")
}
`
Here are some of the comparison operators in Go:

- `==`equal to
- `!=` not equal to
- `<` less than
- `>` greater than
- `<=` less than or equal to
- `>=` greater than or equal to

- THE INITIAL STATEMENT OF AN IF BLOCK
  An if conditional can have an "initial" statement. The variable(s) created in the initial statement are only defined within the scope of the if body.

`if INITIAL_STATEMENT; CONDITION {
}`

- WHY WOULD I USE THIS?
  This is just some syntactic sugar that Go offers to shorten up code in some cases. For example, instead of writing:

`length := getLength(email)
if length < 1 {
    fmt.Println("Email is invalid")
}`

We can do:

`if length := getLength(email); length < 1 {
    fmt.Println("Email is invalid")
}`

- Not only is this code a bit shorter, but it also removes length from the parent scope, which is convenient because we don't need it there - we only need access to it while checking a condition.
