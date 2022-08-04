#### object

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

#### DOM

DOM stands for Document Object Model. It is the magic bridge that connects HTML and JavaScript.

The DOM is simply an HTML document turned into a Javascript Object, so we can get and set properties like any object.

We use the DOM to create new HTML and modify existing HTML, displaying our data to the user.

```js
const myElement = document.getElementById('my-element');

myElement.textContent = 'new words that will show up and the user can see it';
```

#### document.querySelector

This is an alternative to `document.getElementById`.

Except, instead of an id, it can eat anything that css can eat.

`document.querySelector('.my-class-name'`)` will grab the first element with this class name.

`document.querySelector('#my-d')` will grab the first element with this id.

`document.querySelector('div')` will grab the first div.

#### myElement.classList.add()

This simply adds a css class to a DOM element. 

This is how we can dynamically change the styles of an HTML element, without hard coding the `class="my-class"` piece.

#### array

This is the data type for "lists of things". 

We access particular items by their number in line, which is called an 'index'. 

`0` is the first index.

```js
const fruits = ['kiwi', 'lemon', 'apple']

const secondFruit = fruits[1]
```

#### loop

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


