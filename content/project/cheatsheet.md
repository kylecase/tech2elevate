
# Shopping Cart Cheatsheet


## HTML Tags

```html
<div class="shopping-cart"></div>
```
- A **division** tag groups other HTML elements.
- The `class` attribute applies predefined CSS styles.

Other common tags:
- `<p>This is a paragraph tag</p>`
- `<h1>Header One</h1>`
  - Largest header tag (use `<h2>`, `<h3>`, etc. for smaller headers).
- `<img src="/images/products.png" alt="Products image" />`
  - `src` specifies the image file location.
  - `alt` provides alternate text if the image fails to load.

---

## Common CSS Properties

| Property          | Description                                     |
|-------------------|------------------------------------------------|
| `color`           | Changes text color                              |
| `background-color` | Changes background color of an element        |
| `font-size`       | Sets size of text                               |
| `text-align`      | Aligns text inside an element (`center`, `left`, `right`) |
| `padding`         | Adds space inside element (between content and border) |
| `margin`          | Adds space outside element (separates from other elements) |
| `display`         | Defines element behavior (`block`, `flex`)    |
| `gap`             | Adds space between items inside a flex container |

### Example class

```css
.body {
  font-family: Arial, sans-serif;
  margin: 0;
  text-align: center;
}
```
- The dot character indicates a class selector.

---

## JavaScript Basics


### Comparison Operators

| Operator | Meaning                      |
|----------|------------------------------|
| `==`     | equal to                    |
| `===`    | equal value and equal type  |
| `!=`     | not equal                   |
| `!==`    | not equal value or type     |
| `>`      | greater than                |
| `<`      | less than                   |
| `>=`     | greater than or equal to    |
| `<=`     | less than or equal to       |

### Arithmetic Operators

| Operator | Meaning           |
|----------|-------------------|
| `=`      | Variable assignment|
| `*`      | Multiplication    |
| `/`      | Division          |
| `+`      | Addition          |
| `-`      | Subtraction       |
| `++`     | Increment by 1    |
| `--`     | Decrement by 1    |

---

## If / Else Statements

```js
if (conditional) {
    // Conditional is true, use logic defined here
    // ...

} else {
    // Conditional is false, use the following logic
    // ...
}
```


Example:
```js
const age = 15;
if (age > 16) {
  console.log("You can drive!");
} else {
  console.log("Sorry. Too young!");
}

// Output: Sorry. Too young!"
```

---

## Arrays

```js
let fruits = ["apple", "banana", "orange"];
```

### Array Methods

In JavaScript, **arrays are zero-indexed**, which means:

- The **first item** in the array is at **position 0**
- The **second item** is at position **1**, and so on

#### Example:

```js
let fruits = ["apple", "banana", "orange"];
```

| Index | Value   |
|-------|---------|
| 0     | "apple" |
| 1     | "banana"|
| 2     | "orange"|

To access a value, you use its index:

```js
console.log(fruits[0]); // "apple"
console.log(fruits[2]); // "orange"
```

To change a value:

```js
fruits[1] = "grape"; // changes "banana" to "grape"
console.log(fruits); // ["apple", "grape", "orange"]
```

**push()** — Adds item to end:
  ```js
  fruits.push("grapes"); // ['apple', 'banana', 'orange', 'grapes']
  ```

**pop()** — Removes last item:
  ```js
  fruits.pop(); // ['apple', 'banana']
  ```

**splice()** — Modify array contents:
  ```js
  // splice(index, remove_count, item1, item2, ...)
  const fruits = ["Banana", "Orange", "Apple", "Mango"];
  fruits.splice(2, 0, "Lemon", "Kiwi"); 
  // Result: ['Banana', 'Orange', 'Lemon', 'Kiwi', 'Apple', 'Mango']
  ```

---

## Array Find Methods

- **find()** — Returns first element matching condition:

```js
let products = [
  { name: "Apple", price: 1 },
  { name: "Banana", price: 2 }
];

let result = products.find(product => product.name === "Banana");
console.log(result); 
// Output: { name: "Banana", price: 2 }
```

- **findIndex()** — Returns index of first matching element.
```js
let products = [
  { name: "Apple", price: 1 },
  { name: "Banana", price: 2 }
];

let result = products.findIndex(product => product.name === "Banana");
console.log(result); 
// Output: 1
```
---

## Objects

```js
let product = {
  name: "Apple",
  price: 1.29
};
```

- Access a field: `product.name`
- Set a field: `product.price = 2.00`
- Add a new field: `product.category = "Fruit"`

---

## Functions

```js
function functionName(PARAMETER) {
  // Logic here
  return RESULT;
}
```

- Parameters can be zero, one, or many.
- Functions do not have to return anything.

### Example

```js
function printProduct(product) {
  console.log(product.name + " costs $" + product.price);
}

let item = { name: "Sour Patch Kids", price: 1.29 };
printProduct(item); 
// Output: Sour Patch Kids costs $1.29
```

---

## Document Object Model (DOM)

The DOM is how JavaScript sees and changes parts of your webpage, like paragraphs, images, or buttons.

### Accessing Elements

```js
let paragraph = document.querySelector("p");           // By tag
let myDiv = document.querySelector(".my-div");         // By class
let element = document.querySelector("#myDiv");        // By ID
document.getElementById("myElementId").innerHTML = "Set new value";
```

- `document.querySelectorAll(".myClass")` — Gets all elements matching the CSS selector as an array.

---

## Event Listeners

```js
button.addEventListener("event", function);
```
- Event listeners help your webpage respond to clicks and typing.
- `"event"` is a string like `"click"`, `"mouseover"`, or `"keydown"`.
- The function defines what happens when the event occurs.


## Creating + Inserting Elements
`document.createElement(tagName)`
- Creates a new DOM element (not yet on the page).

```js
const li = document.createElement("li");
li.className = "cart-item";
li.textContent = "Banana — $2.00";
```

Common properties to set:
- `textContent / innerHTML` — text or HTML inside the element
- `className / classList.add("...")` — CSS classes
- `setAttribute(name, value)` — any attribute (e.g., src, alt, data-*)

`parent.appendChild(child)`
- Adds the child node as the last child of parent. If the child is already in the DOM, it moves it.

```js
const cartList = document.querySelector(".shopping-cart"); // e.g., a <ul> in your HTML
const li = document.createElement("li");
li.className = "cart-item";
li.textContent = "Banana — $2.00";

cartList.appendChild(li); // li now appears at the end of the cart list
```

---
