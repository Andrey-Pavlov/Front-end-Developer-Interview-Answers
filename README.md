#Front-end Job Interview Questions

This repo contains a number of front-end interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

[Rebecca Murphey](http://rmurphey.com/)'s [Baseline For Front-End Developers](http://rmurphey.com/blog/2012/04/12/a-baseline-for-front-end-developers/) is also a great resource to read up on before you head into an interview.

**Note:** Keep in mind that many of these questions are open ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would.

## <a name='toc'>Table of Contents</a>

  1. [Original Contributors](#contributors)
  1. [General Questions](#general)
  1. [HTML Questions](#html)
  1. [CSS Questions](#css)
  1. [JS Questions](#js)
  1. [jQuery Questions](#jquery)
  1. [Coding Questions](#jscode)
  1. [Fun Questions](#fun)

####<a name='contributors'>Original Contributors:</a>

The majority of the questions were plucked from an [oksoclap](http://oksoclap.com/) thread created originally by [Paul Irish](http://paulirish.com) ([@paul_irish](http://twitter.com/paul_irish)) and contributed to by the following individuals:

* [@bentruyman](http://twitter.com/bentruyman) - http://bentruyman.com
* [@cowboy](http://twitter.com/cowboy) - http://benalman.com
* [@ajpiano](http://ajpiano) - http://ajpiano.com
* [@SlexAxton](http://twitter.com/slexaxton) - http://alexsexton.com
* [@boazsender](http://twitter.com/boazsender) - http://boazsender.com
* [@miketaylr](http://twitter.com/miketaylr) - http://miketaylr.com
* [@vladikoff](http://twitter.com/vladikoff) - http://vladfilippov.com
* [@gf3](http://twitter.com/gf3) - http://gf3.ca
* [@jon_neal](http://twitter.com/jon_neal) - http://twitter.com/jon_neal
* [@wookiehangover](http://twitter.com/wookiehangover) - http://wookiehangover.com
* [@iansym](http://twitter.com/iansym) - http://twitter.com/iansym

**[[⬆]](#toc)**

####<a name='general'>General Questions:</a>

* What did you learn yesterday/this week?

* What excites or interests you about coding?

* Talk about your preferred development environment. (OS, Editor, Browsers, Tools etc.)

* Can you describe your workflow when you create a web page?

* Can you describe the difference between progressive enhancement and graceful degradation?<br/>
progressive enhancement - from less functionality growing to full functional<br/>
graceful degradation - made full functional and then made fallbacks<br/>
  * Bonus points for describing feature detection
    check is feture is exist, use fallback if not
    
* Explain what "Semantic HTML" means.<br/>
 Html consist of only document structure information, without styling and behaviour
 
* How would you optimize a websites assets/resources? (or just customer says: "Optimize my site!")
What does it mean - "Optimize my site!". Figure out customer problems. (loading or rendering or markup or ...)<br/>
Our tookls - dev tools, page speed, fiddler, wireshark<br/>
Key measuremens - loading speed, number of requests, images sizes etc.<br/>
Put css on top<br/>
Put scripts on bottom<br/>
Avoid @import in CSS (new request, DOM rerendering (reflow or repaint))<br/>
Avoid DOM microinsertions in loop (use document.createElement())<br/>
Listen bubbling event (don't add evetlistener for each "row" - save memory)<br/>
Pagination, Visualization, Infinity Scroll (avoid fetch 10000 items to show only 10)<br/>
Deffered plugins initialization (on first click, for example)<br/>
Minimize Http calls,<br/>
Bundling:<br/>
  -css and js, spritesheets<br/>
  -main and vendor<br/>
  -add cache busting suffix<br/>
Minification<br/>
CDN (cache posibility, closer to user, CORS requests not icluded in browser number of requests restrictions)<br/>
Cache headers: cache-control, expired, max-age, e-tag<br/>
Images:<br/>
 -Avoid image resize by css (4k image for icon)
 -Server image resize (/img.png?w=100&h=100)
 -Prevent images download before scroll to them (data-src => src)
Server-side caching (Redis, KeyValue storage)<br/>
Check memory leak (Browsers DevTools)<br/>
JS profiling and code optimization (Browsers DevTools)<br/>
Gzip or compile gzip<br/>
keep-alive header - same connection for several requests<br/>
web-sockets<br/>
Server asynchronous handlers<br/>
Web-workers (long calculations, don't manipulate with DOM)<br/>
Replace JS animation by CSS<br/>
Async and Deffered script attributes (async for 3rd party scripts)<br/>
User AMD (RequireJS or framework built-in)<br/>
Virtual DOM<br/>

* Why is it better to serve site assets from multiple domains?<br/>
* How many resources will a browser download from a given domain at a time?<br/>
depends on browser  2 - 8<br/>
* If you jumped on a project and they used tabs and you used spaces, what would you do?<br/>
  Generalize and document style guide. Suggest the project utilize something like EditorConfig (http://editorconfig.org)<br/>
* Write a simple slideshow page<br/>
  * Bonus points if it does not use JS.<br/>
* If you could master one technology this year, what would it be?<br/>
  Advanced algorithm's<br/>
* Explain the importance of standards and standards bodies.<br/>
  Without standards you cant be sure that you code or design works as you expect to.<br/>
* What is FOUC? How do you avoid FOUC?<br/>
  Flash of unstyled content. Put css in head. You can also made loader (but i did not like it)<br/>


**[[⬆]](#toc)**

####<a name='html'>HTML Questions:</a>

* What's a `doctype` do?

It tells the browser which version of HTML (or XML) it needs to use while rendering the page.

* What's the difference between standards mode and quirks mode?

"Quirks" mode is used for legacy browsers, while "standards" mode follows the W3C specification.

* What are the limitations when serving XHTML pages?
  More strict that classic HTML, XHTML does not have good browser support.
  * Are there any problems with serving pages as `application/xhtml+xml`?
  IE 8 and older does not handle it
* How do you serve a page with content in multiple languages?
 From html point of view use UTF. mostly server side problem.
  * What kind of things must you be wary of when design or developing for multilingual sites?
  right to left languages
* What are `data-` attributes good for?
 Store custom data in Dom node
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
 LocalStorage, video, data-*, canvas
* Describe the difference between cookies, sessionStorage and localStorage.
cookies only 4kb and send allways
sessionStorage 5mb for session
localstorege 5mb

**[[⬆]](#toc)**

####<a name='css'>CSS Questions:</a>

* Describe what a "reset" CSS file does and how it's useful.
set default's to main elements
(like marhin, paddings, border to 0)
* Describe Floats and how they work.
Align element on right or left side, and text will flow around it
* What are the various clearing techniques and which is appropriate for what context?

* Explain CSS sprites, and how you would implement them on a page or site.
Css sprite is set of small images stored in one image.
background property will help you
* What are your favourite image replacement techniques and which do you use when?
* CSS property hacks, conditionally included .css files, or... something else?
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?<br/>
  Shim and polyfills. Vendor prefixes
* What are the different ways to visually hide content (and make it available only for screen readers)?
media queries
* Have you ever used a grid system, and if so, what do you prefer?
bootstrap3 and 4 now
* Have you used or implemented media queries or mobile specific layouts/CSS?
Used
* Any familiarity with styling SVG?
* How do you optimize your webpages for print?
media query print
* What are some of the "gotchas" for writing efficient CSS?
OSCSS, AtomCSS, BEM
* What are the advantages/disadvantages of using CSS preprocessors? (SASS, Compass, Stylus, LESS)
  * If so, describe what you like and dislike about the CSS preprocessors you have used.
* How would you implement a web design comp that uses non-standard fonts?
Webfonts (font services like: Google Webfonts, Typekit etc.)<br/>
Font Awesome<br/>
* Explain how a browser determines what elements match a CSS selector?<br/>
CSS selectors from right to left.<br/>
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
box model it's how you calc size of box<br/>
box-sizing can help you set different aproaches<br/>
content-box border-box<br/>

**[[⬆]](#toc)**

####<a name='js'>JS Questions:</a>

* Explain event delegation
event delegation it's when parant recieve a event
* Explain how `this` works in JavaScript
depends on how it's call
* Explain how prototypal inheritance works
* How do you go about testing your JavaScript?
QUnit Jasmine and bunch of staff
* AMD vs. CommonJS?
* What's a hashtable?
datasctructure
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`. 
  * What needs to be changed to properly make it an IIFE?
* What's the difference between a variable that is: `null`, `undefined` or `undeclared`?
  * How would you go about checking for any of these states?
* What is a closure, and how/why would you use one?
* What's a typical use case for anonymous functions?
callback
* Explain the "JavaScript module pattern" and when you'd use it.
  * Bonus points for mentioning clean namespacing.
  * What if your modules are namespace-less?
* How do you organize your code? (module pattern, classical inheritance?)
* What's the difference between host objects and native objects?
* Difference between:
```javascript
function Person(){} var person = Person() var person = new Person()
```

* What's the difference between `.call` and `.apply`?
* explain `Function.prototype.bind`?
* When do you optimize your code?
* Can you explain how inheritance works in JavaScript?
* When would you use `document.write()`?
  * Most generated ads still utilize `document.write()` although its use is frowned upon
* What's the difference between feature detection, feature inference, and using the UA string
* Explain AJAX in as much detail as possible
* Explain how JSONP works (and how it's not really AJAX)
* Have you ever used JavaScript templating?
  * If so, what libraries have you used? (Mustache.js, Handlebars etc.)
* Explain "hoisting".
* Describe event bubbling.
* What's the difference between an "attribute" and a "property"?
* Why is extending built in JavaScript objects not a good idea?
* Why is extending built ins a good idea?
* Difference between document load event and document ready event?
* What is the difference between `==` and `===`?
* Explain how you would get a query string parameter from the browser window's URL.
* Explain the same-origin policy with regards to JavaScript.
* Describe inheritance patterns in JavaScript.
* Make this work:
```javascript
[1,2,3,4,5].duplicate(); // [1,2,3,4,5,1,2,3,4,5]
```
* Describe a strategy for memoization (avoiding calculation repetition) in JavaScript.
* Why is it called a Ternary expression, what does the word "Ternary" indicate?
* What is the arity of a function?
* What is `"use strict";`? what are the advantages and disadvantages to using it?

**[[⬆]](#toc)**

####<a name='jquery'>jQuery Questions:</a>

* Explain "chaining".
* Explain "deferreds".
* What are some jQuery specific optimizations you can implement?
* What does `.end()` do?
* How, and why, would you namespace a bound event handler?
* Name 4 different values you can pass to the jQuery method.
  * Selector (string), HTML (string), Callback (function), HTMLElement, object, array, element array, jQuery Object etc.
* What is the effects (or fx) queue?
* What is the difference between `.get()`, `[]`, and `.eq()`?
* What is the difference between `.bind()`, `.live()`, and `.delegate()`?
* What is the difference between `$` and `$.fn`? Or just what is `$.fn`.
* Optimize this selector:
```javascript
$(".foo div#bar:eq(0)")
```
* Difference between 'delegate()' and 'live()'?

**[[⬆]](#toc)**

####<a name='jscode'>Code Questions:</a>

```javascript
~~3.14
```
Question: What value is returned from the above statement?
**Answer: 3**

```javascript
"i'm a lasagna hog".split("").reverse().join("");
```
Question: What value is returned from the above statement?
**Answer: "goh angasal a m'i"**

```javascript
( window.foo || ( window.foo = "bar" ) );
```
Question: What is the value of window.foo?
**Answer: "bar"**
only if window.foo was falsey otherwise it will retain its value.

```javascript
var foo = "Hello"; (function() { var bar = " World"; alert(foo + bar); })(); alert(foo + bar);
```
Question: What is the outcome of the two alerts above?
**Answer: "Hello World" & ReferenceError: bar is not defined**

```javascript
var foo = [];
foo.push(1);
foo.push(2);
```
Question: What is the value of foo.length?
**Answer: `2`

```javascript
var foo = {};
foo.bar = 'hello';
```
Question: What is the value of foo.length?
**Answer: `undefined`

**[[⬆]](#toc)**

####<a name='fun'>Fun Questions:</a>

* What's the coolest thing you've ever coded, what are you most proud of?
* What are your favorite parts about the developer tools you use?
* Do you have any pet projects? What kind?
* What's your favorite feature of Internet Explorer?

**[[⬆]](#toc)**
