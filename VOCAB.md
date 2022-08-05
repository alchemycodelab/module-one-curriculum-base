## object

This is the data type for complex "things" like dogs, products, or friends. Objects can have lots of properties, like name, hair color, birthday, etc.

We can access properties with a dot.

We can change or add properties with a single `=`.

```js
const dog = { name: 'jeep', age: 2 }

// this is getting a property
dog.name
dog.age

// this is settting a property
dog.is_cool = true
```

## DOM

DOM stands for Document Object Model. It is the magic bridge that connects HTML and JavaScript.

The DOM is simply an HTML document turned into a Javascript Object, so we can get and set properties like any object.

We use the DOM to create new HTML and modify existing HTML, displaying our data to the user.

```js
const myElement = document.getElementById('my-element');

myElement.textContent = 'new words that will show up and the user can see it';
```

## document.querySelector

This is an alternative to `document.getElementById`.

Except, instead of an id, it can eat anything that css can eat.

`document.querySelector('.my-class-name'`)` will grab the first element with this class name.

`document.querySelector('#my-d')` will grab the first element with this id.

`document.querySelector('div')` will grab the first div.

## myElement.classList.add()

This simply adds a css class to a DOM element. 

This is how we can dynamically change the styles of an HTML element, without hard coding the `class="my-class"` piece.

## array

This is the data type for "lists of things". 

We access particular items by their number in line, which is called an 'index'. 

`0` is the first index.

```js
const fruits = ['kiwi', 'lemon', 'apple']

const secondFruit = fruits[1]
```

## loop

When you want to do the same thing one by one to every item in an array.

Most commonly, we use this when we want to show the user a list of items.

```js
const parentEl = document.getElementById('parent-el');

parentEl.textContent = '';
for (let item of items) {
  const myChildEl = document.createElement('div');

  myChildEl.textContent = item;

  myParentEl.append(myChildEl);
}
```

## request/response cycle

Clients (usually, the user's computer) make requests to servers. Requests are like text messages--it's how a computer talks to another computer.

Servers (any other computer on the internet) are computers that listen for requests. When a server receives a request, it do work, and then gives a response back to the client.

## return value and arguments

In functions, `input` is called `arguments` or `parameters`.

There are two stages of a function: `declaration` and `calling`. 
- When I `declare` a function, I am building the juicer. 
- When I `call` a function, I am shoving fruits and vegetables (`arguments`) into the juicer (`function`) in order to create some juice (`output`).

```js
function makeHelloString(name) {
    return 'Hello, ' + name + '!'
}

makeHelloString('kati') // 'Hello kati!'

// return value can be stored in a const to be used later

const greeting = makeHelloString('kati')

// let's use the variable we made!
alert(greeting);
```

## Pure function

A pure function has:
1) at least one argument
2) a return value based on that argument
3) A predictable outcome (so `Math.random()` is not pure)
4) no "side effects". Another way to say that: it does not mutate anything defined outside the function.

As a rule, pure functions can (and should) be relocated to another file and imported for the sake of readability.

## Impure functions

Impure functions are 
1) functions with no input 
2) or functions with no return value, 
3) or functions where the output is not predictable. 
4) or functions that mutate something defined outside the function.

Anything that depends on the current date, or a random number, or the user's favorite food, or anything else _outside the function_ counts as an impure function.

As a rule, impure functions are harder to move into their own file without creating a sea of undefined variables.

Impure functions are hard to test.

```js
const anchorDiv = document.getElementById('anchor-div');

function showDate() {
    anchorDiv.textContent = new Date();
}
```
