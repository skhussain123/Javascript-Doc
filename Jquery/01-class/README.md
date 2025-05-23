

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


### Get Methods

```bash
$("#box").html("<b>Bold</b>"); // get html
$("#text").text();  // get the text  
$("#text").attr();  // get the attribute 
$("#input").val();   get value from element  
```



### Set Methods

```bash
$("#box").html("<b>Bold</b>"); // set the new html
$("#text").text('set the new text');
$("#text").attr("class", "container");  // Set the attribute 
$("#input").val();   get value from element  
```



### CSS Class Methods
```bash
$("#box").addClass("active");         // Add class
$("#box").removeClass("active");      // Remove class
$("#box").toggleClass("active");      // Toggle class
```


### CSS Methods
```bash
$("#box").css("background", "pink");   
$("#box").css({"background":"pink", "color": "black"});   

```

### jQuery On & Off Method 
```bash
$("#btn").on("click", function () {
  alert("Button clicked!");
});


$("#box").on("mouseenter mouseleave", function () {
  $(this).toggleClass("highlight");
});


$("#list").on("click", "li", function () {
  alert("List item clicked: " + $(this).text());
});


$("#btn").off("click"); // disables click event
$("#list").off("click", "li");

$("#btn").on("click", function () {
  alert("Clicked once!");
  $(this).off("click"); // disables further clicks
});


```


### jQuery Append & Prepend Method
```bash
<ul id="list">
  <li>Item 1</li>
</ul>

<script>
  $("#list").append("<li>Item 2</li>");
</script>


<ul id="list">
  <li>Item 1</li>
  <li>Item 2</li> <!-- added at the end -->
</ul>

```

```bash
<ul id="list">
  <li>Item 1</li>
</ul>

<script>
  $("#list").prepend("<li>New First Item</li>");
</script>


<ul id="list">
  <li>New First Item</li> <!-- added at the beginning -->
  <li>Item 1</li>
</ul>

```


### After & Before Method

```bash
<p id="text">Hello</p>

<script>
  $("#text").after("<span> World!</span>");
</script>


```

```bash
<p id="text">Hello</p>

<script>
  $("#text").before("<span>Welcome: </span>");
</script>

```

### ✅ Difference vs .append() and .prepend()

| Method       | Adds Content | Position           |
| ------------ | ------------ | ------------------ |
| `.append()`  | Inside       | At the end         |
| `.prepend()` | Inside       | At the beginning   |
| `.after()`   | Outside      | After the element  |
| `.before()`  | Outside      | Before the element |


### Empty & Remove Method

```bash
<div id="box">
  <p>Hello</p>
</div>

<script>
  $("#box").empty();
</script>

```

```bash
<div id="box">
  <p>Hello</p>
</div>

<script>
  $("#box").remove();
</script>

```
```bash
$("li").remove(".active"); // removes only <li> elements with class "active"

```

### AppendTo & PrependTo Method 
```bash
<div id="box1"></div>
<div id="box2"></div>

<script>
  $("<p>Hello</p>").appendTo("#box1");
</script>

Output:
<div id="box1">
  <p>Hello</p>
</div>


```

```bash
<div id="container">
  <p>Second</p>
</div>

<script>
  $("<p>First</p>").prependTo("#container");
</script>

output:
<div id="container">
  <p>First</p>
  <p>Second</p>
</div>

```

### jQuery Clone Method

```bash
<div id="original">
  <p>Hello World</p>
</div>

<script>
  let copy = $("#original").clone();
  $("body").append(copy); // add cloned element to the page
</script>



output:
<div id="original">
  <p>Hello World</p>
</div>
<div>
  <p>Hello World</p>
</div>

```

```bash
<button id="btn">Click Me</button>
<div id="box">Box</div>

<script>
  $("#btn").on("click", function () {
    let clone = $("#box").clone();
    $("body").append(clone);
  });
</script>
```

```bash
<input type="text" id="input1" placeholder="Type something">

<script>
  $("#input1").on("keyup", function () {
    console.log($(this).val());
  });

  let copy = $("#input1").clone(true); // copy with event
  $("body").append(copy);
</script>
```

### ReplaceWith & ReplaceAll Method

```bash
<p id="old">Old Text</p>

<script>
  $("#old").replaceWith("<h2>New Heading</h2>");
</script>


output:
<h2>New Heading</h2>

```

```bash
<p class="remove">Old</p>
<p class="remove">Old</p>

<script>
  $("<h2>Replaced</h2>").replaceAll(".remove");
</script>


output:
<h2>Replaced</h2>
<h2>Replaced</h2>

```

| Method           | Replaces                | Used on...                   |
| ---------------- | ----------------------- | ---------------------------- |
| `.replaceWith()` | The **current** element | The selected element         |
| `.replaceAll()`  | The **target** element  | The content replaces another |


### Wrap & UnWrap Method
```bash
<p class="text">Hello World</p>

<script>
  $(".text").wrap("<div class='wrapper'></div>");
</script>

output:
<div class="wrapper">
  <p class="text">Hello World</p>
</div>

```

```bash
<div class="wrapper">
  <p class="text">Hello World</p>
</div>

<script>
  $(".text").unwrap();
</script>


output:
<p class="text">Hello World</p>
```

**Toggle Wrap**
```bash
$("#btn-wrap").click(function () {
  $(".item").wrap("<div class='box'></div>");
});

$("#btn-unwrap").click(function () {
  $(".item").unwrap();
});
```

### Wrap & UnWrap Method Tutorial 
Here’s a simple and clear tutorial on the .wrap() and .unwrap() methods in jQuery — used to add or remove HTML wrappers around selected elements.

####  .wrap() Method (Add a Wrapper)
* Wraps each selected element in a single wrapper element.
```bash
$(selector).wrap(wrappingElement);

```

```bash
<p class="text">Hello World</p>

<script>
  $(".text").wrap("<div class='wrapper'></div>");
</script>

```

OUTPUT:
```bash
<div class="wrapper">
  <p class="text">Hello World</p>
</div>
```

#### .unwrap() Method (Remove a Wrapper)
* Removes the parent element of the selected elements, but keeps the inner content.

```bash
$(selector).unwrap();

```

```bash
<div class="wrapper">
  <p class="text">Hello World</p>
</div>

<script>
  $(".text").unwrap();
</script>

```

OUTPUT:
```bash
<p class="text">Hello World</p>
```

####  (Wrap + Unwrap Toggle)
```bash
<p class="para">Click the buttons to wrap or unwrap me!</p>
<button id="wrapBtn">Wrap</button>
<button id="unwrapBtn">Unwrap</button>

<script>
  $("#wrapBtn").click(function () {
    $(".para").wrap("<div class='box' style='border: 2px solid red; padding: 10px;'></div>");
  });

  $("#unwrapBtn").click(function () {
    $(".para").unwrap();
  });
</script>

```

### WrapAll & WrapInner Method
Here’s a clear and practical guide on .wrapAll() and .wrapInner() methods in jQuery — two powerful ways to manipulate HTML structure dynamically.

#### .wrapAll() – Wrap ALL selected elements with ONE wrapper
```bash
$(selector).wrapAll(wrappingElement);
```

```bash
<p class="item">Item 1</p>
<p class="item">Item 2</p>

<script>
  $(".item").wrapAll("<div class='group'></div>");
</script>

```

```bash
<div class="group">
  <p class="item">Item 1</p>
  <p class="item">Item 2</p>
</div>
```

#### 🌀 .wrapInner() – Wrap the CONTENT of each element
```bash
$(selector).wrapInner(wrappingElement);
```

```bash
<p class="text">Hello</p>

<script>
  $(".text").wrapInner("<span class='highlight'></span>");
</script>
```

```bash
<p class="text"><span class="highlight">Hello</span></p>
```


| Method         | What it Wraps                               | Result Example                |
| -------------- | ------------------------------------------- | ----------------------------- |
| `.wrap()`      | Each element (individually)                 | Multiple wrappers             |
| `.wrapAll()`   | All selected elements together (once)       | One common wrapper            |
| `.wrapInner()` | Only the contents of each selected element  | Content gets wrapped          |
| `.unwrap()`    | Removes the parent of each selected element | Content pulled out of wrapper |


### Width & Height Methods

#### 📏 .width() – Get or set the width of an element

```bash
let w = $("#box").width();
console.log(w); // e.g., 200

$("#box").width(300); // Set width to 300px

```

#### 📐 .height() – Get or set the height of an element

```bash
let h = $("#box").height();
console.log(h); // e.g., 150

$("#box").height(250); // Set height to 250px
```

#### 🔎 .innerWidth() / .innerHeight()

```bash
$("#box").innerWidth();  // width + padding

```

```bash
$("#box").outerWidth();       // width + padding + border
$("#box").outerWidth(true);   // width + padding + border + margin

```


| Method              | Includes                   |
| ------------------- | -------------------------- |
| `.width()`          | Content only               |
| `.innerWidth()`     | Content + Padding          |
| `.outerWidth()`     | Content + Padding + Border |
| `.outerWidth(true)` | + Margin                   |


### Position & Offset Method
Here’s a simple and clear tutorial on .position() and .offset() methods in jQuery — used to get an element’s coordinates.

#### 📍 .position() – Get element's position relative to its parent

```bash
<div id="parent" style="position: relative;">
  <div id="child" style="position: absolute; top: 20px; left: 50px;">Box</div>
</div>

<script>
  let pos = $("#child").position();
  console.log(pos); // { top: 20, left: 50 }
</script>

```

#### 🌍 .offset() – Get element's position relative to the document

```bash
<div id="box" style="margin-top: 100px; margin-left: 200px;">Box</div>

<script>
  let off = $("#box").offset();
  console.log(off); // e.g., { top: 100, left: 200 }
</script>

```

| Method           | Measures from   | Use Case                       |
| ---------------- | --------------- | ------------------------------ |
| `.position()`    | Offset parent   | Inside relative container      |
| `.offset()`      | Document (page) | Absolute position on full page |
| `.offset({...})` | Set position    | Move element on the page       |



