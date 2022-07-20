# Javascript and the DOM

## What is Javascript?

Programming languages allow us to give instructions to a computer to get it to do things for us. Javascript is a programming language that we can connect to our HTML files which will allow us to make our web pages more interactive. Javascript was originally built to be run in your browser but it can now also be run directly on your computer using Node (you'll learn more about that later in the program). For this module, we are focused on using Javascript, inside our browser, to change things around on our HTML.

## Basic Data Types

Javascript, like all programming languages, has different built in data types, which it uses to store different types of information. Because you can perform different operations on different types of data (think adding two numbers versus concatenating two strings), programming languages need to be able to differentiate between them. In Javascript, we have two main types of objects -- primitives and objects. The primitive data types are:

- Numbers `42`
- Strings `"forty two"`
- Booleans `true`
- `null`
- `undefined`
- `bigint`
- `symbol`

The object data types we'll mostly be using are simple objects which allow us to store key value pairs and arrays which allow us to store ordered lists of things.

```js
// object with key / value pairs
const dog = { name: "Benny", age: 7 };

// array of strings
const dogs = ["Benny", "Jeep", "Ruby"];
```

## What is the DOM?

DOM stands for Document Object Model. When we run Javascript in our browser, we get access to a whole bunch of really cool methods that we can call to access and manipulate the data on our HTML. Basically our browser loads up all the stuff on our HTML and makes available to us in our Javascript file. We will be accessing the DOM methods using the `document` variable.

## Connecting Javascript to HTML

In order to use Javascript in our HTML, we have to tell our HTML page where our Javascript file lives. We will do this using a `<script>` tag.

```html
<script type="module" src="index.js"></script>
```

Technically, you can run Javasript directly on your HTML page using the script tag. For example, add the following snippet to your HTML and open up your developer tools.

```html
<script>
  console.log("hello!");
</script>
```

You should see a greeting on your console! Since it would get pretty messy, pretty quickly to have our JS and HTML all mixed up, we instead move our JS into a separate file and link it using the `src` attribute on the `script` tag as shown above.

# Getting Elements / Setting Elements

## getElementById

We use this method to retrieve a DOM element and store it in Javascript. For example, if we have the following HTML:

```html
// index.html
<div id="name-tag" class="name-tag">
  <section id="top-section" class="top">
    <h1>Hello</h1>
    <h2>my name is</h2>
  </section>
  <section id="name-section" class="middle">Julie</section>
  <section id="bottom-section" class="bottom"></section>
</div>
```

We can access each of these individual elements in our Javascript using their ids:

```js
// app.js
const container = document.getElementById("name-tag");
const nameSection = document.getElementById("name-section");
```

Notice that the string that we pass into the `getElementById` method is the same as the `id` attribute on the HTML.

## DOM manipulation

Once we have an element stored as a variable in Javascript, we can then manipulate that data using built in properties. If I wanted to change the name on this name tag, I could put the following in my Javascript:

```js
const nameSection = document.getElementById("name-section");
nameSection.textContent = "Benny";
```

## Event Listeners

Event listeners allow us to listen for specific user interactions. For example clicking, submitting a form, or typing in an input. The following code would produce an alert, everytime the user clicked on the container.

```js
const container = document.getElementById("name-tag");
container.addEventListener("click", () => {
  alert("the container was clicked!");
});
```
