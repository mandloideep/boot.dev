# Ch 1 - Go is Fast, Simple and Productive

GO compiles faster than C and Rust but it is not as fast as C and Rust in Runtime because it is a Garbage Collected language.

Structure of GO Program:

- Package Main is the starting point of the Program and it lets go compiler know that we want this code to compile and run as STANDALONE PROGRAM, as opposed to being a library that's imported by other programs

- `import fmt` is formating package that is included in std lib of go

- `func main()` is the entry point of the program

- Its a strongly typed language and it can only concatenate same types, we can use type casting to concatenate different types of variables

- Go programs are fairly lightweight. Each program includes a small amount of "extra" code that's included in the executable binary. This extra code is called the Go Runtime. One of the purposes of the Go runtime is to clean up unused memory at runtime.
