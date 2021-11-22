# Patterns

The core pattern: 

|  | Get | Set |
|-----------|----|-------|
| **State** | get State | set State |
| **DOM**| get DOM  |  set DOM |

Everything we do falls into one of these 4 activities

# Our 10 patterns:

## 1) Jiggle: 
- Just
- Import 
- Grab DOM with 
- GetElementById
- Let state 
- Event listeners

### Examples include: 
- organization of all apps

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

### Examples include: 
- user interaction in all apps

## 3) Render function 

- A pure function that takes in an object and returns an HTML element _without appending it to any external DOM_

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

### Examples include: soccer scorekeeper renderGame

## 4) Display function 
- An impure function that appends to or mutates existing DOM
- Often uses global state
- Often loops or calls render functions. 
- This function may or may not take an argument.

```js
function resetStyles() {
    shedContainer.classList.remove('face');
    treeContainer.classList.remove('face');
    boulderContainer.classList.remove('face');
}
```

```js
function displayStats() {
    reportEl.textContent = `You have changed the head ${headCount} times, the body ${middleCount} times, and the pants ${bottomCount} times. And nobody can forget your character's classic catchphrases:`;
}

```

### Examples include: character creator displayStats

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

### Examples include: 
character creator: display catchphrases
Soccer scorekeeper: display game history
Mushroom festival: display friends, display mushrooms

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

### Examples include:
Character creator: add catchphrase, soccer scorekeeper: add game to history,
mushroom festival: add friend, feed friend, add musroom (exception: no data array)

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

### Examples include: 
dog list: get dogs, dog detail get dog
character creator: load character
soccer scorekeeper: load game history
To do app: load todos
bunny app: load families
yawp: load profile, load restaurant

## 8) Async create, delete, or update list item on click
    1) add async 'click' listener
    2)  await function to manipulate data in supabase
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

### Examples include: 
- soccer scorekeeper: add game to history
- character creator: update character/ add catchphrase
- todo app: add todo, complete todo, delete todos
- bunny app create bunny, delete bunny
- yawp create review, search restaurants

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

### Examples include: 
- Dog list detail page, 
- yawp profile page, yawp restaurant page

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

### Examples include:
- Mushroom festival: feed friends
- To do app: complete todo
- Bunny app: delete bunny
