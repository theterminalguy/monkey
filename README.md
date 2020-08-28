# monkey

monkey is an experimental programming language with the following features:

- C-like syntax
- variable bindings
- integers and booleans
- arithmetic expressions
- built-in functions
- first-class and higher-order functions
- closures 
- a string data structure
- an array data structure
- a hash data structure

# Example

1. Binding values to names in monkey

```
let age = 10;
let name = "monkey";
let result = age * 2;
```

2. Biding an array of integers

```
let fiboSequence = [0, 1, 1, 2, 3, 5, 8, 13]
```

3. A hash 

```
let album = { name: "Thriller", artist: "Micheal Jackson", release: "November 30, 1982" }
```

4. Accessing the elements in arrays and hashes is done with index expressions

```
fiboSequence[0]     // => 1
album["artist"]     // => "Micheal Jackson"
```

5. The let statements can also be used to bind functions to names. 

```
let add = fn(a, b) { return a + b; };
```

monkey also supports **implicit return** 

```
let add = fn(a, b) { a + b };
```

calling a function is as easy as you'd expect:

```
add(1, 2);
```

# More on functions

A more complex function such as a fibonacci function that returns the Nth Fibonacci number, might look like this:

```
let fibonacci = fn(x) {
  if(x == 0) {
    0
  } else {
    if (x == 1) {
      1
    } else {
      fibonacci(x - 1) + fibonacci(x - 2);
    }
  }
}
```

**Note:** The recursive calls to `fibonacci` itself!

## Hight order functions

monkey supports functions as arguments a.k.a **first class functions**. Here is an example

```
let twice = fn(f, x) {
  return f(f(x));
};

let addTwo = fn(x) {
  return x + 2;
};

twice(addTwo, 2);   // => 6
```

Here twice takes two arguments: another function called **addTwo** and the integer 2. It calls addTwo two times with first 2 as argument and then with the return value of the first call. The last line produces 6.
