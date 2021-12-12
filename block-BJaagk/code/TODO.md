1. Convert the function below into different forms of function expression.

```js
function percentage(marks, total) {
  return (marks * 100) / total;
}

// Function Expression
let percentage = function number(marks, total) {return (marks * 100) / total};

// Anonymous function
let percentage = function (marks, total) {return (marks * 100) / total};

// Arrow function 
let percentage = (marks, total) => (marks * 100) / total;
```

2. Write Function Declaration or Function Expression next to the function.

```js
function percentage(marks, total) {
  return (marks * 100) / total;
}
// function declaration
```

```js
let percentage = function percentage(marks, total) {
  return (marks * 100) / total;
};
// function Expression
```

```js
let percentage = function (marks, total) {
  return (marks * 100) / total;
};
//  Anonymous function 
```

```js
let percentage = (marks, total) => {
  return (marks * 100) / total;
};
// Arrow function
```

```js
let percentage = (marks, total) => (marks * 100) / total;
// Arrow function
```

3. Why is a function definition an expression in JavaScript? Give one example of function expression.
- To the right side of equals to (=) there can only be a value. Functions are object and object is expression which leads to value. So we can store function inside a variable. Because they are to right side of equals to in side variable they are called function expression.

```js

const filterOdd = function odd(num) {return num % !== 0};

```


4. Why is a function call an expression in JavaScript?
- To the right side of equals to (=) there can only be a value. function call is expression which leads into value. So we can store function call inside a variable.


5. Write VALID and INVALID next to each example below with the reason.

```js
function add(a, b) {
  return a + b;
}

let five = add(2, 3); // Valid
five = add; // valid
five = five(10, 11); // valid
five = function () {
  return 'Hello';
}; // valid
```

6. What is the difference between function definition and function call? Explain with an example.
-Function Defination = It is creating function with multiple steps in it and accpeting parameter(placeholder) into its defination.
-function call = It is executing the function by passing arguments as real value;

```js

function multiply(num, num2) {
  return num * num2;
}
multiply(5,10);

```

7. What is the similarities between function definition and function call?
- Name of function in defination and while call is only similaries 


8. Is the code below valid or invalid. Explain with reason.

```js
function hello() {
  console.log('Hello World!');
}

hello.user = 'Sam'; // valid
```
- function is an object so we can store value inside the object.


9. What is higher order function explain with an example.
- function which accept function defination or function reference as an argument
- function which return function defination or function reference as an argument.

```js

let numbers = [1,2,3,4,5,6,7,8,9,10];

function isOdd(num) {
  return num % 2 !== 0;
}

function filter(arr, cb) {

  let final = []
  for(let num of arr) {
    if(cb(num)) {
      final.push(num)
    }
  }
  return final;
}
filter(numbers, isOdd);



function first(num){
  return function second(num2) {
    return num * num2;
  }
}

let multiply5 = first(5);
let multiplyBy10 = multiply5(10);


```


10. Explain what is callback function. Why you can pass a function inside a function?
-Function which is passed as argument is call back function.

We can pass expression as argument. So function is expression and it can be passed as argument.
