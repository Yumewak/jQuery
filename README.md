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

## Manipulating text with jQueri
```javascript
.text()
$("h1").text("Bye")//This will change the text in the h1 element
console.log($("h1").text())//This will get the text of the h1 element

$("button").text("Don't Click Me")//This will change the text in every single button
console.log($("button").text())//This will get the text of every single button

//The .html() method works similar to InnerHTML in the DOM
$("button").html("<em>Don't Click Me</em>") //This will insert an <em> tag like the InnerHTML
```
