

# 1. .children() and .find()
Here’s a clear explanation of .children() and .find() in jQuery – both are used for selecting child elements but work differently:


### 1. .children()
Selects direct (immediate) children of the selected element.

```bash
<div class="parent">
  <p class="child">One</p>
  <div>
    <p class="child">Two (Nested)</p>
  </div>
</div>

<script>
  $('.parent').children('.child').css('color', 'red');
</script>


```
Only the first <p class="child">One</p> will be affected because it's an immediate child of .parent.

### 2. .find()
Selects all descendants (children, grandchildren, etc.) that match the selector.

```bash
$('.parent').find('.child').css('color', 'blue');

```
This will apply to both "One" and "Two", since it searches deeply inside the .parent.

### Key Differences
| Method        | Searches       | Returns                 | Example                           |
| ------------- | -------------- | ----------------------- | --------------------------------- |
| `.children()` | One level down | Immediate children only | `$('.parent').children('.child')` |
| `.find()`     | All levels     | Any matching descendant | `$('.parent').find('.child')`     |


###  Example in Action

```bash
<div class="container">
  <div class="box">Box 1</div>
  <div class="nested">
    <div class="box">Box 2 (Nested)</div>
  </div>
</div>

<script>
  // Only direct .box under .container
  $('.container').children('.box').css('background', 'lightgreen');

  // All .box under .container (even deeply nested)
  $('.container').find('.box').css('border', '2px solid red');
</script>

```


# 2. siblings(), next(), nextAll(), nextUntil(), prev(), prevAll(), prevUntil()

### 1. .siblings()
Selects all siblings (same parent) of the selected element excluding itself.

```bash
$('.item').siblings().css('color', 'blue');

```

### 2. .next()
Selects the immediate next sibling.

```bash
$('.item').next().css('color', 'green');

```

### 3. .nextAll()
Selects all next siblings after the selected element.

```bash
$('.item').nextAll().css('color', 'orange');

```

### 4. .nextUntil(selector)
Selects all next siblings up to (but not including) the element matched by the selector.

```bash
$('.item').nextUntil('.stop').css('background', 'yellow');

```

### 5. .prev()
Selects the immediate previous sibling.

```bash
$('.item').prev().css('border', '1px solid red');

```

### 6. .prevAll()
Selects all previous siblings before the selected element.

```bash
$('.item').prevAll().hide();

```

### 7. .prevUntil(selector)
Selects all previous siblings up to (but not including) the element matched by the selector.

```bash
$('.item').prevUntil('.start').fadeOut();

```

### Example HTML for Testing
```bash

<ul>
  <li class="start">Start</li>
  <li>One</li>
  <li class="item">Two (Selected)</li>
  <li>Three</li>
  <li>Four</li>
  <li class="stop">Stop</li>
</ul>


```

### Summary Table

| Method            | What it selects                    |
| ----------------- | ---------------------------------- |
| `.siblings()`     | All siblings except itself         |
| `.next()`         | Next **one** sibling               |
| `.nextAll()`      | All siblings after                 |
| `.nextUntil(sel)` | All siblings after, **until sel**  |
| `.prev()`         | Previous **one** sibling           |
| `.prevAll()`      | All siblings before                |
| `.prevUntil(sel)` | All siblings before, **until sel** |



# 3. .first(), .last(), .eq(), .filter(), .not(), and .slice()

### 1. .first()
Selects the first element from a jQuery selection.

```bash
$('li').first().css('color', 'green');

```

### 2. .last()
Selects the last element.

```bash
$('li').last().css('color', 'red');

```

### 3. .eq(index)
Selects the element at the given index (zero-based).

```bash
$('li').eq(2).css('font-weight', 'bold');  // 3rd item

```
Negative index counts from the end:

```bash
$('li').eq(-1).css('color', 'blue');  // Last item

```

### 4. .filter(selector/function)
Returns only the elements that match a selector or custom function.

```bash
$('li').filter('.active').css('background', 'lightgreen');

// OR with a function
$('li').filter(function(index) {
  return index % 2 === 0;  // Even items
}).css('background', '#eee');

```

###  5. .not(selector/function)
Excludes elements that match the selector or condition.

```bash
$('li').not('.active').css('opacity', '0.5');

// OR with a function
$('li').not(function(index) {
  return index === 2;
}).css('font-style', 'italic');

```

### 6. .slice(start, end)
Selects a subset of elements from the list (like array slicing).

```bash
$('li').slice(1, 4).css('border', '1px solid black');  // 2nd to 4th item

```

### Example HTML to Try With:

```bash
<ul>
  <li>One</li>
  <li class="active">Two</li>
  <li>Three</li>
  <li class="active">Four</li>
  <li>Five</li>
</ul>

```

### Summary Table

```bash
| Method              | Description                 |
| ------------------- | --------------------------- |
| `.first()`          | First element only          |
| `.last()`           | Last element only           |
| `.eq(index)`        | Element at specific index   |
| `.filter()`         | Keep matching elements only |
| `.not()`            | Exclude matching elements   |
| `.slice(start,end)` | Select a range of elements  |

```

# 4.  .has() and .is()

### 1. .has(selector)
Returns elements that contain a descendant matching the selector.

```bash
<div class="box">
  <p>Inside</p>
</div>
<div class="box">
  <span>Another</span>
</div>

<script>
  $('.box').has('p').css('border', '2px solid green');
</script>

```

### 2. .is(selector/function)
Checks if any element in the selection matches the selector or condition.
🔸 Returns true or false.

#### Example 1: Check if element has class
```bash
if ($('#myDiv').is('.active')) {
  console.log('It has the active class');
}
```
#### Example 2: Check if it's a hidden element

 ```bash
if ($('#myDiv').is(':hidden')) {
  $('#myDiv').show();
}
 ```
 
 #### Example 3: Use with function

 ```bash
$('li').each(function() {
  if ($(this).is(':nth-child(odd)')) {
    $(this).css('background', '#eee');
  }
});

 ```


 ### Summary Table
 | Method   | Purpose                                       | Returns        |
| -------- | --------------------------------------------- | -------------- |
| `.has()` | Filters elements that contain a child element | jQuery object  |
| `.is()`  | Checks if element matches selector/condition  | `true`/`false` |



# 5. .each() — Loop Through Elements
The .each() method lets you iterate over a set of elements and run code on each one individually.

```bash
$(selector).each(function(index, element) {
  // 'this' refers to the current element
});

```

#### Example 1: Change color of each <li>
```bash
<ul>
  <li>Apple</li>
  <li>Banana</li>
  <li>Mango</li>
</ul>

<script>
  $('li').each(function(index) {
    $(this).text((index + 1) + '. ' + $(this).text());
    $(this).css('color', 'green');
  });
</script>

```

#### Example 2: Use .each() with array
```bash
$.each([10, 20, 30], function(index, value) {
  console.log('Index:', index, 'Value:', value);
});

```

#### Example 3: .each() with object
```bash
let obj = { name: 'Ali', age: 22, role: 'Developer' };

$.each(obj, function(key, value) {
  console.log(key + ': ' + value);
});

```

* $(this) inside .each() refers to the current DOM element.
* You can break the loop using return false;.
* You can skip an item using return true;.


### Break Example
```bash
$('li').each(function(index) {
  if (index === 2) return false; // Stops at third item
  console.log($(this).text());
});

```

### Skip Example
```bash
$('li').each(function(index) {
  if (index === 1) return true; // Skips second item
  console.log($(this).text());
});
```


# 6.  event.pageX and event.pageY
In jQuery (and plain JavaScript), event.pageX and event.pageY are properties that give you the mouse pointer position relative to the entire document (page) when an event (like a click or mousemove) happens.

```bash
$(document).on('click', function(event) {
  console.log('X: ' + event.pageX + ', Y: ' + event.pageY);
});

```

### Explanation
| Property      | Description                                   |
| ------------- | --------------------------------------------- |
| `event.pageX` | Horizontal position from the **left** of page |
| `event.pageY` | Vertical position from the **top** of page    |

### Example: Show Mouse Position on Click
```bash
<div id="output"></div>

<script>
  $(document).on('click', function(event) {
    $('#output').text('X: ' + event.pageX + ' | Y: ' + event.pageY);
  });
</script>

```
### Difference from clientX / clientY
| Property    | Measures from                              |
| ----------- | ------------------------------------------ |
| `pageX/Y`   | Top/left of the **page** (includes scroll) |
| `clientX/Y` | Top/left of the **viewport** (no scroll)   |



# 7. jQuery event properties and methods:

### event.type
Returns the type of the event triggered (like "click", "keydown").

```bash
$(document).on('click keydown', function(event) {
  console.log('Event type:', event.type);
});
```

### event.which
Gives the mouse button (for mouse events) or key code (for keyboard events).

```bash
$(document).on('keydown', function(event) {
  console.log('Key code:', event.which); // e.g., Enter = 13
});

```
```bash
$(document).on('click', function(event) {
  console.log('Mouse button:', event.which); // Left=1, Middle=2, Right=3
});
```

### event.target
Returns the exact DOM element that triggered the event.

```bash
$(document).on('click', function(event) {
  console.log('You clicked:', event.target);
  $(event.target).css('background', 'lightblue');
});
```

### event.preventDefault()
Stops the default browser behavior, such as link navigation or form submission.

```bash
$('a').on('click', function(event) {
  event.preventDefault(); // Stop link from navigating
  alert('Link blocked!');
});
```

### event.stopPropagation()
Stops the event from bubbling up to parent elements.

```bash
<div id="outer">
  <button id="inner">Click Me</button>
</div>

<script>
  $('#outer').on('click', function() {
    alert('Outer div clicked');
  });

  $('#inner').on('click', function(event) {
    event.stopPropagation(); // Prevent outer div click
    alert('Button clicked');
  });
</script>
```

### event.data
Allows you to pass custom data to the event handler using jQuery.

```bash
$('#btn').on('click', { name: 'Ali', age: 22 }, function(event) {
  alert('Name: ' + event.data.name);
});
```

### Summary Table
| Property / Method         | Description                             |
| ------------------------- | --------------------------------------- |
| `event.type`              | Event type (e.g., `click`, `keydown`)   |
| `event.which`             | Key code or mouse button                |
| `event.target`            | Element that triggered the event        |
| `event.preventDefault()`  | Prevent default browser behavior        |
| `event.stopPropagation()` | Stop event from bubbling up             |
| `event.data`              | Custom data passed to the event handler |


##  jQuery Plugin — Introduction
A jQuery plugin is a reusable function or feature that extends jQuery's capabilities. You can create your own or use plugins built by others to add effects, sliders, form validation, modals, etc.

### Why Use jQuery Plugins?

* Reuse code across projects
* Keep your code modular and clean
* Extend jQuery with custom functionality
* Easily add features like carousels, date pickers, etc.


### Basic Structure of a jQuery Plugin

```bash
(function ($) {
  $.fn.myPlugin = function (options) {
    // Default settings
    let settings = $.extend({
      color: 'blue',
      fontSize: '16px'
    }, options);

    // Apply to each matched element
    return this.each(function () {
      $(this).css({
        color: settings.color,
        fontSize: settings.fontSize
      });
    });
  };
}(jQuery));


Usage:
$('p').myPlugin({ color: 'red', fontSize: '20px' });
```


#### Example Plugin: Highlight Text

```bash

(function($){
  $.fn.highlight = function(color){
    color = color || 'yellow';
    return this.css('backgroundColor', color);
  };
})(jQuery);

// Usage:
$('h2').highlight('lightgreen');

```

###  Famous jQuery Plugins
| Plugin Name          | Purpose                       |
| -------------------- | ----------------------------- |
| **jQuery UI**        | Interactions, effects         |
| **Slick**            | Responsive carousels/sliders  |
| **Lightbox**         | Image viewer modal            |
| **Validate.js**      | Form validation               |
| **DataTables**       | Dynamic table with search     |
| **Chosen / Select2** | Beautify `<select>` dropdowns |

### How to Use a jQuery Plugin
#### Include jQuery:
```bash
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
```
#### Include plugin file (CDN or local):
```bash
<script src="path-to-plugin.js"></script>
```

#### Initialize plugin:
```bash
$('#element').pluginName(options);
```