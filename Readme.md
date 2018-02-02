# Learn HTML and CSS
These lessons will give you the basics needed to create and host your own website. This is not meant to be a deep dive or cover all available topics and scenarios. Instead the information is broken up into four lessons each designed to be about an hour of work. It should give you the foundation of knowledge that allows you to get started as well as be able to confidently search for and understand more advanced tutorials and documentation. After each lesson, there is an example website that shows an example for how to implement the elements and style topics covered.

## Prerequisites
- Web browser (I prefer Chrome)
- [Sublime Text](https://www.sublimetext.com/) A text editor for code

# HTML Lesson 1
## Basic Document

Open index.html 
1. `Doctype` gives the browser the version of html you are using (html is html5)
2. `html` this is the full document
3. `head` this is metadata for the document: information for the browser
4. `body` this is the content of the document: what the user will see 

### HTML Basics

HTML stands for  "hyper text markup language". It marks up text using tags to describe the structure and style your browser should display.

**tags** - surrounded by angled brackets `<tag>`, Usually come in pairs `<tag></tag>`, the closing tag starts with a  forward slash / 
- tags can contain content 
- tags can be nested

**attributes** - are part of the tag `<tag attribute=‘value’></tag>` they give more information about the element. They are always a part of the start tag, never the end. They can either be key=‘value’ or key

### Elements
1. **Title**  `<title>` This is what will appear in the text for the tab. It belongs in the header
2. **Headings** `<h1> <h2> <h3> <h4> <h5> <h6>` These will be rendered large and bold. They are your section headings
3. **Paragraphs** `<p>` These are blocks of text. This is the meat of the content.
4. **Links** `<a>` This are links to other parts of the current page or other pages,
	1. The `href` attribute is the destination location. You can give it a full web address, a name of a document in the same folder, or the id of an element on the current page (we’ll get to ids later).
5. **Images** `<img>` These will render the image on the page.
	1. The `src` attribute is the location of the image. You can either give it a full web address or a path.
	2. The `title` attribute give the image text if you hover over it.
6. **Breaks** `<br/>` The break element inserts a line break on the page. This is a self closing tag, so you only need one.

### Layout and Style
These are basic content elements so far, but your browser can do so much more. You can add style, size, and color to your elements with CSS. You can also organize your document and tell it how to layout your elements. 

**Block vs Inline** Block elements insert a line break at the end. Inline elements do not. 
 `<div>` - empty block element
`<span>` - empty inline element
You can nest these elements to ensure your page looks the way you want

**Style** You can add the style element to pretty much any tag in the `body` to control how it looks. There are many key value pairs that you can give for the value of style. `style=“color:green”` You can add many values to style by separating them with `;`
* color - green, slateblue, #00aaff,  
* font-family - Georgia, serif, courier 
* font-size - 30%, 10px,
* border - 1px solid black

**Comments** If you want to give a message to a human reading the code and not to the browser or the person visiting your website you can use a comment. `<!— comment —>` Anything between the angled brackets will be ignored by the browser

### Complex Elements

1. **Tables** `<table>` Tables display items ordered by columns and rows.
	1. To start a new row in the table use `<tr>` and close at the end of the row.
	2. Rows will include cells. Either `<th>` for table headers (with content inside that tag) or `<td>` for table data (with content inside these tags) .
	3. *hint* Make sure that each row contains the same number of cells.
2.  **Lists** There are two types of lists: Ordered lists `<ol>` where elements are numbered and unordered lists `<ul>` where elements are just marked 
	1. Each element of the list is represented by `<li>` standing for list item. These are nested in the `<ol>` or `<ul>` tags. 


*campfire.jpg by Visit Lakeland*

# CSS Lesson 2
## CSS Introduction
### Defining Style
**CSS** stands for Cascading Style Sheets. It gives the browser information on how to display HTML elements on the screen.

There are three places you can define style
* external style sheet - save your style as a file and link it to your document
	* `<link rel="stylesheet" type="text/css" href="mystyle.css">`
	* This way is the most reusable, as you can upload your file to many pages in the same site
* internal style sheet - insert style directly in the `head` element
	* `<style></style>`
* inline style - insert style on the individual element
	* `<element style=“…”>`

### Format
The format for external and internal stylesheets are the same (we have already seen inline style in the HTML lesson): 
```
selector {
	key: value;
	key2: value;
}

selector2 {
	key: value
}
```

### Selectors (basics)
1. **Element** selectors select all elements with that tag ex `p` would match `<p>`
2. **Id** selectors select the specific element where the id attribute of the element matches. To indicate it is an id match, it starts with a `#` ex. `#main-header` would match `<h1 id=‘main header’>`
3. **Class** selectors select all the elements where the class attribute of the element matches. To indicate it is a class match it starts with a `.` ex. `.pretty` would match `<h1 class=“pretty”>` and `<ul class=“pretty”>`

#### Id’s and Classes (aside)
`id` and `class` are HTML attributes. Id’s on a page must be unique i.e. there cannot be two elements with id=‘main-header’. There can be many of the same classes i.e. 10 elements could have class=‘pretty’. Additionally an element can have many classes, to have more than one class, separate them with a space. e.x. class=‘pretty strong heading-content’

#### Combining selectors
You can combine element and class or element and id selectors by squishing the id/class selector to the element selector. Ex `h1#main-header` or `p.pretty`
You can also group many selectors together if they will all have the same rules. You separate these with a space. ex. `h1, h2, h3`

## Rules
This is just a selection of rules and values that are very common. There are many more that you can look up. 
### Color
 **Properties**
* `color` - font color
* `background-color` - color of background

**Color Formats**
* name - red, green, blue [Web colors - Wikipedia](https://en.wikipedia.org/wiki/Web_colors#/media/File:SVG_Recognized_color_keyword_names.svg)
* hex - #4f4f4f (#rrggbb)
* rgb - rgb(255,99, 71)

### Backgrounds
 **Properties**
* `background-color` - color of background
	* *values* - color formats
* `background-image` - image for background
	* *values* - url, none, linear-gradient()
* `background—repeat` - how image will be repeated
	* *values* - repeat, repeat-x, repeat-y, no-repeat, space

### Borders
 **Properties**
* `border-width` - size of border
	* *values* - size in px, pt, cm, em or thin, medium, thick
* `border-style` - line style
	* *values* - solid, dotted, dashed, double, none
* `border-color` - color or border
	* *values* - color value as above
* `border` - short hand for all of the above
* `border-radius` - rounds the corners of border 
	* *values* - length of circle radius for rounded corners

### Box Model 
![Box Model](boxmodel.gif)
```
Content - The text/image in the element
Padding - Transparent area around content
Border - Visible border around padding
Margin - Transparent spacing between border and other elements
```
 **Properties**
* `padding` - Transparent area around content
	* *values* - size values, % of containing element, inherit (same as parent)
	* can suffix padding with top, right, bottom, left. ex. `padding-top`
* `margin` - Transparent spacing between border and other elements
	* *values* - size values, % of containing element, inherit (same as parent)
	* can suffix padding with top, right, bottom, left. ex. `margin-top`

### Size
 **Properties**
* `height` - vertical size of element
	* *values* - auto, length (px, cm), % of containing block, inherit
	* `max-height` and `min-height` are also available 
* `width` - horizontal size of element
	* *values* - auto, length (px, cm), % of containing block, inherit
	* `max-width` and `min-width` are also available 

### Text
 **Properties**
* `color` - font color
	* *values* - color value as above
* `text-align` - alignment of paragraph text
	* *values* - right, left, center, justify
* `text-decoration` - adds some decoration to text
	* *values* - underline, overlain, line through, inherit
* `line-height` - spacing between lines in text
	* *values* - size values, % of text height
	
### Fonts
 **Properties**
* `font-family` - font and class of font for text
	* *values* generic classes - serif, sans-serif, monospace, font-names - Arial, Courier, Times New Roman
	* You can put several in a line, the first that the computer is able to show will be displayed ex. `font-family: "Times New Roman", Georgia, serif`
* `font-size` - size of text
	* *values* - px, em, %
* `font-style` - mostly for italics
	* *values* - normal, italic, oblique
* `font-weight` - mostly for bold
	* *values* - normal, bold

# CSS Lesson 3
## CSS Advanced and CSS frameworks

### Display
**Properties**
* `display` - how element should be displayed
	* *values* - inline, block, none,  inherit
	* `display:none` removes element from layout
* `visibility` - whether an element should be visible
	*  *values* - visible, hidden, inherit
	* `visibility:hidden` does not show an element, but it still takes up space

### Centering
One way to center content is to use widths and margins.
* Give your element a set width either in px or %. Then set `margin: auto`
* You can do this with % widths/margins too
	* `width: 60%; margin-right: 20%; margin-left:20%`

### Tables
 **Properties**
 * `border-collapse` - sets whether borders for individual cells should be collapsed into a single border 
 	* *values* - collapse, separate
 * `border` - same as for other elements
 * `text-align` - same as for other elements
 * `vertical-align` - vertically aligns text in cells
 	* *values* - top, bottom, center

### Lists
**Properties**
* `list-style-type` - select shape of marker from browser defaults
	* *values* - disc, circle, decimal, georgian, lower-roman, upper-roman, none ...
* `list-style-image` - uses an image for list marker 
	* *values* - url('<url to image>')
* `list-style-position` - put list markers insider or outside flow of content
	* *values* - inside, outside

### Position
**Properties**
* `position` - determines positioning method for element, set `top, left, bottom, right` properties to position element
	* `static` - default, in the flow of content
	* `relative` - relative to default location 
	* `fixed` - relative to viewport, always stays in the same place even during scrolling
	* `absolute` - relative to nearist positioned ancestor 
	* `sticky` - relative until it reaches specified offset position in viewport, then fixed

### Float
**Properties**
* `float` - element floats to left or right of container
	* *values* - left, right, none, inherit

## Frameworks

Most developers don't start from scratch when laying out their website. Many will choose to use one of the many available frameworks. The currently most popular of these is [Bootstrap](https://getbootstrap.com/) 

### Bootstrap
Bootstrap is a set of files (css and javascript) that you include on your page and it gives you a basic style and several useful elements you can build your page with. It uses a grid based layout system so you don't have to worry about setting up the margins, widths and floats to position your elements in a pleasing fashion. 

Once you start to use bootstrap, you'll start to recognize sites that use the default bootstrap style. There is an easy fix for your own site. There are hundreds of free (and paid) templates out there that allow you to use bootstrap elements and layout but look like a cutting edge modern website. Just google `bootstrap templates free` (you can add the current year to get the absolute latest)

You can also layer your own css on top of bootstrap style. Use bootstrap as a foundation for your site, but then build on top of it. Add your own classes and ids to override bootstrap's default styling. Adding `!important` at the end of any css rule (but before the semicolon) makes that the rule that gets priority  if you have trouble overriding selectors.  

## More Help

The best resource I have found for learning CSS is [W3 Schools](https://www.w3schools.com/css/default.asp) They have an extensive tutorial for CSS and for Bootstrap and allow you to try things out in the browser.


# Web Hosting Lesson 4
There are many ways to get your website from your computer out into the internet to be accessed by the world. We will only cover a few of them today (and you only need to pick one anyways). 

## Simple Option — Surge
[Surge](http://surge.sh) is a command line tool that allows you to publish from the directory with your site.  It is free for basic hosting. They will give you a domain name or you can use your own. We will learn how to buy domains later.

1. Install Node and NPM
NPM is a package manager. It allows you to install certain programs that have been uploaded to their site (like Surge).
[Node.js](https://nodejs.org/en/) 
2. Open the command line (terminal in OSX, powershell in Windows)
3. Navigate to the directory with your site use `cd <directory name>`
4. Run `surge` and follow prompts if it is your first time deploying
5. You can reach your site from the url that the program prints out

## Domains
You can buy a domain name. This means that you own that url. You will need somewhere to host the files (we will get to this in a bit). You will need to pay for this; some hosting companies will give you a free domain, but you still are paying for the hosting. It is usually far easier to buy the domain from the hosting company you will use, the transfer process can be a pain if you buy from a different company.

## Long-Term Option - Hosting
Once you get more comfortable with hosting you almost certainly will want to use a hosting company. There are several good options. The some of the popular options currently are [BlueHost](https://www.bluehost.com/), [HostGator](https://www.hostgator.com/), and [GoDaddy](https://www.godaddy.com/). I use Bluehost so I’ll cover that. It will cost money.

### Bluehost Instructions

#### Sign up
1. Select hosting plan (Basic is fine for now)
2. Search for an available domain name
3. Fill out sign up form (make sure you uncheck all the extra options).

#### Hosting Site
1. Login to account
2. Go to hosting tab
3. Click on file manager  in the files section. Choose Web Root
4. Click Upload button and select file.  (The default permissions are fine)
5. Index.html will be the site that is loaded when you go to the domain name, everything else will be a relative path. 
6. Go to your URL and check it out!



*circles-and-roundabouts by Riadh Khan*
