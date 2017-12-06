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
