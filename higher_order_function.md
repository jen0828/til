# Higher Order Function

A function which takes another function as an argument or returns a function such as map, filter, reduce etc.

![Screenshot 2023-02-28 at 1 23 54 pm](https://user-images.githubusercontent.com/79845719/221868719-5023b9d7-a669-4ba9-8cf6-5f3ce6b9a307.png)

```
function minSum(arr) {
  const sortedArr = arr.sort((a, b) => a - b);
  
  let sum = 0;
  for (let i = 0; i < arr.length / 2; i++) {
    sum += sortedArr[i] * sortedArr[sortedArr.length - 1 - i];
  }
  return sum;
}

```

```
# Refactor - using higher order functions take another function as an argument

function minSum(arr) {
  arr.sort((a, b) => a - b);
  return arr.slice(0, arr.length/2).reduce((acc, val, i) => acc + val * arr[arr.length - 1 - i], 0);
}

```

```
# Return a function from another function 

function calculate(operation) {
  switch (operation) {
    case "ADD":
      return function (a, b) {
        console.log(`${a} + ${b} = ${a + b}`);
      };
    case "SUBTRACT":
      return function (a, b) {
        console.log(`${a} - ${b} = ${a - b}`);
      };
  }
}

const calculateAdd = calculate("ADD");
console.log(calculateAdd);

// Output: 
// [Function (anonymous)]

const calculateAdd = calculate("ADD");
calculateAdd(2, 3);
// Output: 2 + 3 = 5


const calculateSubtract = calculate("SUBTRACT");
calculateSubtract(2, 3);
// Output: 2 - 3 = -1


```