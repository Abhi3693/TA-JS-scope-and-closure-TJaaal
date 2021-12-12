Create a execution context diagram of the following code on your notebook. Take a screenshot/photo and store it in the folder named `img`. Use `![](./img/image-name.png)` to display it here.

- Take in account the different phases of execution, different execution contexts

1.

```js
var species = 'human';

function change() {
  var species = 'vampire';
  console.log(species);
}

console.log(species); // 1
change();
console.log(species); // 2
```

<!-- Put your image below -->

`![](./img/img-1.png)`

- Create the execution context diagram
- What will be the value of species on 1 and 2
1 - human
2 - human

2.

```js
var topLevelVar = 'This is global scope!';

function topLevelFn() {
  var localVar = "This is local to topLevelFn's scope";

  function nestedFn() {
    var anotherLocalVar = "Local to nestedFn's scope.";

    console.log(localVar); // 1
    console.log(topLevelVar); // 2
  }

  nestedFn();
}

topLevelFn();
```

<!-- Put your image below -->

`![](./img/img-2.png)`

- Create the execution context diagram
- What will be the value of 1 and 2
1 - "This is local to topLevelFn's scope"
2 - 'This is global scope!'



3.

```js
var one = 'One';
var two = 'Two';

function main() {
  var three = 'Three';

  function inner() {
    var four = 'Four';

    console.log(one); // 1
    console.log(two); // 2
    console.log(three); // 3
  }
  console.log(four); // 4
  inner();
}

main();
console.log(one, two, three, four); // 5
```

<!-- Put your image below -->

`![](./img/img-3.png)`

- Create the execution context diagram
- What will be the value of 1, 2, 3, 4 and 5 or error if the code does not work
1 - One
2 - two
3 - Three
4 - four is not defined
3 - three and four is not defined