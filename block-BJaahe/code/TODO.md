## Closure Exercise

1. Write a function, `outer` that takes an input `string`. Inside the function `outer` define another function expression named `sayHello` which alerts the `input`. `sayHello` should be call immediately after it is defined.

```js

function outer(str) {
  let sayHello = () =>  alert(str);
  return sayHello();
}
```

2. Write a function `delay` that accepts two arguments, a callback and the wait for the time in milliseconds (1000 ms is 1 second). `delay` should return a function that, when invoked waits for the specified amount of time before executing. (Use setTimeout)

```js

function delay(time, cb) {
  return setTimeout(cb, time)
}

function sayHello() {
  alert("hello");
}

```

3. Write a function with a closure. The first function should only take one argument, someone's last name, and return the inner function. The returned `inner` function should take one more argument, someone's first name. When inner function when called it should console.log both the first name and the last name with a space.

```js
function lastName(lastName) {
  return function inner(firstName) {
    console.log(`${firstName} ${lastName}`)
  }
}

let lastNameLee = lastName('lee'); // logs nothing
lastNameLee('Brett'); //logs 'Brett Lee'
```

This function is useful in case you want to create name for multiple people with same last name.

```js
lastNameLee('Jane'); //logs 'Jane Lee'
lastNameLee('Lynne'); //logs 'Lynne Lee'
```

4. Create a `storyWriter` function that returns an object with two methods. One method, `addWords` adds a word to your story and returns the story while the other one, `erase`, resets the story back to an empty string. Here is an implementation:

```js

function storyWriter() {
  let story = "";
  return {
    addWords: function add(str) { story = story.concat(str)},
    
    erase: function remove(str) { story = "";}
  }
}

// Test
let farmLoveStory = storyWriter();
farmLoveStory.addWords('There was once a lonely cow.'); // 'There was once a lonely cow.'
farmLoveStory.addWords('It saw a friendly face.'); //'There was once a lonely cow. It saw a friendly face.'
farmLoveStory.erase(); //''

let storyOfMyLife = storyWriter();
storyOfMyLife.addWords('My code broke.'); // 'My code broke.'
storyOfMyLife.addWords('I ate some ice cream.'); //'My code broke. I ate some ice cream.'
storyOfMyLife.erase(); // ''
```

5. Create a function named `forEach` which accepts one parameter an array. Inside the function `forEach` there a variable named `index` which is initialized to `0`.

When `forEach` function is called it returns another function. When the returned function is called it returns the element from the array at specific index. Every time you call the returned function the value of index should increment.

```js

function forEach(arr) {
  let index = 0;
  return function next() {
    
    let val = index;
    index++;
    if(index >= arr.length) {
      index = 0;
    }
    return arr[val];
    
  }
};

let next = [1, 2, 3, 4, 5];

let getVal = forEach(next);
getVal(); // 1
getVal(); // 2
getVal(); // 3
getVal(); // 4
getVal(); // 5
```

6. Create a function named `addDesignation` which accepts a `title` and returns another function.

The returned function accepts a string `prefix` and returns `prefix` and `title` with a space.

```js

function addDesignation(title) {
  return function nextDesignation(name) {
    return `${name} ${title}`;
  }
}

let sales = addDesignation('Salesman');
sales('Main'); // Main Salesman

let manager = addDesignation('Manager');
manager('Regional'); // Regional Manager
manager('Head'); // Head Manager
```

7. Create a function named `changeSalary` which accepts `currentSalary` (number) and returns an object that contains three methods

- `raise` which will add `500` to the current salary and returns the updated salary
- `lower` will decrease the salary by 500 returns the updated salary
- `current` will return the current salary returns the updated salary

```js

function changeSalary(currentSalary) {

  return {
    raise: function () {currentSalary = currentSalary + 500;},
    lower: function () {currentSalary = currentSalary - 500;},
    current: function() {return currentSalary;}
  }
}

let sam = changeSalary(2000);
sam.raise(); // 2500

let arya = changeSalary(4000);
arya.lower(); // 3500
```

8. Create a function named `nameFactory` which accepts `firstName` and `lastName` and returns an object with multiple functions.

- `getFullName`: return the full name of the person with a space
- `setFirstName`: accepts a parameter first name using which updates the firstName and return the updated full name
- `setLastName`: accepts a parameter last name using which updates the firstName and return the updated full name

```js

function nameFactory(firstName, lastName) {
  return {
    getFullName: function () {return `${firstName} ${lastName}`},
    setFirstName: function(name) {
      firstName = name;
      return `${firstName} ${lastName}`},
    setLastName: function(name) {
      lastName = name;
      return `${firstName} ${lastName}`}
  }
}


let arya = nameFactory('Arya', 'Stark');
arya.getFullName(); // "Arya Stark"
arya.setFirstName('Jon'); // "Jon Stark"
arya.setLastName('Lannister'); // "Jon Lannister"
```

9. Create a function named `createTag` which accepts an HTML element name and returns another function.

The returned function accepts a string (children) and returns the children with the tag you passed.

```js
function createTag(elementName) {
  return function(str) {
    return `<${elementName}>${str}</${elementName}>`
  }
}

let bold = createTag('b');
bold('Hello World!'); // <b>Hello World!</b>

let italic = createTag('i');
italic('Hello World!'); // <i>Hello World!</i>
```
