# Learn HTML and CSS

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


*Image by Visit Lakeland*

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
	* values - color formats
* `background-image` - image for background
	* values - url, none, linear-gradient()
* `background—repeat` - how image will be repeated
	* value - repeat, repeat-x, repeat-y, no-repeat, space

### Borders
 **Properties**
* `border-width` - size of border
	* size in px, pt, cm, em or thin, medium, thick
* `border-style` - line style
	* solid, dotted, dashed, double, none
* `border-color` - color or border
	* color value as above
* `border` - short hand for all of the above

### Box Model 
[image:3412A09F-7F70-420B-944D-BD5083683AEC-413-00000E0CCEBDA75C/boxmodel.gif]
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
	* 	*values* - auto, length (px, cm), % of containing block, inherit
	* `max-width` and `min-width` are also available 

### Text
 **Properties**
* `color` - font color
	*  color value as above
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

### Display
**Properties**
* `display` - how element should be displayed
	* *values* - inline, block, none,  inherit
	* `display:none` removes element from layout
* `visibility` - whether an element should be visible
	*  *values* - visible, hidden, inherit
	* `visibility:hidden` does not show an element, but it still takes up space

