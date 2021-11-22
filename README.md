## The Pattern of Patterns

All patterns revolve around these 4 fundamental activities:

|  | Get | Set |
|-----------|----|-------|
| **State** | 1) get State | 2) set State |
| **DOM**| 3) get DOM  |  4) set DOM |

# The 10 Patterns

1) [Jiggle](#1-jiggle)
1) [Event Handler](#2-event-handler)
1) [Render function](#3-render-function)
1) [Display Function](#4-display-function)
1) [Display a list](#5-display-a-list)
1) [Update a list](#6-update-a-list)
1) [Async fetch on 'load'](#7-async-fetch-on-load)
1) [Async update a list on click](#8-async-update-a-list-on-click)
1) [List / Detail](#9-list--detail)
1) [List of clickables](#10-list-of-clickables)

## 1) Jiggle: 

The main .js file for each of your pages should follow this basic format:

- Just
- `import` functions
- Grab DOM with `getElementById`
- `let state` 
- `(add)EventListener` for each event

<!-- ### Examples include: 
- organization of all apps -->

## 2) Event handler 
1) add click listener to a dom element
2) optional: get form info
3) change state
4) update dom

```js
button.addEventListener('click', () => {
    const name = nameInput.value;

    timesClicked++;

    charactereName.textContent = name
    countDiv.textContent = timesClicked;
});
```

<!-- ### Examples include: 
- user interaction in all apps -->

## 3) Render function 

- A pure function that takes in an object and returns an HTML element _without appending it to any external DOM_
- Should always live in a separate file, to be imported then called.

```js
export function renderCat(cat) {
    const catEl = document.createElement('div');
    const nameEl = document.createElement('nameEl');
    const img = document.createElement('img');
    nameEl.textContent = cat.name;
    img.src = cat.image_url;

    catEl.classList.add('cat-box');
    
    catEl.append(nameEl, img);

    return catEl;
}
```

<!-- ### Examples include: 
- soccer scorekeeper renderGame -->

## 4) Display function 
- An impure function that appends to or mutates existing DOM
- Often uses global state
- Often loops or calls render functions. 
- This function may or may not take an argument.
- Must always live in the same file as the DOM elements it grabs and the state it references.
    - Usually not to be imported.

```js
function displayStats() {
    reportEl.textContent = `You have changed the head ${headCount} times, the body ${middleCount} times, and the pants ${bottomCount} times. And nobody can forget your character's classic catchphrases:`;
}

```

<!-- ### Examples include: 
- character creator displayStats -->

## 5) Display a list
1) loop through array
2) for each item render an html element
3) append each element to the dom

```js
    for (let game of pastGames) {
        const gameEl = renderGame(game);

        gameEl.classList.add('past');
        
        pastGamesEl.append(gameEl);
    }
}
```
<!-- 
### Examples include: 
character creator: display catchphrases
Soccer scorekeeper: display game history
Mushroom festival: display friends, display mushrooms -->

## 6) Update a list
1) add (or remove) item to state array
2) clear dom list
3) loop through updated list
4) render and append updated list items to cleared dom

```js
finishGameButton.addEventListener('click', () => {
    const fruit = fruitInput.value;

    fruitsArray.push(fruit);

    displayFruits();
});
```

<!-- ### Examples include:
Character creator: add catchphrase, soccer scorekeeper: add game to history,
mushroom festival: add friend, feed friend, add musroom (exception: no data array) -->

## 7) Async fetch on 'load'
1) add async 'load' listener to the window
2)  await function to fetch data from supabase
3) render and append fetched data to dom

```js
window.addEventListener('load', async() => {
    // fetch all dogs
    const veggies = await getVeggies();

    for (let veggie of veggies) {
        const veggieEl = renderVeggie(veggie);
      // render the dog detail
        veggieListContainer.append(veggieEl);
    }
});
```
<!-- 
### Examples include: 
dog list: get dogs, dog detail get dog
character creator: load character
soccer scorekeeper: load game history
To do app: load todos
bunny app: load families
yawp: load profile, load restaurant -->

## 8) Async update a list on click
    1) add async 'click' listener
    2) await function to manipulate data in supabase
    3) refetch updated data
    4) render and append updated data to dom

```js
button.addEventListener('click', async e => {
    const name = nameInput.value;

    await createLizard(name);

    lizards = await updatedLizards();

    // uses global lizard state to clear and update lizard DOM
    displayLizards();
});
```
<!-- 
### Examples include: 
- soccer scorekeeper: add game to history
- character creator: update character/ add catchphrase
- todo app: add todo, complete todo, delete todos
- bunny app create bunny, delete bunny
- yawp create review, search restaurants -->

## 9) List / Detail 
- list pages display a list where each item contains a link to a detail page about that particular item
- detail pages shows that item's id in the url. Detail pages shows info about just that item


```js
// get the id from URL: www.cool-cats.com/detail/?id=4
const params = new URLSearchParams(window.location.search);
const id = params.get('id');

// use the id to fetch the dog
const cat = await getCat(id);

// render the cat detail
const catDetailEl = renderCatDetail(cat);
catDetailContainer.append(catDetailEl);
```
<!-- 
### Examples include: 
- Dog list detail page, 
- yawp profile page, yawp restaurant page -->

## 10) List of clickables 
- display a list, plus add an event listener to each rendered element inside the loop. Arguably, list/detail is a subset of this pattern with a link instead of an event listener

```js
for (let todo of todos) {
    const todoEl = renderTodo(todo);

    todoEl.addEventListener('click', async () => {
        await completeTodo(todo.id);

        displayTodos();
    });

    todosEl.append(todoEl);
}
```

<!-- ### Examples include:
- Mushroom festival: feed friends
- To do app: complete todo
- Bunny app: delete bunny -->
