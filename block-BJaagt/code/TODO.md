Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

Example:

```js
function hello() {
  var username = 'Arya';
}
console.log(username); // output
```

In above code we are looking for the variable named `usename`. There is no variable named `username` in the global scope. The variable is inside the function named `hello` and we can't access the variable defined inside a function from outside.

The above code will throw an error `Reference Error username is not defined`.




2. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
{
  const username = 'Arya';
}
console.log(username); // username is not defined
```

In above code we are looking for the variable named `usename`. There is no variable named `username` in the global scope. The variable is inside the object and we can't access the variable defined inside a object from outside.

The above code will throw an error `Reference Error username is not defined`.





3. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
if (true) {
  let username = 'Arya';
}
console.log(username); // username is not defined
```


In above code we are looking for the variable named `usename`. There is no variable named `username` in the global scope. The variable is inside the object and we can't access the variable defined inside a object from outside.

The above code will throw an error `Reference Error username is not defined`.





4. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
if (true) {
  var username = 'Arya';
}
console.log(username); // Arya
```

In above code we are looking for the variable named `usename`. There is no variable named `username` in the global scope. The variable is inside the object and and it is defined with var and var is only function scope not object scope so it has access from out side of object

The above code will return `Arya`.





5. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = 'John';
if (true) {
  var username = 'Arya';
}
console.log(username); // username is already decleared
```
In above code we have defined  variable name `username` using let and var is not object scope so inside object we can not create variable of same name which is already defined using let and const.

code will return `syntaxError: Identifier 'username' has already been decleared`




6. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = 'John';
if (true) {
  let username = 'Arya';
}
console.log(username); // John
```

In above code we have defined variable name `username` using let and also defined `username` inside object. let is object scope so inside object we can create variable of same name which is already defined using let and const.

code will return `john`.





7. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
let username = 'John';
function sayHello() {
  let username = 'Arya';
}
sayHello();
console.log(username); // John
```
In above code `username` is defined using let in global scope and in function. let is object and function scope so we can define variable which is already defined in global scope. but console log will show username of global scope because username inside function will not have access from out side 

code will return `john`




8. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
for (var i = 0; i < 10; i++) {
  console.log(i, 'First'); // 9
}
console.log(i, 'Second'); // 10
```
In above code i is defined using var in object so console log inside object will return `i value from 0 to 9.` and console log out side object will take last i inside object and add one in that i because there is i++ and it will return `10`.





9. Go through the code below and write down the process of making decision about looking for the variable. Also write the output of the code below.

```js
for (let i = 0; i < 10; i++) {
  console.log(i, 'First'); // 0,1,2,3,4,5,6,7,8,9
}
console.log(i, 'Second'); // `referenceError: i is not defined.`
```
In above code i is defined in side object so first console log will show all `i value from 0 to 9.` and console log out side object will not access i so it will return `referenceError: i is not defined.`