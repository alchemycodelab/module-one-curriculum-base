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

// it's usually worth clearing out your container element before appending a list to it.
container.textContent = ''

for (let fruit of fruits) {
    container.append(fruit);
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

