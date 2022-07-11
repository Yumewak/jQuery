# jQuery

## What is jQuery?
```
jQuery created by John Resig, is a JavaScript library that will prevent our fingers from breaking
by making our javascript code a lot easier to read, a lot easier to debug and a lot faster to write
it's similar to Bootstrap, a code that someone else wrote.
```
```javascript
for (i=0; i<document.querySelectorAlll("button").length; i++) {
    document.querySelectorAll("button")[i].addEventListener("click", function() {
        document.querySelector("h1").style.color = "red";
    });
}
// With jQuery
$("button").click(function(){
  $("h1").css("color", "red")
});
```
```javascript
//Here's another example
document.querySelector("h1") //Vs.
jQuery("h1") //Vs.
$("h1)
```

## How to incorporate jQuery into websites
```
There's two options to incorporate jQuery into our website
a.- Download all the jQuery code files through their download page
b.- Use a CDN
```
```
1.- Create all the files html, css, js, and make a boilerplate
2.- Link all the files and creato one "h1" and five buttons that says click me
3.- Use the same code of the last lesson to write some jQuery that's going to change the text color of "h1" to red
```
```javascript
// Target change it's css color property to red
$("h1").css("color", "red");
```
```
Go back to the google hosted libraries and copy the script tag, and paste that above our javascript tag

The position where you place your jQuery scrit tag is really important, if we placed
it below our index.js then you'll see that it no longer works.
The reason is because the browser will read the code from top to bottom

The other way that it might mess up is that if you had both of the script tags inside the head section
```
```javascript
//You can use this "ready()" method to check wheter if our jQuery library is ready
$(document).ready(function() {
    $("h1").css("color", "red");
})
//When you come across websites, you'll often see this line of code, but another way of doing exactly the same
//thing is simply to include all scripts at the end of our website and in the right order.
```
[ready() Method](https://api.jquery.com/ready/)

## How minification works
```
Minified version it's javascript code where all of the spaces, the new lines and the comments
have been removed from the file to try and reduce its size.
By minifying we get rid of those things and make our website load much faster

Exercies: Use minifier.org to minfying the drum js file.
```
[Minify](https://minifier.org/)
[JavaScript Minifier](https://www.toptal.com/developers/javascript-minifier)

## Selecting elements with jQuery
```
Manipulating styles with jQuery
First we select our element in our web page in order to manipulate it
```
```javascript
// Vanilla JavaScript
document.querySelector("h1");
// jQuery
$("h1"); //Using jQuery method to select h1

// Vanilla JavaScript
document.querySelector("button");
// jQuery
$("button");

// Vanilla Javascript
document.querySelector("h1").style.color="red";
// jQuery
$("h1").css("color", "red");

//Get the current value
console.log($("h1").css("color"));
console.log($("h1").css("font-size"));
```
```
Remember. With this css method, if you have a single property in, then you're getting the value of it.
And if you have two properties in it, then you're setting the value
```

### Separation of conserns
```
Separate our conserns
1.- Keep our javascript code all about behavior
2.- Keep our style code all about the appearence
3.- Keep our HTML all about content
```
```css
/* For the next examples use this styles inside your styles file: */
.big-title {
    font-size: 10rem;
    color: yellow;
    font-family: cursive;
}

.margin-50 {
    margin: 50px;
}
```
```javascript
//Use jQuery to add a class
$("h1").addClass("big-title");
//Use jQuery to remove a class
$("h1").removeClass("big-title");
//Use jQuery to toggle a class
$("h1").toggleClass("big-title");

// Add or remove multiple classes
$("h1").addClass("big-title margin-50");
// All we need to do is just to include them inside the same set of quotation marks but with a spaces in between

// See whether or not if our element has a particular class
$("h1").hasClass("margin-50");
```

## Manipulating text with jQuery
```javascript
.text()
$("h1").text("Bye")//This will change the text in the h1 element
console.log($("h1").text())//This will get the text of the h1 element

$("button").text("Don't Click Me")//This will change the text in every single button
console.log($("button").text())//This will get the text of every single button

//The .html() method works similar to InnerHTML in the DOM
$("button").html("<em>Don't Click Me</em>") //This will insert an <em> tag like the InnerHTML
```

## Manipulatin attributes with jQuery
```html
<! -- Use the following HTML code to practice this lesson in your jQuery folder -->
    <h1 class="big-title margin-50">Hello.</h1>
    <img src="drum.png" alt="">
    <a href="https://www.google.com">Search</a>
```
```
If we wanted to be able to get and set these attributes on the fly using JavaScript and jQuery
we can do it whit the folloing code
```
```javascript
//To get attribute attr("attribute name")
console.log($("img").attr("src"));//This will get the value of the attribute

//To get and set attribute attr("attribute name", "attribute set it")
$("a").attr("href", "https://yahoo.com");//This will get the value and set it to yahoo
```
```
If there is a second input then we're going to set it to that input
And if there isn't one then we're going to get the value of the attribute
```
```javascript
//Remember, a class is also an HTML attribute
//Write in your console
$("h1").attr("class")
```

## Adding event listener with jQuery
```html
<--! For this subject add an input -->
    <input type="text">
```
```javascript
//Vanilla JavaScript
document.querySelector("h1").addEventListener("click", function(){
    document.querySelector("h1").style.color="purple";
});
//jQuery
$("h1").click(function(){
    $("h1").css("color", "purple");
});
```
```javascript
// Previously if we wanted to add an event listener to all five buttons we had to write a for loop, but with jQuery its not necessary
//Vanilla JavaScript
for (let i = 0; i < 5; i++) {
    document.querySelectorAll("button")[i].addEventListener("click", function(){
        document.querySelector("h1").style.color="red";
    });    
}
//jQuery
$("button").click(function(){
    $("h1").css("color", "purple")
});
```
```javascript
//Keypress event addEventListener
$("input").keypress(function(event){ //keydown also works
    console.log(event.key)
});
//This is similar to add an event listener to the entire web page like "document.addEventListener("keydown", function (event)..."
$(document).keypress(function(event){
    console.log(event.key)
});
//Another way to add an event listener to the entire web page
$("body").keypress(function(event){
    console.log(event.key)
});
```
```
Challenge: Update the code that we wrote just now so that whenever your press a key inside our web site
it gets show inside the h1
```
```javascript
// Challenge vanilla JavaScript
document.addEventListener("keydown", function(event){
    document.querySelector("h1").textContent=event.key;
})
// Challenge jQuery
$(document).keypress(function(event){
    $("h1").text(event.key)
});
```
```javascript
//Method on() takes two parameters, the first one is the event that you're looking to listen for
//and the second parameter is going to be usually the callback function
$("h1").on("mouseover", function(){
    $("h1").css("color", "purple");
})
```

## Adding and removing elements with jQuery
```javascript
//Inside the parentheses you can put down the HTML that you want to add before the h1 (for example)
//before()
//after()
//prepend()
//append()

//Before method
$("h1").before("<button>New</button>");
//After method
$("h1").after("<button>New</button>");
//Prepend and append method
//The difference between prepend and before is that prepend will add your new HTML element into the item that you've selected just after the opening tag
$("h1").prepend("<button>New</button>");
$("h1").append("<button>New</button>");

//Do this in your console and inspect the "New" buttons created, see that its been added inside the h1

//Remove method
//Select the element that you want to remove and use the "remove()" method
$("button").remove()
```

## Website animations with jQuery
```javascript
// This method is an animation that will hide, reappear and toggle (hider-show) the selected element
.hider()
.show()
.toggle()

// Reduce the opacity of the selected element and the it will hide it, fade in does the opposite and toggle will change between (out-in)
.fadeOut()
.fadeIn()
.fadeToggle()

// Collapses our element or toggle
.slideUp()
.slideDown()
.slideToggle()
```
```
Control over the animations
.animate() Allows you to define some custom css that you want to gradually animate towards
Remember: In between the curly braces you can only add the CSS rules that have a numeric value
Example: You can't change the color to red
If you want to include a unit measure simbol like "%" you must do it as a string
```
```javascript
.animate({margin: "20%"});
.animate({height: "20px"}, 500);
```
```
More than one animation, you can chain them together
```
```javascript
$("h1").slideUp().slideDown().animate({opacity: 0.5});
```
```
We chained three methods together, this wont do that all three happened at the same time, it will do it in order.
```
```
Never try to remember or memorize anything
Programming is basically like an open book exam
Try to understand how things work
```
