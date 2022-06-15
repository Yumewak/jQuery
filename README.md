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
