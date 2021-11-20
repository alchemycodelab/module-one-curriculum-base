# Module 2 - Compound State


## Dropdowns

```html
<select id="my-select">
    <option value="dog-value">Dog Is What The User Sees</option>
    <option value="cat-value">Cat Is What The User Sees</option>
    <option value="pigeon-value">Pigeon Is What The User Sees</option>
</select>
```

```js
const selectEl = document.querySelector('#my-select');

selectEl.addEventListener('change', () => {
    console.log(selectEl.value) // cat-value, dog-value, or pigeon-value
})
```

## Arrays as state

```js
let fruits = ['apple', 'orange'];

myButton.addEventListener('click', () => {
    console.log(selectEl.value) // cat-value, dog-value, or pigeon-value

    // here we mutate the array state
    fruits.push('kiwi')

    // note that, as usual, whenever we update state, we want to update the DOM
    updateListDOM()
})
```


## creating DOM elements

```js
const container = document.querySelector('#container');

const div = document.createElement('div')

div.textContent = 'This is my new, dynamically generated div!'
```

## Rendering lists of things

```js
const container = document.querySelector('#container');

for (let fruit of fruits) {
    container.append(fruit);
}
```

In situations where you expect to _add items to your list of things_, the easiest solution is to clear out the DOM every time you want to add a new item to the list. If you don't it's easy to accidentally duplicate the whole list. It might be a good idea to put all this work into a function.

```js
function refreshList() {
    const container = document.querySelector('#container');

    // it's usually worth clearing out your container element before appending a list to it.
    container.textContent = ''

    for (let fruit of fruits) {
        container.append(fruit);
    }
}
```

We could also refactor this work into two functions:

```js
function refreshList() {
    const container = document.querySelector('#container');

    container.textContent = '';

    const listEl = renderList();

    container.append(listEl)
}

function renderList() {
    const newListEl = document.querySelector('#container');

    for (let fruit of fruits) {
        newListEl.append(fruit);
    }

    return newListEl;
}
```

One of these functions is pure and the other is impure. Which is which?

## Where should functions live?

Impure functions that manipulate existing DOM elements _must_ live in the main .js file. Otherwise, you will cause problems in your test suite down the road.

Pure functions that _create and return new DOM elements_ should probably live in a separate file and imported in.

```js
import { add } from './utils.js'

add(4, 2)
```

```js
export function add(num1, num1) {
    return num1 + num2
}
```

# Deliverable - Dropdown Character Maker

| User should be able to . . .                                                         |             |
| :----------------------------------------------------------------------------------| ----------: |
| Visit the deployed pages on GitHub pages, with link in the About section of the Github repo |    1 |

| Events . . .                                                         |             |
| :----------------------------------------------------------------------------------- | ----------: |
| Select from at least three dropdowns with at least three options each                |           1 |
| On choosing an option from the dropdown and see the change reflected in the UI with a new image |     1 |
| On change, See all catchphrases rendered to the DOM                                             |           1 |
| When submitting a catchphrase, add it to an array of catchphreses, clear the current DOM's list of catchphases, and list all catchphrases in the DOM         |           1 |
| See displayed how many times each dropdown has been changed in the current session   |           1 |

| Functions                                                              |             |
| :----------------------------------------------------------------------------------- | ----------: |
| IMPURE: `renderStatsAndCatchphrases()` | 1 |

