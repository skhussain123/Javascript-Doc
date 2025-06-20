

# JavaScript Events
JavaScript Events wo actions hain jo browser ya user perform karta hai — aur aap un pe respond karte ho.


## Example events:

* User ne button click kiya 🖱️
* Mouse move hua 🐭
* Key press hui ⌨️
* Page load hua 🌐


## Event Types
JavaScript supports a variety of event types. Common categories include:

Mouse Events: click, dblclick, mousemove, mouseover, mouseout
Keyboard Events: keydown, keypress, keyup
Form Events: submit, change, focus, blur
Window Events: load, resize, scroll


## Common JavaScript Events

| **Event Attribute** | **Description**                                       |
| ------------------- | ----------------------------------------------------- |
| `onclick`           | Triggered when an element is clicked.                 |
| `onmouseover`       | Fired when the mouse pointer moves over an element.   |
| `onmouseout`        | Occurs when the mouse pointer leaves an element.      |
| `onkeydown`         | Fired when a key is pressed down.                     |
| `onkeyup`           | Fired when a key is released.                         |
| `onchange`          | Triggered when the value of an input element changes. |
| `onload`            | Occurs when a page has finished loading.              |
| `onsubmit`          | Fired when a form is submitted.                       |
| `onfocus`           | Occurs when an element gets focus.                    |
| `onblur`            | Fired when an element loses focus.                    |


```bash

// Mouse Event
document.addEventListener("mousemove", (e) => {
    console.log(`Mouse moved to (${e.clientX}, ${e.clientY})`);
});

// Keyboard Event
document.addEventListener("keydown", (e) => {
    console.log(`Key pressed: ${e.key}`);
});


```
* The mousemove event tracks cursor movement.
* The keydown event captures key presses.

## Event Handling Methods

### 1. Inline HTML Handlers
```bash
<button onclick="alert('Button clicked!')">Click Me</button>
```

### 2. DOM Property Handlers
```bash
let btn = document.getElementById("myButton");
btn.onclick = () => {
      alert("Button clicked!");
};
```

### 3. addEventListener() (Preferred)
```bash
btn.addEventListener("click", () => {
    alert("Button clicked using addEventListener!");
});
```
addEventListener() is the most versatile and recommended method as it supports multiple event listeners and removal of listeners.


## Event Propagation
JavaScript events propagate in two phases:

* Capturing Phase: Event travels from the root to the target element.
* Bubbling Phase: Event travels from the target element back to the root.

```bash
document.querySelector("div").addEventListener("click", () => {
    console.log("Div clicked");
}, true); // Capturing phase

button.addEventListener("click", (e) => {
    console.log("Button clicked");
    e.stopPropagation(); // Stops propagation
});
```
* Setting true in addEventListener makes it capture events during the capturing phase.
* stopPropagation() halts further propagation.


### Event Delegation
Event delegation allows you to handle events efficiently by attaching a single listener to a parent element.
```bash
document.querySelector("ul").addEventListener("click", (e) => {
    if (e.target.tagName === "LI") {
        console.log(`Clicked on item: ${e.target.textContent}`);
    }
});
```

### Preventing Default Behavior
Certain elements have default actions (e.g., links navigating to URLs). Use preventDefault() to override them.
```bash
document.querySelector("a").addEventListener("click", (e) => {
    e.preventDefault();
    console.log("Link click prevented");
});
```
preventDefault() stops the link from navigating.



# Practical Applications
### 1. Form Validation

```bash
<html>
<body>
    <h2>Form Validation</h2>
    <form id="example">
        <input type="text" placeholder="Enter something" id="formInput" />
        <button type="submit">Submit</button>
    </form>
    <script>
        document.querySelector("#example").addEventListener("submit", (e) => {
            let input = document.querySelector("#formInput");
            if (!input.value) {
                e.preventDefault();
                alert("Input cannot be empty");
            }
        });
    </script>

</body>

</html>


```

### 2. Dynamic Content
```bash
<html>

<body>
    <h2>Dynamic Content</h2>
    <button id="button">Add Element</button>
    <script>
        document.querySelector("#button").addEventListener("click", () => {
            let newDiv = document.createElement("div");
            newDiv.textContent = "New Element Added";
            newDiv.style.margin = "10px 0";
            document.body.appendChild(newDiv);
        });
    </script>

</body>

</html>


```

### 3. Interactive Lists
```bash
<html>

<body>
    <h2>Interactive Lists</h2>
    <ul id="lists">
        <li>Interactive Item 1</li>
        <li>Interactive Item 2</li>
        <li>Interactive Item 3</li>
    </ul>
    <script>
        let ul = document.querySelector("#lists");

        ul.addEventListener("click", (e) => {
            if (e.target.tagName === "LI") {
                e.target.style.backgroundColor = "yellow";
            }
        });
    </script>

</body>

</html>
```



# JavaScript Event Bubbling
Event Bubbling JavaScript ka ek process hai jisme:

Jab kisi nested element pe event hota hai, to wo event upar parent elements tak automatically propagate karta hai.

Matlab:

* Pehle inner element ka event chalega.
* Phir parent ka.
* Phir uske parent ka... aur aise hi bubble hota hua document tak chala jata hai.

### Real-Life Example:
```bash
<div id="outer">
  <button id="inner">Click Me</button>
</div>



document.getElementById("outer").addEventListener("click", function () {
  console.log("Outer Div Clicked");
});

document.getElementById("inner").addEventListener("click", function () {
  console.log("Button Clicked");
});

Output on Button Click::
Button Clicked
Outer Div Clicked

```
 Pehle button ka event chalega, phir outer div ka — yehi bubbling hai.


 ### Stop Bubbling:
Kabhi kabhi aap chahte ho ke event upar propagate na ho. Tab aap event.stopPropagation() use karte ho.
```bash
document.getElementById("inner").addEventListener("click", function (e) {
  e.stopPropagation();
  console.log("Only Button Clicked");
});

```

###  Event Bubbling vs Capturing:

| Feature          | **Event Bubbling**            | **Event Capturing**             |
| ---------------- | ----------------------------- | ------------------------------- |
| Direction        | Child ➝ Parent (bottom-up)    | Parent ➝ Child (top-down)       |
| Default behavior | ✅ Yes                         | ❌ No (need `{ capture: true }`) |
| Common use       | Most JavaScript apps use this | Rare, but possible              |


| Concept            | Description                                                          |
| ------------------ | -------------------------------------------------------------------- |
| **Event Bubbling** | Event child se parent tak jata hai                                   |
| **Why Useful?**    | Aap parent pe ek event laga ke multiple children handle kar sakte ho |
| **Stop it?**       | Use `event.stopPropagation()`                                        |

