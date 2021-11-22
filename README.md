# Patterns

The core pattern: 
- Get state, 
- set state, 
- get dom,
- set dom.

Everything we do falls into one of these 4 activities

# Our 10 patterns:

## 1) Jiggle: 
- Just
- Import, 
- Grab DOM with 
- GetElementById, 
- Let state, 
- Event listeners

Ex: all apps

## 2) Event handler - 
    1) add click, submit, load listener to a dom element
    2) optional: get form info
    3) change state,
    4) update dom

Ex: all apps

## 3) Render function 

- pure function takes in object, returns html element without appending it to the DOM

Ex: soccer scorekeeper renderGame

## 4) Display function 
- impure function, uses global state to append to existing dom, or otherwise mutate existing dom, often looping or calling render functions

Ex: character creator displayStats

## 5) Display a list -
   1) loop through array
   2) for each item render an html element
  3) append each element to the dom

Ex: 
character creator: display catchphrases
Soccer scorekeeper: display game history
Mushroom festival: display friends, display mushrooms

## 6) update a list -
    1) add (or remove) item to state array, 
   2) clear dom list, 
   3) loop through updated list, 
   4) render and append updated list items to cleared dom

Ex:
Character creator: add catchphrase, soccer scorekeeper: add game to history,
mushroom festival: add friend, feed friend, add musroom (exception: no data array)

## 7) Async fetch on 'load'
    1) add async 'load' listener to the window
    2)  await function to fetch data from supabase
    3) render and append fetched data to dom

Ex: 
dog list: get dogs, dog detail get dog, 
character creator: load character, 
soccer scorekeeper: load game history
To do app: load todos, 
bunny app: load families,
yawp: load profile, load restaurant

## 8) Async create, delete, or update list item on click
    1) add async 'click' listener
    2)  await function to manipulate data in supabase
    3) refetch updated data
    4) render and append updated data to dom

Ex: 
soccer scorekeeper: add game to history,
character creator: update character/ add catchphrase, 
todo app: add todo, complete todo, delete todos, 
bunny app create bunny, delete bunny, 
yawp create review, search restaurants

## 9) List / Detail 
- list pages display a list where each item contains a link to a detail page about that particular item, with that item 's id in the url. Detail pages shows info about just that item

Ex: 
Dog list detail page, 
yawp profile page, yawp restaurant page

## 10) List of clickables 
- display a list, plus add an event listener to each rendered element inside the loop. Arguably, list/detail is a subset of this pattern with a link instead of an event listener

Ex:
Mushroom festival: feed friends
To do app: complete todo
Bunny app: delete bunny
