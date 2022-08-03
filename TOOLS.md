## Finite list of tools

#### 1) `let someState = 0`
  - initialize state
#### 2) `const myEl = document.querySelector('.my-class');`
  - grab DOM elements from the HTML
#### 3) `someState++`
  - increment state
#### 4) `myEl.textContent = someState`
  - we display a state change
#### 5) `const userTypedThis = myInputEl.value`
  - get what the user typed
#### 6) `myEl.textContent = myInputEl.value`
  - display what the user typed
#### 7) `myButton.addEventListener('click', () => {})`
  - listen for a click
#### 8) ```myEl.textContent = `this is a ${someState} string template` ```
  - set text content to a dynamic string
#### 9) `myEl.classList.add('some-class')`
#### 10) `if (someState > 10) { /* do something */ }`
  - conditionally use one of your other finite tools
#### 11) `function doStuff() { /* do something */ }`
  - move repeated/complex work into a named function
  - render functions take in an object and return a DOM element
  - display functions mutate the root HTML/DOM
#### 12) `myArrayState.push(newThing)`
  - update array state
#### 13) `Math.floor(Math.random() * 10)`
  - when we need to do stuff randomly

#### Loops) for loop to display a list 
```js
  myParentEl.textContent = '';

  for (let item of items) {
    const myChildEl = document.createElement('div');

        myChildEl.textContent = item;

        myParentEl.append(myChildEl);
      }
```

#### Forms)
    ```js
    form.addEventListener('submit', (e) => {
      e.preventDefault();

      const data = new FormData(form);

      data.get('name-of-field')
    });
    ```
