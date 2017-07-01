
# JavaScript 101

---

## About me

* @ericmasiello
* eric.j.masiello@gmail.com
* Fullstack JavaScript Engineer @ Vistaprint Digital
* Co-Instructor for FEWD 31
* Co-Author of Mastering React Native

--

### Buy Me :)

<img src="img/mastering-react-native.png" style="max-height: 450px; border-width: 0; box-shadow: none;" />

<a target="_blank" href="https://www.amazon.com/gp/product/1785885782/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=1785885782&linkCode=as2&tag=ericmasiello-20&linkId=0b797f6960a050d6567fd26505307fec">Mastering React Native</a><img src="//ir-na.amazon-adsystem.com/e/ir?t=ericmasiello-20&l=am2&o=1&a=1785885782" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />

---

## Agenda

1. TODO
2. TODO
3. TODO

---

# Introduction to Programming

The computer will do what you tell it to do.

--


## What is a Program

A __program__ is a set of instructions that you write to tell a computer what to do

--

## What Is Programming

__Programming__ is the task of writing those instructions in a language that the computer can understand.


--

## Becoming A Programmer

It isn't about the programming language - it's a way of thinking.

--

## How Computers 'Think'

They don't.

Buuut, they pretend to by sequentially executing simple instructions.

The only things a computer knows are the things we tell it.

-- 

## Low-level Programming Language
Assembly Code

```
global  _start
section .text
_start:
    ; write(1, message, 13)
    mov     rax, 1                  
    mov     rdi, 1                  
    mov     rsi, message            
    mov     rdx, 13                 
    syscall                         
    write

    ; exit(0)
    mov     eax, 60                 
    xor     rdi, rdi                
    syscall                         
message:
    db      "Hello, World", 10
```

--

## High-level Programming Language
JavaScript

```
alert('Hello, World!')
```

---

## What Is JavaScript?

- Insanely popular
- High level syntax, low barrier to entry
- The only language that runs in the browser
- Can be used "server-side" or "client-side"

Note:

- Hasn't always been only browser language, nor will it always be (probably)
- Runs on the server, in robots, databases, etc

--

### In the Beginning, There was HTML

<img src="img/html.jpg" style="max-width:800px; margin-bottom: 20px;">

<small>Credit: A Look Back at 20+ Years of Website Design - Myia Kelly</small>

Note:

- Internet predates web pages (developed by military and universities for information sharing)
- WWW and HTML invented at CERN in the late 80s, early 90s in large part by Tim Berners-Lee
- No styles, no interactivity - just text and links

--

### Make it Pretty(ish)

<img src="img/styles.jpg" style="max-width:800px; margin-bottom: 20px;">

<small>Credit: A Look Back at 20+ Years of Website Design - Myia Kelly</small>

--

### Make it Interactive!

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

---

## What Can JavaScript Do?

Respond to user interaction

- https://generalassemb.ly/education/digital-marketing
- https://isl.co/
- https://websdev.github.io/stencil

---

## What's the DOM?

--

### DOM

* Document Object Model
* Tree structure
* Allows JavaScript to read or manipulate the HTML of a webpage

Note:
- This includes changing CSS properties
- Or adding/removing CSS classes from HTML elements

--

### The Family Tree

![DOM Tree](img/dom.png)

---

## Syntax

__Syntax:__ Spelling and grammar rules of a programming language. 


Note:
Like with any language, there are formal rules around how to write it. This is the syntax.

--

## JavaScript Syntax Examples

* Semicolon - end of a statement
* Quotation Marks - a String (of characters)

```javascript
document.getElementById('stopButton').onclick = illuminateRed;
```

--

## JavaScript Syntax - Comments

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

## "Comment Out"
Use comments to stop the program from running one or more lines of code

```js
// This line runs
console.log('Hello world!');

// These are commented out
// console.log('Hello FEWD');
// console.log('Hello GA');
```

---

## Definitions

--

### Function

A named, self-contained set of instructions that is reusable. A "recipe" in our programming-as-cooking metaphor.

```javascript
function makeGrilledCheese() {
  ...
}
```

Functions can be easily rerun (e.g. on every click, run these instructions)

--

### Event

A user interaction

e.g. click, scroll, mouseover, etc

--

### Event Listener/Handler

A `function` whose job is to respond to some user input.

--

### Example

```js
document.getElementById('primary').onclick = function() {
 // do stuff!
}
```

---


## How we solve problems in JavaScript

1.  Find some elements on the page
2.  Listen for some user interaction (click, scroll, mouseover)
3.  Respond to that event
    - Add, remove or modify HTML
    - Add, remove or modify CSS

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

## Traffic Light

http://codepen.io/ericmasiello/pen/vxbgXo
- Fork this on Codepen

---

## Variables

What are variables?

--

### Variables

JavaScript variables are containers for storing data values.

--

### Variables

```javascript
var a = 13;
```

--

### Variables

We can tell our program to remember values for us to use later on.

The action of saving a value to a variable is called assignment.

--

### Variable Declaration

Telling our program that we wish to make a variable. We choose the name.

```javascript
var a;
```

--

### Variable Assignment

```javascript
a = 13;
```

--

### Variable Assignment and Declaration

```javascript
// Do assignment and declaration separately
var a;
a = 13;

// Do assignment and declaration at the same time
var b = a + 2;
```

--

### Variable Reassignment

```javascript
var a = 'Eric';

a = 'Erika';
```

--

### Variable Naming Conventions

Use "camel case":
- start with lower case letter
- each new word is capitalized

```javascript
var numberOfStudents = 20;
```

---

## Data Types

Parts of variable:

```js
var numberOfStudents = 20;
```

- name: `numberOfStudents`
- value: `10`

--

### Data Types

What can those _values_ be??

--

### JavaScript Data Types

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

### String

Text, a collection of characters.

```javascript

var firstName = 'Erika';

var lastName = 'Lewis';

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

## Score Keeper

[CodePen](https://codepen.io/ericmasiello/pen/VWXWEB?editors=1010)

---

## Thank you!

