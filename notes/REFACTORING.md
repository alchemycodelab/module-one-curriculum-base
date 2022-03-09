Refactoring
===

If it works, you're only halfway there.

Code is _read_ ten times more than it is _written_. Who cares if it works? We need it to be _maintanable_.

!()[./wtf.png]
Decisions you make today, you (or somebody) will have to live with in 6 months. 
    - Every line of code is _signed forever_. If you write something confusing, future developers will immediately learn and curse your name.

## Refactoring basics

1) Store repeated or duplicate code in functions or variables, and assign them simple, human-readable names.
    - Favor DRY (Don't Repeat Yourself) code over WET code (Write Everything Twice)
    - Every time you copy and paste, you introduce a new possibility for error
    - If you write it in one place and refer to it by name later, you only have to make changes in one place later.
1) Store complex and ugly code in functions
    - Keep the engine under the hood.
    - Keep all the scary monsters in the basement where they cannot hurt casual onlookers.
1) Store magic numbers and magic strings in variables 
    - For example, define a variable called `salesTax` instead of just copying and pasting `.06` throughout your code.
1) If all else fails, write comments to clarify the intent or purpose of code.


## Casserole Code

![](./casserole.png)

1) One big file of robot guts
1) To outsiders it looks like a mess
    - If you didn't cook it, it's basically impossible to find, fix, or focus on one piece of the dish
    - Cnce you step away from the casserole for a few days, you have _become an outsider_. 
1) But hey, I guess it works!
    - _Just don't touch anything!_

![](./garbage.png)

```js
const sauce = localStorage.getItem('SAUCE') || 'red'; 
const defaultToppings = [
    'garlic',
    localStorage.getItem('IS_VEGAN') ? 'nutritional yeast' : 'cheese',
    localStorage.getItem('IS_VEGETARIAN') ? 'peppers' : 'pepperoni',
];

const oven = new Oven({ 
    base: dryIngredients
        .slice(0, 3)
        .reduce((acc, curr) => acc + curr + Math.random()), 
    [sauce]: wetIngredients
        .filter(item => !item.isExpired)
        .reduce((acc, curr) => { ...acc, [curr]: curr.length }), 
    toppings: new Ingredients([
    ...defaultToppings,
    ...toppings,
    ])})


car.startEngine()
    .then(driver => driver.drive(oven.cookPizza())
    .then(register => {
        register.addMoney(money)

        return 'another satisfied customer!'
    })
```


##  Bento Box code 

![](./bento.png)

1) Easy to understand
1) Clarity of purpose  
    - code is well named and sometimes commented if naming isn't enough
1) Divided up into named parts
    - often, code is `import`ed and `export`ed to and from in many different files

```js
import {
    makeDough, 
    makeSauce, 
    assemblePizza, 
    cookPizza, 
    deliverPizza, 
    addMoneyToRegister,
} from './pizzaUtils.js';

    const dough = makeDough(dryIngredients);
    const sauce = makeSauce(wetIngredients);
    const rawPizza = assemblePizza(dough, sauce);
    const cookedPizza = cookPizza(rawPizza);

    deliverPizza(cookedPizza, address);
    addMoneyToRegister(money);
}
```

# Importing and exporting code


Imagine the following file structure:

```
my-project
    |
    --- utils.js // functions live here
    --- app.js // we import them here!
```


`utils.js`

Here, we will define all of our (imaginary) util functions, ane export them to be used in other files.

```js
export function makeGreeting() {
    // imagine greeting logic here
}

export function sendEmail(greeting) {
    // imagine some email logic here

}
```


`app.js`

Here, we will import all of our util functions and use them inside of an event listener.

```js
import { makeGreeting, sendEmail } from './utils.js'

const button = document.querySelector('#my-button')

button.addEventListener('click', () => {
    const geeting = makeGreeting();
    sendEmail(greeting);
})
```
