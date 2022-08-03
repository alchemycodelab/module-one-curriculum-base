# Finite list of tools

## Section One - DOM manipulation
#### 1) `const myEl = document.querySelector('.my-class');`
  - grab DOM elements from the HTML
#### 3) `const userTypedThis = myInputEl.value`
  - get what the user typed
#### 4) `myEl.textContent = myInputEl.value`
  - display what the user typed
#### 5) `myEl.classList.add('some-class')`
  - add a css class to an element
#### 6) `myButton.addEventListener('click', () => {})`
  - listen for a click
#### 7) for loop to display a list 
```js
  myParentEl.textContent = '';

  for (let item of items) {
    const myChildEl = document.createElement('div');

        myChildEl.textContent = item;

        myParentEl.append(myChildEl);
      }
```
#### 8) Get data from a form

```js
form.addEventListener('submit', (e) => {
  e.preventDefault();

  const data = new FormData(form);

  data.get('name-of-field')
});
```

## Section Two - State manipulation
#### 9) `let someState = 0`
  - initialize state
#### 10) `someState++`
  - increment state
#### 11) `myArrayState.push(newThing)`
  - update array state
#### 12) `myEl.textContent = someState`
  - we display a state change
#### 13) ```myEl.textContent = `this is a ${someState} string template` ```
  - set text content to a dynamic string based on state

## Section Three - Fun stuff
#### 15) `if (someState > 10) { /* do something */ }`
  - conditionally use one of your other finite tools
#### 16) `function doStuff() { /* do something */ }`
  - move repeated/complex work into a named function
  - render functions take in an object and return a DOM element
  - display functions mutate the root HTML/DOM
#### 17) `Math.floor(Math.random() * 10)`
  - when we need to do stuff randomly


