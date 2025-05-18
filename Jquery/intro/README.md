

# introduction
jQuery is a fast, small, and feature-rich JavaScript library that simplifies tasks like:

1. DOM manipulation
2. Event handling
3. AJAX requests
4. Animations
5. Cross-browser compatibility

 It was very popular before modern JavaScript (ES6+) and frameworks (like React, Vue) became common.
* if you write jquery code you will see the jquery code will run all browser properly
* increase Code speed

### Why Use jQuery?

| ✅ Feature                 | 🔎 Explanation                                                                       |
| ------------------------- | ------------------------------------------------------------------------------------ |
| **Simplified Syntax**     | Short and clean code. Example: `$("#id")` instead of `document.getElementById("id")` |
| **Cross-Browser Support** | Automatically handles browser differences                                            |
| **DOM Manipulation**      | Add, remove, update HTML elements easily                                             |
| **Event Handling**        | Simplified handling of click, hover, etc.                                            |
| **AJAX Made Easy**        | Send/receive data without refreshing the page                                        |
| **Animations**            | Built-in functions like `fadeIn()`, `slideUp()`                                      |
| **Plugins**               | Thousands of free plugins (sliders, modals, etc.)                                    |


**Tirget using id:**
document.getElementsById('#example')
```bash
$('.example')
```

**Tirget using Class:**
document.getElementsByClassName('#example')
```bash
$('#example')
```


**Tirget Using Tag name:**
document.getElementsByTagName('#example')
```bash
$('tagexample')
```


**select the dom element**
```bash
$(document).ready(function () {
  // Your jQuery code here
});
```

### Selectors
| Selector                  | Meaning            | Example                    |
| ------------------------- | ------------------ | -------------------------- |
| `$("*")`                  | Select All element | `$("#btn")`                |
| `$("#id")`                | Select by ID       | `$("#btn")`                |
| `$(".class")`             | Select by class    | `$(".box")`                |
| `$("tag")`                | Select by tag      | `$("p")`                   |
| `$("div, p")`             | Multiple elements  | `$("h1, h2")`              |
| `$("ul li:first")`        | First child        | `$("ul li:first")`         |
| `$("ul li:last")`         | Last child         | `$("ul li:last")`          |
| `$("input[type='text']")` | Attribute selector | `$("input[type='email']")` |


### CSS and Effects

```bash
$("#box").css("color", "blue");       // Apply CSS
$("#box").addClass("active");         // Add class
$("#box").removeClass("active");      // Remove class
$("#box").toggleClass("active");      // Toggle class

$("#box").hide();                     // Hide element
$("#box").show();                     // Show element
$("#box").toggle();                   // Toggle visibility

$("#box").fadeIn();
$("#box").fadeOut();
$("#box").slideUp();
$("#box").slideDown();
```

### ✅ Mouse Events in jQuery
```bash
// Click event
$("#btn").click(function () {
  alert("Clicked!");
});

// Right-click event (context menu)
$("#input").on("contextmenu", function () {
  console.log($(this).val());
});

// Mouse enters the element
$("#input").mouseenter(function () {
  console.log("Mouse entered:", $(this).val());
});

// Mouse leaves the element
$("#input").mouseleave(function () {
  console.log("Mouse left:", $(this).val());
});

```
| Event                | Description                                 |
| -------------------- | ------------------------------------------- |
| `.click()`           | Triggered on left mouse click               |
| `.on("contextmenu")` | Triggered on right click                    |
| `.mouseenter()`      | Triggered when the mouse enters the element |
| `.mouseleave()`      | Triggered when the mouse leaves the element |


### Keyboard Events

```bash
$("#input").keydown(function () {
  console.log("Key is down");
});

$("#input").keypress(function () {
  console.log("Key is pressed");
});

$("#input").keyup(function () {
  console.log("Key is released");
});

```

### Window Events
```bash
$(window).on("event", function () {
  // code
});


$(window).on("load", function () {
  alert("Page fully loaded!");
});
Note: Modern browsers may not always trigger load this way — use in specific cases only.


$(window).resize(function () {
  console.log("Window resized to: " + $(window).width() + " x " + $(window).height());
});


$(window).scroll(function () {
  console.log("Scroll position: " + $(window).scrollTop());
});


$(window).on("unload", function () {
  console.log("Page is being unloaded.");
});
Tip: unload is deprecated. Use beforeunload cautiously if needed for warnings.

$(window).on("beforeunload", function () {
  return "Are you sure you want to leave this page?";
});

```





### DOM Manipulation
```bash
$("#text").text("Hello");         // Set text
$("#box").html("<b>Bold</b>");    // Set HTML
$("#input").val("New value");     // Set value

$("ul").append("<li>Item</li>");  // Add to end
$("ul").prepend("<li>Item</li>"); // Add to start

$("#item").remove();              // Remove element
```

### Form Methods
```bash
$("#myForm").submit(function (e) {
  e.preventDefault();
  alert("Form submitted!");
});

```

### Looping and Traversing
```bash
$("li").each(function () {
  console.log($(this).text());
});

$("#list").children();     // Get child elements
$("#list").parent();       // Get parent
$("#item").next();         // Next sibling
$("#item").prev();         // Previous sibling

```


