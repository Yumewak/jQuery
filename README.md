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
