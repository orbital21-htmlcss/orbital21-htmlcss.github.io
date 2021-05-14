## Orbital 2021 
### HTML/CSS/JS Workshop
Brought to you by NUS Hackers



### Disclaimer
- This workshop covers the basics, not meant to master HTML/CSS/JS in 2 hours that's just not possible
- Feel free to ask questions in chat



### Resources
Slides can be found here 

[bit.ly/orbital21-hsj](bit.ly/orbital21-hsj)

Code examples can be found here 

[bit.ly/orbital21-hsj-code](https://github.com/raniceyue/orbital21-htmlcss/tree/master/code)



### Outline
1. HTML
    - Basic HTML elements
    - Forms
2. CSS
    - CSS selectors + specificity
    - Flexbox
    - Media queries
3. JavaScript
    - Manipulating the DOM
    - Event listeners



### What you need
1. Your browser

<br/>
<img src="img/firefox.svg" width=150px>
<img src="img/chrome.svg" width=150px>
<br/>

2. Your favourite text editor
    - Vim/Emacs 
    - Sublime text
    - VS Code



### INTRODUCTION
- HTML/CSS are not programming languages
- JS is a programming language
- The browser is your REPL



### How do they all work together?
![](img/html-css-js.png)



### HTML
#### Hyper Text Markup Language



### HTML files
- End with `.html`
- Contents can be viewed in the browser



### HTML Snippet
```html [1 - 9]
<!DOCTYPE html>         
<html lang="en">        
	<head>              
		<title> Hello </title>   
	</head>
	<body>              
		Hello world.
	</body>
</html>
```
- Every web page consists of nested **HTML elements**
- Each element (HTML tag) describes something on the page e.g, headings, lists, links, etc. 


### Doctype declaration
```html [1]
<!DOCTYPE html>         
<html lang="en">        
	<head>              
		<title> Hello </title>   
	</head>
	<body>           
		Hello world.
	</body>
</html>
```
The **`DOCTYPE`** declaration tells the browser what ver. of HTML to use


### HTML tag
```html [2 - 9]
<!DOCTYPE html>         
<html lang="en">        
	<head>              
		<title> Hello </title>   
	</head>
	<body>           
		Hello world.
	</body>
</html>
```
The **`HTML`** tag marks beginning of HTML content, in between the start and closing tags contains all elements in the page


### head tag
```html [3 - 5]
<!DOCTYPE html>         
<html lang="en">        
	<head>              
		<title> Hello </title>   
	</head>
	<body>           
		Hello world.
	</body>
</html>
```
The **`head`** of a webpage contains information browsers need to know about


### body tag
```html [6 - 8]
<!DOCTYPE html>         
<html lang="en">        
	<head>              
		<title> Hello </title>   
	</head>
	<body>           
		Hello world.
	</body>
</html>
```
The **`body`** = the visible part of a web page



### The DOM
- DOM = document object model
- Each web page is like a tree structure that describes how the HTML elements are related to each other

![](img/dom.png)



### Common HTML Elements
- Headings
- Divs
- Lists
- Images
- Links
- Buttons
- Forms
- so much more!!!

[Mozilla HTML Elements Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)


### Comments in HTML
```html
<!-- You can add comments to html like this -->
```
Starts with `<!--` and ends with `-->`


### `<div>`
```html
<div class="container">
    Some text here
</div>
```
- Usually comes with `class` or `id` specified (more about this later)
- Used for **containers**
- No impact on webpage layout unless it is **styled with CSS** (more about this later)


### Elements for styling text
```html
<b>bold</b>
<i>italics</i>
<u>underline</u>
<br/> <!-- Adding whitespace to a page -->
```
- Note: `<br>` is self closing, can use as either `<br>` or `<br/>`


### Headings
Used for titles
```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
```


### Lists - Ordered
`<li>` (list items) nested inside `<ol>`
```html
<ol>
    <li> item 1 </li>
    <li> item 2 </li>
</ol>
```


### Lists - Unordered
`<li>` (list items) nested inside `<ul>`
```html
<ul>
    <li> item 1 </li>
    <li> item 2 </li>
</ul>
```


### Images
```html
<img src="{LINK_TO_IMAGE}"/>
```
- Note: Images are self-closing! There is no `</img>` closing tag, use `/>` at the end
- `src` defines a link to the image, could be a URL or PATH


### Links
```html
<a href="https://nushackers.org">Click me!</a>
```
- `href` defines link to go to, could be a URL or PATH
- Name of the link e.g., "Click me!" defined within the starting and closing tags


### Buttons
```html
<button onclick=clickme()>Click me!</button>
```
- `onclick` is an **event listener** (will be discussed in later slides)
- Buttons are usually associated with forms
- Automatically styled by browser to look like a button (you can change this with CSS)



### Forms
- Forms are a little more complex
```html
test
```


### CSS
#### Cascading Style Sheets



### CSS
```css [1 - 4]
h1 {
    color: #999;
    font-size: 12px;    
}
```
- Every element has CSS style attributes



### CSS Box Model
![](img/box_model.png)

Each element on the page is represented by a rectangular box with 4 main areas.
1. Content 
2. Padding
3. Margin
4. Position


### CSS Attributes
Examples of attributes
- `font-family: 'Roboto', serif;` 
- `font-size: 30px;`
- `color: #999999;`
- `padding: 10px;`
- `margin: 10px;`

[Mozilla CSS Attributes Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)



### Integration with HTML
1. Inline 
2. Within `<style>` tags in the `<head>`
3. In a separate file referenced using `<link>` tags in the `<head>`


### Inline CSS
Specified directly in the element tag using `style` attribute
```html
<h1 style="font-size: 30px">Hello</h1>
```


### Within `<style>` tags
Styles within a `<style>` tag within the `<head>` tag
```html
<head>
    <style>
        h1 {
            font-size: 30px;
        }
    </style>
</head>
```


### Within separate file
`style.css`
```css
h1 {
    font-size: 30px;
}
```
`index.html`
```html
<head>
    <link rel="stylesheet" href="style.css"/>
</head>
```
- `rel` describes what this link is for
- `href` links to the stylesheet, could be a URL or PATH



### HTML Classes and IDs
```html
<div class="container"> ... </div>
<div id="about"> ... </div>
```
- HTML elements can be assigned **classes** and **id**s 
- This is useful for identifying and styling certain elements


### CSS Selectors
```css
h1.container {
	color: #e4e4e4;
}

h1#about {
	color: #55555;
}
```
Allows us to select HTML elements based on relationships and identification
- `h1.title` selects all elements `<h1>` with `class="title"`
- `h1#special-title` selects all elements `<h1>` with `id="special-title"`


### Specificity
There are 3 main types of selectors
1. Type selectors (For selecting elements)
2. Class selectors
3. ID selectors

1 is the least specific, 3 is the most specific.

[Mozilla CSS Specificity Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)


### Selecting based on type
```css
h1 {
	color: blue;
}
```
- Applies to all `<h1>` elements on the page


### Selecting based on class
```css
.container {
    color: red;
    font-size: 25px;
}

h1.container-title {
    color: green;
    font-size: 30px;
}
```
- `.container` applies to all elements with `class="container"`
- `h1.container-title` applies to all `<h1>` elements with `class="container-title"`


### Selecting based on ID
```css
#about {
    color: red;
    font-size: 25px;
}

h1#about-title {
    color: green;
    font-size: 30px;
}
```
- `.about` applies to all elements with `id="about"`
- `h1#about` applies to all `<h1>` elements with `id="about"`


### Combinators
Based on the document object model (DOM), we can combine selectors to select elements based on relationships
```css
div h1 {
    color: pink;
    font-size: 30px
}

div > h1 {
    color: blue;
    font-size: 30px
}
```
- `div h1` selects all `<h1>` inside `<div>` elements
- `div > h1` selects all `<h1>` whose parent = `<div>` element


### A lot more selectors

- [Mozilla CSS Selector Reference](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Combinators)
- [W3Schools CSS selector cheatsheet](https://www.w3schools.com/cssref/css_selectors.asp)



### Responsive design
Everyone views web pages from their phones now, we need to be able to style for different viewports, like phones and tablets

![](img/responsive.gif)



### Flexbox
- Flexbox = flexible box
- A way to construct responsive layouts in CSS
- Alternative to CSS grid
  - (Self-study) [Grid v Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Relationship_of_Grid_Layout)


### How to use flexbox in CSS?
To create a **flex container**, just add the `display: flex` attribute to the container
```
.container {
	display: flex;
}
```
The container is now a **flex container** and all elements within it are **flex items**


### Configuring flex containers
For flex containers, we can adjust the alignment and order of the items inside + much more, using different attributes


### Flex container attributes

|Attribute|Description|
|---------|-----------|
|`flex-direction` | Specifies direction of the flex items |
|`flex-wrap`| Specifies wrapping behaviour of flex items |
| `flex-grow` | Specifies |
| `justify-content` | Specifies horizontal alignment of flex items |
|`align-items`| Specifies vertical alignment of flex items | 

There are also attributes that you can provide for flex items.

[Reference: A complete guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)



### Media queries
```css [1 - 6]
@media (width: 360px) {
    div {
        color: white;
        background: black;
    }
}
```
Another way you can make your web page more responsive, is through media **queries on the width of the viewport.**

[Mozilla Media Query Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)



### Mastering HTML/CSS
- Might seem easy but actually tedious 
- CSS is very powerful and has a lot more features than covered today (RTFM!)
- Practice makes perfect, just dive right into it and Google like mad... also RTFM



### External Libraries
You don't have to style everything from scratch!! Learn how to use external libraries after you have gotten the hang of CSS.
- [Bootstrap](https://getbootstrap.com/)
- [Tailwind CSS](https://tailwindcss.com/)

<br/>
<img src="img/bootstrap-4.svg" width=200px/>
<img src="img/tailwind.svg" width=300px/>



### CSS Pre-processors
Allows you to generate CSS from the preprocessor's own syntax
- [Sass](https://sass-lang.com/)
- [Less](https://lesscss.org/)

<br/>
<img src="img/sass.svg" width=200px/>
<img src="img/less.svg" width=300px/>


### Example: Sass
Sass allows for nesting within CSS, variables + more features
```scss
.alert, .warning {
  ul, p {
    margin-right: 0;
    margin-left: 0;
    padding-bottom: 0;
  }
}

```
[Reference: Sass documentation](https://sass-lang.com/documentation)



### JavaScript
- Source is a subset of JavaScript!
- HTML describes what a page looks like, **JS allows us to add logic and behaviours to a webpage**
- It can manipulate the DOM!



### Integration with HTML
Done in 2 ways 
1. Using `<script>` tags within `<head>` 
2. In a separate file using `<link>` in `<head>`



### Example 1
Simple counter button
```html [3 - 9]
    <head>
		<title>Counter</title>
		<script>
				let counter = 0;
				function count() {
					counter++;
					alert(counter);
				}
		</script>
	</head>
	<body>
		<h1>Hello!</h1>
		<button onclick="count()">Count</button>
	</body>
```



### Example 2
Manipulating the DOM
```html [3 - 7]
<head>
    <title>Foobar</title>
    <script>
        function foobar() {
            document.querySelector('h1').innerHTML = 'Bar!'
        }
    </script>
</head>
<body>
    <h1>Foo!</h1>
    <button onclick="foobar()">Click me</button>
</body>
```



### Manipulating the DOM
```html [3]
<script>
    function foobar() {
        document.querySelector('h1').innerHTML = 'Bar!'
    }
</script>
```
- `document` serves as an entrypoint to the web page's DOM, has many other functions to manipulate or query the DOM
- `document.querySelector` allows us to extract elements out of the page so we can manipulate them


### Other `document` methods

- `document.getElementById`
  - Returns element with given `id` attribute
- `document.getElementsByClassName()`
  - Returns a list of elements with given class name 

[Mozilla `Document` Reference](https://developer.mozilla.org/en-US/docs/Web/API/Document)


### Logging for debugging
```js
function button() {
	console.log('I have been pressed');
}
```



### CODE DEMO
We can actually create a static website with all the info we have learned thus far. 



### Event Handlers
- Every user interaction with the page = EVENT!
- E.g, mouse events
  - `onclick`
  - `onmousemove`
  - `onmouseenter`
  - `onwheel`
- Many other events, refer to [Mozilla Event Reference](https://developer.mozilla.org/en-US/docs/Web/Events)



### So what now?
- Learn how to create static sites using a **static site generator**
- Learn frameworks e.g., React, Angular, Vue
- The best way to master what you've learnt is to **build your own project**



### Conclusion
- Front-end development is more than meets the eye
- Hands on practice to get more experience, a lot of self learning things you can't learn in NUS
- Modules that touch on web development
  - CS3249 User Interface Design
  - CS3240 Interaction Design
  - CS3226 Web Programming and Applications (Not sure if it's still around)
- Come for NUS Hackers' hackerschool



### Thanks for attending
Join the NUS Hackers' telegram chat if you have any questions

[t.me/nushackers_chat](https://t.me/nushackers_chat)

Follow us on instagram for updates on our events!! 

[instagram.com/nushackers](https://instagram.com/nushackers)