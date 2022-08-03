# Finite list of tools

## Section One - DOM manipulation
#### 1) `const myEl = document.querySelector('.my-class');`
  - grab DOM elements from the HTML
#### 2) `const userTypedThis = myInputEl.value`
  - get what the user typed
#### 3) `myEl.textContent = myInputEl.value`
  - display what the user typed
#### 4) `myEl.classList.add('some-class')`
  - add a css class to an element
#### 5) `myButton.addEventListener('click', () => {})`
  - listen for a click
#### 6) for loop to display a list 
```js
  myParentEl.textContent = '';

  for (let item of items) {
    const myChildEl = document.createElement('div');

        myChildEl.textContent = item;

        myParentEl.append(myChildEl);
      }
```
#### 7) Get data from a form

```js
form.addEventListener('submit', (e) => {
  e.preventDefault();

  const data = new FormData(form);

  data.get('name-of-field')
});
```

## Section Two - State manipulation
#### 8) `let someState = 0`
  - initialize state
#### 9) `someState++`
  - increment state
#### 10) `myArrayState.push(newThing)`
  - update array state
#### 11) `myEl.textContent = someState`
  - we display a state change
#### 12) ```myEl.textContent = `this is a ${someState} string template` ```
  - set text content to a dynamic string based on state

## Section Three - Fun stuff
#### 13) `if (someState > 10) { /* do something */ }`
  - conditionally use one of your other finite tools
#### 14) `function doStuff() { /* do something */ }`
  - move repeated/complex work into a named function
  - render functions take in an object and return a DOM element
  - display functions mutate the root HTML/DOM
#### 15) `Math.floor(Math.random() * 10)`
  - when we need to do stuff randomly


