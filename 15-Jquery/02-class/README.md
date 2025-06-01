

## 1. scrollTop() and scrollLeft()

In jQuery, scrollTop() and scrollLeft() are used to get or set the vertical and horizontal scroll positions of an element or the entire page.

```bash
// Get vertical scroll position
let top = $(window).scrollTop();

// Get horizontal scroll position
let left = $(window).scrollLeft();

```

### Set Scroll Position
```bash
// Set vertical scroll position to 100 pixels
$(window).scrollTop(100);

// Set horizontal scroll position to 50 pixels
$(window).scrollLeft(50);

```

### Scroll a specific element
```bash
<div id="box" style="width: 200px; height: 200px; overflow: scroll;">
  <div style="width: 1000px; height: 1000px;">Content</div>
</div>

<script>
// Set scroll positions of #box
$('#box').scrollTop(150);
$('#box').scrollLeft(200);

// Get scroll positions of #box
let top = $('#box').scrollTop();
let left = $('#box').scrollLeft();
</script>

```

### Scroll Event Example
```bash
$(window).on('scroll', function() {
  console.log('Top:', $(this).scrollTop());
  console.log('Left:', $(this).scrollLeft());
});

```


## 2. HasClass Method
In jQuery, the .hasClass() method is used to check if an element has a specific class.

```bash
<div id="myDiv" class="box active"></div>

<script>
  if ($('#myDiv').hasClass('active')) {
    console.log('Element has the class "active"');
  } else {
    console.log('Class not found');
  }
</script>

```

### Loop through multiple elements
```bash
$('.item').each(function() {
  if ($(this).hasClass('selected')) {
    console.log('This item is selected:', this);
  }
});

```
Let me know if you want examples with .addClass(), .removeClass(), or .toggleClass() too.


## 3. .hide(), .show(), and .toggle()
In jQuery, you can use .hide(), .show(), and .toggle() to control the visibility of elements with or without animation.

### 1. .hide()
Hides the selected elements.

```bash
$('#box').hide();              // Instantly hide
$('#box').hide(1000);         // Hide with 1-second animation

```

### 2. .show()
Shows hidden elements.

```bash
$('#box').show();             // Instantly show
$('#box').show(1000);         // Show with animation

```

###  3. .toggle()
Toggles between .show() and .hide().
```bash
$('#box').toggle();           // Instantly toggle
$('#box').toggle(1000);       // Animate toggle

```

###  Full Example
```bash
<button id="btn">Toggle Box</button>
<div id="box" style="width:200px;height:100px;background:red;margin-top:10px;"></div>

<script>
  $('#btn').click(function() {
    $('#box').toggle(500);  // Toggle with animation
  });
</script>

```

## 4.  .fadeIn(), .fadeOut(), and .fadeTo()
Here’s a clear explanation of jQuery’s fade effects: .fadeIn(), .fadeOut(), and .fadeTo().

### 1. .fadeIn()
Gradually changes the opacity of a hidden element to make it visible.

```bash
$('#box').fadeIn();          // Default speed
$('#box').fadeIn(1000);      // Fade in over 1 second

```

### 2. .fadeOut()
Fades out (hides) a visible element by reducing opacity.

```bash
$('#box').fadeOut();         // Default speed
$('#box').fadeOut(1000);     // Fade out over 1 second

```

### 3. .fadeTo()
Fades the element to a specific opacity level.

```bash
$('#box').fadeTo(1000, 0.5);  // Fade to 50% opacity over 1 second

```
Use .fadeTo() when you want the element to remain partially visible, not fully hidden.


### Example: Full Demo
```bash
<button id="in">Fade In</button>
<button id="out">Fade Out</button>
<button id="half">Fade to 50%</button>

<div id="box" style="width:200px;height:100px;background:blue;display:none;margin-top:10px;"></div>

<script>
  $('#in').click(function() {
    $('#box').fadeIn(800);
  });

  $('#out').click(function() {
    $('#box').fadeOut(800);
  });

  $('#half').click(function() {
    $('#box').fadeTo(800, 0.5);
  });
</script>

```
Let me know if you want .slideDown(), .slideUp(), or .animate() effects next!


## 5. SlideDown and SlideUp
Here’s how jQuery’s slide effects work: .slideDown() and .slideUp().

### 1. .slideDown()
Slides an element down to show it (usually from height 0 to full height).

```bash
$('#box').slideDown();          // Default speed
$('#box').slideDown(1000);      // Slide down over 1 second

```

###  2. .slideUp()
Slides an element up to hide it (height shrinks to 0).

```bash
$('#box').slideUp();            // Default speed
$('#box').slideUp(1000);        // Slide up over 1 second

```

### 3. .slideToggle()
Toggles between .slideDown() and .slideUp().

```bash
$('#box').slideToggle(700);     // Toggle slide with animation

```

###  Example
```bash
<button id="toggleBtn">Toggle Slide</button>

<div id="box" style="width:200px; height:100px; background:green; display:none; margin-top:10px;"></div>

<script>
  $('#toggleBtn').click(function() {
    $('#box').slideToggle(600);
  });
</script>

```


## 6. animate() Method
The .animate() method lets you create custom animations by changing CSS properties with numeric values over time.

```bash
$(selector).animate(properties, duration, easing, complete);
```

* properties: Object of CSS properties to animate (numeric values only, like width, height, opacity, margin, left, top, etc.)
* duration: Time in milliseconds or strings 'slow', 'fast'
* easing: Animation speed curve ('linear' or 'swing') — 'swing' is default
* complete: Callback function after animation finishes

### Example: Animate width and height
```bash
$('#box').animate({
  width: '300px',
  height: '200px',
  opacity: 0.5
}, 1000, 'swing', function() {
  console.log('Animation complete!');
});

```

####  Animate position
```bash
$('#box').animate({
  left: '+=100px',    // Move 100px right relative to current position
  top: '-=50px'       // Move 50px up
}, 800);

```

#### Chaining animations
```bash
$('#box')
  .animate({width: '300px'}, 500)
  .animate({height: '150px'}, 500)
  .animate({opacity: 1}, 500);

```

###  Stop an animation
```bash
$('#box').stop();          // Immediately stop current animation
```


## 7. What is Method Chaining?
Because most jQuery methods return the jQuery object itself, you can “chain” methods together like this:

```bash
$('#box').css('color', 'red').slideUp(500).slideDown(500);
```

1. Set the text color to red.
2. Slide the element up over 0.5 seconds.
3. Then slide it down over 0.5 seconds.

```bash
<button id="btn">Click me</button>
<div id="box" style="width:200px; height:100px; background:blue; color:white;">
  Hello!
</div>

<script>
  $('#btn').click(function() {
    $('#box')
      .css('background-color', 'green')
      .slideUp(500)
      .slideDown(500)
      .fadeOut(500)
      .fadeIn(500);
  });
</script>

```

### Why use chaining?

* Cleaner code — no need to repeat selectors.
* More efficient, fewer DOM queries.
* Easy to read sequences of operations.


## 8. parent(), parents(), parentutility closest, and offestparse

###  1. .parent()
Returns immediate parent of the selected element.

```bash
<div class="grand">
  <div class="parent">
    <p class="child">Hello</p>
  </div>
</div>

<script>
  $('.child').parent().css('border', '2px solid red');
</script>


```
Selects only .parent, not .grand.


### 2. .parents()
Returns all ancestors (not just the immediate one), up the DOM tree.

```bash
$('.child').parents('.grand').css('border', '2px solid blue');

```
 Finds .grand (any matching ancestor).


 ### 3. .closest(selector)
Returns the first ancestor (including itself) that matches the selector.

```bash
$('.child').closest('.grand').css('background', 'yellow');

```
Similar to .parents(), but stops at the first match going up.


### 4. .offset()
Gets or sets the position relative to the document (top-left corner).

#### ➕ Get position
```bash
let position = $('#box').offset();
console.log(position.top, position.left);

```

#### ➕ Set position
```bash
$('#box').offset({ top: 100, left: 200 });
```
🔹 Note: The element must be positioned (relative, absolute, or fixed).


### 5. Summary Table
| Method       | Purpose                                   | Example                      |
| ------------ | ----------------------------------------- | ---------------------------- |
| `.parent()`  | Immediate parent                          | `$('.el').parent()`          |
| `.parents()` | All ancestors                             | `$('.el').parents()`         |
| `.closest()` | Closest matching ancestor (or itself)     | `$('.el').closest('.class')` |
| `.offset()`  | Get/set position relative to the document | `$('#box').offset()`         |

