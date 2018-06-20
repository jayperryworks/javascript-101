
# JavaScript 101

---

## About me

* @ericmasiello
* Fullstack JavaScript Engineer @ Vistaprint Digital
* Front-End Web Development (FEWD) Instructor at General Assembly
* Co-Author of _Mastering React Native_

--

## Your turn to share 🤗
* Your name
* Any programming experience? (HTML, JavaScript, C, etc.)
* What brought you here today

---

## Agenda

1. Introduction to programming
2. What is JavaScript?
3. JavaScript & the DOM
4. JavaScript syntax
5. Responding to "events"
6. BONUS: JavaScript variables and data types
7. BONUS: Node.js

---

## Setting expectations

2 hours is not a lot of time

---

## Introduction to programming

The computer will do what you tell it to do.

--


### What is a program (or app)?

A set of written instructions that explicitly tells the computer what to do

--

### What is programming

The task of writing those instructions in a language that the computer can understand.

--

### What is programming language

A formal language that specifies a _set of instructions_ that can be used to produce various kinds of output.

(e.g. JavaScript)

--

### Becoming a programmer

It isn't about the programming language - it's a way of thinking.

-- 

## Low-level Programming Language
Assembly Code

```
global  _start
section .text
_start:
    ; write(1, message, 13)
    mov  rax, 11
    mov  rdi, 1
    mov  rsi, message
    mov  rdx, 13
    syscall
    write

    ; exit(0)
    mov  eax, 60
    xor  rdi, rdi
    syscall
message:
    db  "Hello, World", 10
```

--

## High-level programming language
JavaScript

```
alert('Hello, World!');
```

---

## What is JavaScript?

- Insanely popular
- High level syntax, low(ish) barrier to entry
- The only language that runs in the browser
- Can be used "server-side" or "client-side"

Note:

- Hasn't always been only browser language, nor will it always be (probably)
- Runs on the server, in robots, databases, etc

--

### In the beginning, there was HTML

<img src="img/html.jpg" style="max-width:800px; margin-bottom: 20px;">

<small>Credit: A Look Back at 20+ Years of Website Design - Myia Kelly</small>

Note:

- Internet predates web pages (developed by military and universities for information sharing)
- WWW and HTML invented at CERN in the late 80s, early 90s in large part by Tim Berners-Lee
- No styles, no interactivity - just text and links

--

### Make it pretty(ish)

<img src="img/styles.jpg" style="max-width:800px; margin-bottom: 20px;">

<small>Credit: A Look Back at 20+ Years of Website Design - Myia Kelly</small>

--

### Make it interactive!

<img src="img/googlemaps.png" style="max-width:800px; margin-bottom: 20px;" alt="Google Maps">

Note:

- JavaScript was developed in 10 days by one developer (Brendan Eich) for Netscape. It needed to be done quickly so that it could gain adoption over Microsoft's browser language.
- Has evolved enormously since 1995 when it was created

--

## Java vs. JavaScript

Very, very, very different.

(But a little similar)

Note:

- Two completely different languages
- At around the time time JavaScript was created, Java was newish and had a lot of buzz
- The language was originally named as LiveScript
- Netscape renamed it to JavaScript to capitalize on the cachet of Java at the time
- If you ever do a job interview, don't confuse these two languages

--

## JavaScript vs. Javascript

- Officially, its "JavaScript"
- In reality, no one cares

<style type="text/css">
#javascript-vs-javascript {
    text-transform: none;
}
</style>

---

## JavaScript & the DOM

--

## JavaScript in the wild

- [Form Validation](https://formvalidation.io/guide/plugins/bootstrap/)
- [Dynamic Navigation](https://generalassemb.ly/education/digital-marketing)

--

### DOM

* Document Object Model
* Tree structure
* Allows JavaScript to read or manipulate the HTML of a webpage

Note:
- This includes changing CSS properties
- Or adding/removing CSS classes from HTML elements

--

### The family tree in code

```html
<html>
    <head>
        <title>The Title</title>
        <link rel="stylesheet" href="css/styles.css">
    </head>
    <body>
        <header>...</header>
        <header>...</header>
        <section>
            <h1>My Website!</h1>
            <p>lorem ipusm <a href="#">dolar</a></p>
        <section>
    </body>
</html>
```

--

### The family tree visualized

![DOM Tree](img/dom.png)

--

### How do we add JavaScript to a webpage?

### `<script></script>`

--

```html
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" type="text/css" href="css/styles.css">
  </head>
  <body>
    <!-- your webpage contents -->
    ...

    <script src="script.js"></script>
  </body>
</html>
```
Put it right before the closing `</body>` element

---

## Syntax

"...set of rules that defines the combinations of symbols that are considered to be a correctly structured \[code\] in that language."

\- [Wikipedia](https://en.wikipedia.org/wiki/Syntax_(programming_languages)


Note:
Like with any language, there are formal rules around how to write it. This is the syntax.

--

### JavaScript syntax examples

* Semicolon - end of a statement
* Quotation Marks - a String (of characters)

```javascript
document.getElementById('stopButton').onclick = illuminateRed;
```

--

### JavaScript syntax - comments

```javascript
// Single Line Comments
```

```javascript
/*
Multi
line
comments
*/
```

--

### "Comment out"
Use comments to stop the program from running one or more lines of code

```js
// This line runs
console.log('Hello world!');

// These are commented out
// console.log('Hello FEWD');
// console.log('Hello GA');
```

--

### Basic JavaScript Syntax

[https://www.w3schools.com/js/js_syntax.asp](https://www.w3schools.com/js/js_syntax.asp)

---

## Responding to &ldquo;events&rdquo;

`event + event handler => run some code`

Note:
- Let's cover some basic definitions

--

### Event

Typically a user interaction

e.g. click, scroll, mouseover (hover), etc.

```html
<!-- I want to know when someone clicks on this button -->
<button id="dealButton">Deal cards!</button>
```

--

### Event listener/handler

A `function` whose job is to respond to some user input.

```js
// I want to know whenever someone *clicks* on the element
// with an id of "dealButton"
```

--

### Function

A named, self-contained set of instructions that is reusable.

```javascript
function dealRandomCard() {
  // code here that picks a card at random
}
```

Functions can be easily rerun (e.g. on every click, run these instructions)

--

### Example

JS
```js
function dealRandomCard() {
  // code here that picks a card at random
}

// whenever someone clicks the html tag with an id="dealButton",
// run the dealRandomCard function
document.querySelector('#dealButton').onclick = dealRandomCard;
```
HTML
```html
<!-- I want to know when someone clicks on this button -->
<button id="dealButton">Deal cards!</button>
```
---

## How we solve problems in the browser with JavaScript

1.  Find some elements on the page
2.  Listen for some user interaction (click, scroll, mouseover)
3.  Respond to that event
    - Add, remove or modify HTML
    - Add, remove or modify CSS
    - or anything else :)

--

<img src="img/js/step1.png" style="border: 0; box-shadow: none;" alt="How JS Works">

--

<img src="img/js/step2.png" style="border: 0; box-shadow: none;" alt="How JS Works">

--

<img src="img/js/step3.png" style="border: 0; box-shadow: none;" alt="How JS Works">

--

<img src="img/js/step4.png" style="border: 0; box-shadow: none;" alt="How JS Works">

--

<img src="img/js/step5.png" style="border: 0; box-shadow: none;" alt="How JS Works">

--

<img src="img/js/step6.png" style="border: 0; box-shadow: none;" alt="How JS Works">

---

![GeneralAssemb.ly](img/exercise_icon_md.png)

## Traffic light

http://codepen.io/ericmasiello/pen/vxbgXo
- Fork this on Codepen

--

## Traffic light Assignment
*15 mins*
1. Make the slow button turn the 2nd light yellow
2. Make the go button turn the last light green
3. **BONUS:** Make it so that I can click the lights themselves to turn them on

*If you finish early, help others around you if they're stuck.*

---

## BONUS: Variables & data types

--

### Variables

JavaScript variables are containers for storing data values.

--

### Variables

```javascript
var age = 13;
```

--

### Variable declaration

* Tell our program that we wish to make a variable
* We choose the name

```javascript
var age;
```

--

### Variable assignment

Give our declared variable a value

```javascript
age = 13;
```

--

### Variable assignment and declaration

```javascript
// Do assignment and declaration separately
var a;
a = 22;

// Do assignment and declaration at the same time
var b = a + 2;
```

--

### Variable reassignment

```javascript
var a = 'Eric';

a = 'Erika';
```

--

### Variable naming conventions

Use "camel case":
- start with lower case letter
- each new word is capitalized

```javascript
var numberOfStudents = 20;
```

---

## Data types

Parts of variable:

```js
var numberOfStudents = 20;
```

- name: `numberOfStudents`
- value: `20`

--

### Data types

What can those _values_ be??

--

### JavaScript data types

- *Number*
- *String*
- *Boolean*
- Undefined
- Null
- Object
- Function

--

### Number

```javascript

// We call this type of number an "integer"
var myInteger = 10;

// And this type a "float"
var myFloat = 10.13093;

var sum = myInteger + myFloat;
```

--

### Common JavaScript Math Operators

| Operator        | Description           | Example  |
| ------------- |:-------------:| -----:|
| `+`      | Addition | `x = y + 2;` |
| `-`      | Subtraction | `x = y - 2;` |
| `*`      | Multiplication | `x = y * 2;` |
| `/`      | Division | `x = y / 2;` |
| `%`      | Modulus (division remainder) | `x = y % 2;` |

--

### String

Text, a collection of characters.

```javascript

var firstName = 'Eric';

var lastName = 'Masiello';

// fullName = 'Eric Masiello'
var fullName = firstName + ' ' + lastName;
```

Note:

This operation is called concatenation

--

### Boolean

True or False

```javascript

var lightOn = true;

function turnLightsOff() {
  lightOn = false;
}
```

---

![GeneralAssemb.ly](img/code_along.png)

## Score keeper

[CodePen](https://codepen.io/ericmasiello/pen/VWXWEB?editors=1010)
- Fork this on Codepen

--

## Score keeper Assignment
*15 mins*
1. Add a button labeled "Double" that takes the current score and doubles it
2. Add a button labeled "Half" that takes the current score and cuts it in half

*If you finish early, help others around you if they're stuck.*

---

## BONUS: Node.js

<img src="img/nodejs.png" style="max-height: 450px; border-width: 0; box-shadow: none;" />

--

### Node.js
* Developed in 2009
* Built on top of Google Chrome's _V8_ JavaScript engine
* Open source runtime environment for running server-side JavaScript applications
* Install the _LTS_ version from https://nodejs.org/

--

### Sample Node app

* Copy this code http://bit.ly/2tpAOXZ
* Save as add.js
* Open your command line tool
```
node add.js 3 4
```

---

## Resources

* **Books**
* [You Don't Know JS: Up & Going](http://shop.oreilly.com/product/0636920039303.do)
* [HTML and CSS: Design and Build Websites](https://www.amazon.com/HTML-CSS-Design-Build-Websites/dp/1118008189/ref=sr_1_2?ie=UTF8&qid=1502034868&sr=8-2&keywords=html+css+javascript)
* **Online**
* [Code Academy (Free)](https://www.codecademy.com/)
* **In Person Courses**
* [Web Development Immersive (Full Time)](https://generalassemb.ly/education/web-development-immersive)
* [Front End Development (Part time)](https://generalassemb.ly/education/front-end-web-development)
* [JavaScript (Part Time)](https://generalassemb.ly/education/javascript-development)

---

## Thank you! 🙏🏼🙏🏼🙏🏼

