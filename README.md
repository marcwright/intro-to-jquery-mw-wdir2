---
title: Intro To jQuery
type: lesson
duration: "1:25"
authors:
    creators: Gerry Mathe (LON), Elie Schoppik (SF)
    editors: Marc Wright (ATL)
competencies: Front-end intro
---

# ![Imgur](http://i.imgur.com/peEEWB0.png) Intro To jQuery

## Objectives
*After this lesson, students will be able to:*

- Describe jQuery and the context to use it
- Include jQuery in your projects
- Practice using jQuery selectors


## Preparation
*Before this lesson, students should already be able to:*

- Use vanilla JavaScript to manipulate the DOM
- Use a text editor
- Explain CSS selectors

## Contents

* [WHAT IS JQUERY?](#what-is-jquery)
	* [LIBRARY VS FRAMEWORK](#library-v-framework) 
* [ADD JQUERY TO YOUR APP](#add-jquery)
	* [CDN](#cdn)	
	* [DOWNLOAD JQUERY DIRECTLY](#download-directly)
	* [MINIFICATION](#min)
	* [JQUERY VERSIONS](#versions)
* [DOM MANIPULATION WITH JQUERY](#dom-manipulation-with-jquery)
	* [DIFFERENCES IN JQUERY SYNTAX](#syntax)
	* [SELECT AN ELEMENT](#select-an-element)
 	* [SELECT AN ELEMENT AND CHANGE IT'S CONTENT](#change-element-content)
 	* [APPEND A DOM ELEMENT](#append-an-element)
 	* [MODIFY STYLES (CSS)](#modify-styles)
 	* [ADD AND REMOVE ELEMENTS](#modify-styles)
 	* [FORMS](#forms)
* [EXERCISES](#exercises)
* [BONUS](#bonus)
* [CONCLUSION](#conclusion)

--
# <a name="what-is-jquery">WHAT IS JQUERY?</a>

![Imgur](http://i.imgur.com/ylb6WX9.gif)
<details>
  <summary>What is jQuery?</summary>
    <br>
      jQuery is a 3rd-party library that is intended to make front-end development tasks — particularly those involving DOM selection and manipulation — easier, faster, and more fun.
    <br>
</details>


### <a name="library-v-framework">LIBRARY VS FRAMEWORK</a>
Question: Has anybody used a Javascript library or a framework before?


<details>
  <summary>**YOU DO (60 seconds)** -- What is a library?</summary>
    <br>
      A library is a collection of Javascript functions and methods that make writing Javascript an easier, smoother and ultimately shorter experience.
    <br><br>
      Under the hood, all Javascript libraries are written using Javascript. So technically, there is nothing you can do using a library that can't already be done using Vanilla JS.
    <br><br>
      There are [tons of them](https://www.javascripting.com/).
    <br><br>
      Some are suited for particular uses like data visualization(D3.js), 3D imaging (Three.js), charts (Chart.js), autocomplete functionality (Typeahead.js) and many more...
    <br>  

</details>

**I DO (60 seconds)** -- Draw a Venn Diagram of the Javascript world.


<details>
  <summary>**YOU DO (60 seconds)** -- What is a framework?</summary>
    <br>
      A framework not only provides tools like a library does, but also defines the architecture of your code (e.g., syntax, folder structure). Basically, it's a set of rules you have to follow.
    <br><br>
      Let's pretend the human body is a web app. Our body has a framework (skeleton) and various organs (libraries) that perform specific tasks. For example, the heart pumps our blood, the lungs process oxygen, etc. Our organs rely on the skeleton for structure.
    <br><br>
      Examples: AngularJS, Ember.js, React.js, Backbone.js, Ionic.js.
    <br>
</details>


Sometimes "library" and "framework" are used interchangeably, but they are not the same. The difference will be more apparent as you get some experience with both as the course progresses.


#### So, what does jQuery offer us?

- jQuery helps us manipulate the DOM, allowing us to perform complex manipulations using less code with less hassle.  
- jQuery's syntax was developed to mimic CSS selector syntax, making code easier to develop, read, and manage.
- jQuery solves many cross-browser compatibility issues for us.


### ![Imgur](http://i.imgur.com/2BtC2Zx.gif)
1. Is jQuery a considered a library or a framework? Why?
2. What are 3 benefits of using jQuery?
3. What are 3 other examples of Javascript libraries and frameworks?

--
# <a name="add-jquery">ADD JQUERY TO YOUR APP</a>

jQuery is a client side library, which means we need to include it in our HTML. To do this, we have two options:

* Reference Directly from a server using a CDN
* Download the jQuery file itself

### <a name="cdn">CDN</a>

<details>
  <summary>**YOU DO (60 seconds)** -- What is a CDN?</summary>
    <br>
      **CDN** stands for Content Delivery Network
    <br><br>
      A content delivery network (CDN) is a system of distributed servers (network) that deliver webpages and other Web content to a user based on the geographic locations of the user, the origin of the webpage and a content delivery server.
    <br><br>
      
<br><br>

</details>


**Question**: Can we access a CDN on an airplane or some place without internet access?
      
We can grab the jQuery library directly from [jQuery's website](http://code.jquery.com/) or from a CDN (content delivery network) like [CDNJS](https://cdnjs.com/) or [Google Hosted Libraries](https://developers.google.com/speed/libraries/).


We would then add the link inside the `head` section of our `html` like so:	
	
```html
<html>
	<head>
		<script src="http://code.jquery.com/jquery-1.11.1.min.js"></script>
	</head>
	<body>
	</body>
</html>
```
<br>
![wedo](http://i.imgur.com/6Kce0ca.png) 

**WE DO (60 seconds)** -- Paste the URL directly in the broswer. What happens?

### <a name="download-directly">DOWNLOAD JQUERY DIRECTLY</a>

Download a copy of jQuery to host on your own server:

[CDNJS](http://www.cdnjs.com), [Google Hosted Libraries](https://developers.google.com/speed/libraries/), and the [jQuery site](http://www.jquery.com) will all allow you to download a copy of jQuery to include in your projects.

**WE DO (60 seconds)** 

Let's visit the [jQuery](http://www.jquery.com) site and download the file.

### <a name="min">MINIFICATION</a>
What's with the 'min.js' in the name of the jQuery file?

<details>
  <summary>**YOU DO (60 seconds)** -- What is minification?</summary>
    <br>
    
**Minification is the process of making a JavaScript file smaller by, among other things, removing all line breaks and whitespace, reducing the length of variable and function names, and stripping out all comments.** Minification can significantly reduce the size of a JavaScript file, and in turn, significantly decrease the time it takes our browsers to load the file into memory.
    
If you look carefully at the filenames of the jQuery versions you download, or just look at the URL in the "src" attribute for each script tag above, you'll notice something at the end of each file name — namely, that they end in 'min.js'. This means the JavaScript code has been minified.

In jQuery's 1.11.1's case, the original unminified code is about 276 kilobytes, whereas the minified code is only 94 kilobytes. That makes the minified version **one-third** the size of the original - not bad!

Minified scripts can be difficult to read, so most servers that host jQuery and other libraries will also offer the original (non-minified) version of the code so developers can understand the code.

Minification is performed on a JavaScript when it's ready for release and there are many options for doing this. If you'd like to minify your own scripts, try a Google search to check out the various options. Or, you can try the [Closure Compiler from Google](https://developers.google.com/closure/compiler/) which runs locally on your computer like any other piece of software you might use as a developer.

Also, if you do happen to come across a library where you can't find a non-minified version to look at, software also exists to decompress a minified script. These are usually called unminifiers, pretty-printers, or beautifier). They take a minified JavaScript and attempt to decompress it, making it easier to read and understand.

**Even if you don't fully understand the code, it's a good exercise to visit code.jquery.com and take a look at minified and non-minified jQuery.**
   
</details>

### <a name="versions">JQUERY VERSIONS</a>

If you've visited code.jquery.com, you'll see that there are three major versions in development.
 
The **1.x** branch is the most cross-browser-compatible version of the jQuery core.

The **2.x and 3.x** branches, while offering some new features, are not compatible with older web browsers — most notably, they're not compatible with Internet Explorer versions 8 and below.

### ![Imgur](http://i.imgur.com/2BtC2Zx.gif)
1. What are two ways to add jQuery to our app?
2. What is minification?
3. What is the major difference between jQuery 1.x and 2.x or 3.x?
4. Go back and read though the minification section tonight.

--
# <a name="dom-manipulation-with-jquery">DOM MANIPULATION WITH JQUERY</a>

Let's look at some features of jQuery. We'll use it to:

  - `select` a DIV and change it's content
  - `append` a new DIV with some content to a web page
  - `handle` forms where users want to dynamically add elements to the page
  - `listen` for events on a collection of DIVs or other HTML elements (For example, a blog site might have a "like" button for each comment on a post)

  
### <a name="syntax">DIFFERENCES IN JQUERY SYNTAX</a>

Four things to keep in mind:

1. jQuery always starts with a `$` this might seem weird, but it's really just a variable. jQuery is essentially a giant object with a ton of methods and at the beginning it says:

	```javascript
	var $ = jQuery = {
	// all of jquery!
	}
	```

2. Every response in jQuery is returned inside of jQuery object that looks like this 

	```js
	$('h1'); // query for all <h1> tags
			  // [ <h1>first h1</h1>, <h1>second h1</h1> ]
	```

	In order to call jQuery methods on a node. It must be wraped in a jquery object `[ ]` 

3. jQuery objects look like arrays! Sorry all, they're close to arrays, they're almost arrays, they're array-like. But in jQuery land they're not arrays... they're jQuery objects.

4. Final thing to keep in mind is that when we create variables that hold jQuery objects we always preface the evariable with a `$` 

	```js
	var $everyH1 = $('h1'); // query for all <h1> tags
	
	$everyH1					// [ <h1>first h1</h1>, <h1>second h1</h1> ]
	```

This is just a good practice to help distinguish our jQuery code from our regular Javscript. 

Why is this good practice? Because _remember_ every node created or queried using jQuery, is returned in a jQuery object, which looks like an array but is not an array.



### <a name="select-an-element">SELECT AN ELEMENT</a>

To select an element in the DOM, we use the global jQuery function:

```javascript
// This is the basic syntax for jQuery selections
$(' ')

// To select a particular element by tag, you do
$('h2') // selects all h2 elements

// To select by ID, you use the same syntax as CSS selectors
$('#someID') // Would select the element with ID="someID"

// To select all elements of a particular class, use CSS syntax again
$('.someClass') // Selects all elements of the class "someClass"

// And you can use more complicated CSS selectors as well
$('p.anotherClass') // Selects all <p> tags that also have the class "anotherClass" (<p class="anotherClass")
```

If you use variable assignment when doing a selection, a "jQuery" object is returned

```javascript

// We prepend '$' to variable names when a variable is going to be a jQuery object to help us remember what that variable is for.
var $jqObject = $('p'); // Returns a jQuery object containing all <p> tags on your web page.

// However, we don't have to prepend '$' to our variables. It's just so we can remember what a variable is being used for.
var jqObject = $('p'); // This is functionally identical to the version above that includes the '$' in front of jqObject.
```



![Imgur](http://i.imgur.com/ylb6WX9.gif)

**Open the `student_starter` code and select the `title` element.**



### <a name="change-element-content">SELECT A DOM ELEMENT AND CHANGE IT'S CONTENT</a>

In this HTML:


```html
<div id="myDiv">Hello world!</div>
```

```javascript
var divToManipulate = document.getElementById('myDiv');
divToManipulate.innerHTML = "Goodbye world!";
```

Now the code above isn't too hard to deal with, but even so, in jQuery, this is a one-liner.

```javascript
$('#myDiv').html("Goodbye world!");
```

See it in action [here](http://jsbin.com/hopoxo/edit?html,js,output)

If we wanted to **save our selection as a jQuery object**, the code would look like this instead:

- First we select the element we want and save it as a jQuery object

```javascript
var $myDiv = $('#myDiv');
```

- Then we use our jQuery object to perform our task

```javascript
$myDiv.text("Goodbye world!");
```

There are three things about the example above that make jQuery easier to use:
 
1. jQuery is using the same syntax as CSS to select elements
2. jQuery allows us to chain methods together to accomplish our goals (i.e., $().html(...) ), making code shorter and easier to understand
3. jQuery deals with any cross-browser compatibility issues, which may not seem like a big deal in this example, but which quickly become difficult to deal with as things get more complex


![Imgur](http://i.imgur.com/ylb6WX9.gif)

**Open the `student_starter` code and change the content of the `title` element.**


--
# <a name="append-an-element">APPEND A DOM ELEMENT</a>

If we had the following HTML page...

```html
<html>
<body>
  <div id="container">
    <h1>Hello World!</h1>
  </div>
</body>
</html>
```

If we want to add a new DIV that provides a nice greeting, our vanilla JavaScript would have to be:

```javascript
  var myDiv = document.getElementById('container');
  var newP = document.createElement('p');
  newP.innerHTML = "Hello complicated, multi-step world of adding an element to the DOM!";
  myDiv.appendChild(newP);
```

And in jQuery, it looks like this:

```javascript
  $('#container').append("<p>Hello simple insertion using jQuery chaining</p>");
```

In the jQuery code example above, we first select the DIV with `id="container"`, then we append a new paragraph element (automatically created using core jQuery selector function), and then we append the text we want to insert to the new paragraph element we just created. In effect, the new HTML looks like this after the jQuery is run:

```html
<div id="container">
  <p>
    Hello simple insertion using jQuery chaining
  </p>
</div>
```

You can [see this in action on JSBin](http://jsbin.com/vixuqe/3/edit?html,js,output)

![Imgur](http://i.imgur.com/ylb6WX9.gif)

**Complete the next two prompts in the `student_starter` code.**

--
# <a name= "modify-styles">MODIFY STYLES (CSS)</a>

You can do more than select elements and modify content. You can also create or update CSS style attributes in jQuery using the .css() method

```js
$("#myDiv").css("color", "red");
```

The code above will change the color of all text inside the DIV with `id="myDiv"` to red.

[Check this out here](http://jsbin.com/cupumu/1/edit?html,js,output)

Or, if we have a bunch of elements that all have the same class (in this example, it's class="myClass"), we can use the class selector to modify the color of all of them at once:

```js
$(".myClass").css("color", "blue");
```

[You'll find this example here](http://jsbin.com/yutoyi/1/edit?html,js,output)

But that seems kind of boring. I mean, what if we want to do something with less hard-coding using jQuery.

[Here's a repeat of the last example](http://jsbin.com/wevoti/1/edit?html,js,output) that sets the text in all elements of class="myClass" to a random color. Try to understand how it works before moving on:

```js
var randColorValue = function() {
  return Math.floor( Math.random() * 255 );
}

var randColor = function() {
  var red = randColorValue();
  var green = randColorValue();
  var blue = randColorValue();

  return "rgb(" + red + "," + green + "," + blue + ")";

}

$(".myClass").css("color", randColor() );
```

![Imgur](http://i.imgur.com/ylb6WX9.gif)

**Complete the prompts dealing with color in the `student_starter` code.**

--

# <a name="add-and-remove">ADD AND REMOVE ELEMENTS</a>


Sometimes in a dynamic web application, user-input is meant to trigger the addition or removal of content or functionality. Using jQuery, we can easily create new DOM elements and insert them into the DOM, or remove existing elements (and any content they contain) from the DOM.

So, let's imagine we have a web page with the following content on it:

```html
<body>
  <div id="outerContainer">
    <div class="innerItem innerItemHeader">Enjoy some hipster ipsum:</div>
    <div class="innerItem">
      Aesthetic migas paleo McSweeney's, pork belly Kickstarter Echo Park sriracha keytar disrupt viral drinking vinegar fanny pack typewriter.
    </div>
  </div>
</body>
```

Let's say we want to add some more hipster ipsum to the page. Something like:

```html
<div class="innerItem">
	Farm-to-table Godard roof party bespoke, fashion axe mustache vinyl.
</div>
```

To add this DIV, and our hipster ipsum content using jQuery, we'd do the following:

Define a new DIV and assign the jQuery object to `$newDiv`

```js
$newDiv = $('<div>');

// Add hipster ipsum content
$newDiv.html("Farm-to-table Godard roof party bespoke, fashion axe mustache vinyl.");

// Set it's class to innerItem
$newDiv.addClass("innerItem");

// Append our new element  
$('#outerContainer').append($newDiv);
```


See this in action (and play around with it) [on JSBin](http://jsbin.com/gupade/3/edit?html,js,output)


![Imgur](http://i.imgur.com/ylb6WX9.gif)

**Complete the last prompt in the `student_starter` code.**


--
# <a name="forms">FORMS</a>

I'm going to briefly talk about forms, default functionality, and how to use jquery to use the text a user input. 

So, say we have the following form:

```html
<form>
  <input type="text">
  <button> add </button>
</form>
```

1. Add a jQuery click event to the button that sends an alert that a button was clicked.
2. query for the input field and save it to a variable. 
3. use .val() on the input node to extract the text and use `alert` to display the input text to the user. 


--
# <a name="exercises">EXERCISES</a>
* Finish the [student-starter] code tasks.
* [Jedi Academy](https://github.com/ATL-WDI-Exercises/jedi-javascript-jquery)

--
# <a name="bonus">![Imgur](http://i.imgur.com/K0d7Tq8.jpg)</a>

Following the directions below to practice using jQuery:

- Go to http://www.reddit.com

- Reddit uses jQuery, so we can use our Chrome developer console to manipulate the site in real time using jQuery.

- To do this, once Reddit.com has loaded, go to your view menu in Chrome. Select View > Developer > JavaScript Console

- Once that's loaded, try entering the following command into the Chrome REPL:

```javascript
$('img').hide()
```

- Hit enter. All the images should have dissappeared from the Reddit.com home page. Make sure you understand why before moving on.

- Now try this:
```js
$('img').show()
```

- That should have brought all the images back. Make sense so far?

- Now with the chrome inspector, try to match the title of the first reddit post and replace the text using `.text()` or `.html()`.

- Try to replace the blue background in the header by another color using the function `.css()`.

- Now try some of the other examples we've gone over in the Chrome REPL and see what happens to the Reddit.com website. Remember, this is your laboratory — your chance to experiment and learn. Make use of it.

--
# <a name="conclusion">![Imgur](http://i.imgur.com/wPefQjh.png)</a>

- jQuery makes JavaScript super friendly and easy to write. a lot of websites are using jquery, soon you will too.  Remember that it's always good to know how to use what is called vanilla JavaScript, or JavaScript without a library.

- Please spend some time reviewing [the documentation](https://api.jquery.com/).