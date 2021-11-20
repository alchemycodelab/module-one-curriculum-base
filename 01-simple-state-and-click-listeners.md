# Module 3 - Simple State and Event Listeners

## Query Selector 

```js
// these two statements are exactly the same
const myDiv = document.getElementById('my-div');
const myDiv = document.querySelectors('#my-div');
```

## Click handlers

```js
const button = document.querySelector('#my-button');

button.addEventListener('click', () => {
    // 😎 Cool Zone 😎
    // when you click the #my-button button, whatever code you write in the cool zone will execute 

    // (the cool zone is actually called an 'anonymous callback' or maybe a 'click handler')

    // usually, we do 3 things here:
        // 1) get some information
        // 2) use that information to update state
        // 3) update the DOM to reflect these state changes
})
```

## Random numbers

```js
// get a random number between 1 and 10
const randomNumber = Math.floor(Math.random() * 10);

// you could use this random number as an array index. Why would we want to do that?
myArray[randomNumber] 
```

## Functions for Reused Code

There are two kinds of functions:

### Pure Functions

```js
// pure functions are super predictable
// if you pass the same input twice, you will get the same output twice
// all pure functions have return statements
function add(num1, num2) {
    return num1 + num2
}

// because this function has a return statement, we can store (in a variable) whatever result it 'spits out'.
const sum = add(5, 6);
```

### Impure Functions

```js
// notice that this variable is defined _outside the function declaration_
const coolDivFromHTML = document.querySelector('#my-divs)

function mutateCoolDiv(words) {
    // 💥 impure function alert 💥
    // this function mutates something defined _outside the function declaration_
    coolDivFromHTML.textContent = words;

    // 💥 impure function alert 💥
    // no return statement!
}
```


```js
function getRandomNumberBetween0And10(/*💥 impure function alert 💥 no arguments! */) {
    // 💥 impure function alert 💥
    // randomness! no way to predict this
    return Math.random() * 10
}
```

Question: What do you think is easier to test: pure or impure functions? Why?

# Deliverable - Hide and Seek

| User should be able to . . .                                                         |             |
| :----------------------------------------------------------------------------------- | ----------: |
| Visit the deployed pages on GitHub pages, with link in the About section of the Github repo|        1 |
| See three hiding places, with a button beneath each of them.                               |        1 |

| Events . . .                                                         |             |
| :----------------------------------------------------------------------------------- | ----------: |
| On clicking a hiding place button, the total number of guesses increment                         |        1 |
| On clicking the correct hiding place button, the total number of correct guesses increment                       |        1 |
| On click, see the correct hiding place's image change, clearing out the previous correct guess style|1|

| Functions                                                              |             |
| :----------------------------------------------------------------------------------- | ----------: |
| IMPURE: `resetStyles()` | 1 |
| IMPURE: `getRandomItem(arr) : returns random item from given array` | 1 |
| IMPURE: `handleGuess(userGuess, correctSpot)` | 1 |