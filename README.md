### Setup
- Setup the dev environment
- Planning (website info, color, font, layout etc.)
- Graphics designer (put together the visuals of the website) + UX designer (how users will experience and interact with the website)
- Assets : Text, [Theme color](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Colors/Color_picker_tool), Images (google images => tools => Creative Commons licenses filter)
- Choose a Font : [Google fonts](https://developers.google.com/fonts/docs/getting_started)
- It is best to get into the habit of writing your folder and file names lowercase with no spaces and with words separated by hyphens

#### Structuring the project
```
|
|--- index.html
|--- images/ => Images used by the website
|--- styles/ => CSS files
|--- scripts/ => JS files
```

#### HTML
- The class attribute allows you to give the element a non-unique identifier that can be used to target it (and any other elements with the same class value) with style information and other things.
```
<!DOCTYPE html> : needed to make sure your document behaves correctly
<html></html> : root element
<meta charset="utf-8"> : sets the character set your document
<title></title> : sets the title of your page
<body></body> : all the content that you want to show to web users i.e. text, images, videos, games, playable audio tracks, or whatever else
```

#### CSS
|Selector name |What does it select |Example|
|---|---|---|
Element selector (sometimes called a tag or type selector) | All HTML elements of the specified type | p selects `<p>`
ID selector|The element on the page with the specified ID. On a given HTML page, each id value should be unique.|#my-id selects `<p id="my-id"> or <a id="my-id">`
Class selector|The element(s) on the page with the specified class. Multiple instances of the same class can appear on a page.|.my-class selects `<p class="my-class"> and <a class="my-class">`
Attribute selector|The element(s) on the page with the specified attribute.|img[src] selects `<img src="myimage.png"> but not <img>`
Pseudo-class selector|The specified element(s), but only when in the specified state. (For example, when a cursor hovers over a link.)|a:hover selects `<a>`, but only when the mouse pointer is hovering over the link.

- Something you'll notice about writing CSS: a lot of it is about boxes. This includes setting size, color, and position. Most HTML elements on your page can be thought of as boxes sitting on top of other boxes.
- [CSS_basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics)

#### JS
- Browser Application Programming Interfaces (APIs) built into web browsers, providing functionality such as dynamically creating HTML and setting CSS styles
- Third-party APIs that allow developers to incorporate functionality in sites from other content providers, such as Twitter or Facebook
- Third-party frameworks and libraries that you can apply to HTML to accelerate the work of building sites and applications

#### Publishing the website
1. Put website files on the webserver
2. Rent your domain name from a domain registrar (e.g. go Daddy, AWS route53)

#### How web works
`Client ---> Server`
`Client <--- Server`

- Internet connection: Tx/Rx data on web
- TCP/IP: how data should travel on the internet
- DNS: domain name to IP address mapping
- HTTP: a language for client and servers to speak to one another
- Component files: code files (html,css,js) + assets (images, music, video, pdfs)

##### Req/Resp
type google.com in browser --> check on DNS server for actual server IP --> server receives a request --> 200 ok --> start sending website's files in chunks (i.e. packets) --> browser collects all the packets to form a complete web page

##### Browser Parsing Order
Parse HTML file first --> finds <links> and <script> elements --> send request back to server to get those files --> Parse css, js --> Generate in-memory DOM tree from parsed URL --> Generate in memory CSS Object Model --> compile & execute JS --> rendering of page --> User interaction

#### Why packets instead of one chunk of whole data
- if packets are dropped/corrupted, it is easier to replace small chunks
- packets can be routed along different paths, making exchange faster and allowing multiple users to access website at the same time

#### References
- [Getting_started_with_the_web](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web)
