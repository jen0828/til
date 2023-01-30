# Programming Paradigms

Programming paradigms are a way to classify programming languages based on their features. Languages can be classified into multiple paradigms( JavaScript and Python are good examples).

Common programming paradigms include:

![paradigm](https://user-images.githubusercontent.com/79845719/215570758-fd0cc8f1-5f52-461d-8633-143e16f45020.png)


## Functional Programming
- Examples : Haskell, F#, Erlang
- Functions are treated as first-class citizens, meaning that they can be assigned to variables, passed as arguments, and returned from other functions.
- Another key concept is the idea of pure functions. A pure function is one that relies only on its inputs to generate its result. And given the same input, it will always produce the same result. Besides, it produces no side effects (any change outside the function's environment).
- Higher-order functions are rarely used in older imperative programming. A traditional imperative program might use a loop to traverse and modify a list. A functional program, on the other hand, would probably use a higher-order “map” function that takes a function and a list, generating and returning a new list by applying the function to each list item.


```
// traditional imperative loop

const numList = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
let result = 0;
for (let i = 0; i < numList.length; i++) {
  if (numList[i] % 2 === 0) {
    result += numList[i] * 10;
  }
}
```

```
// functional programming with higher-order functions

const result = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
               .filter(n => n % 2 === 0)
               .map(a => a * 10)
               .reduce((a, b) => a + b);

```