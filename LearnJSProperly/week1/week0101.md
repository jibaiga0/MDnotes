Learn JS properly
===

# 1. learn some html & css(done).
# 2. make a simple web site
# 3. read "beginning javascript" chapter 1
## what is javascript?
It's a "computer programming language"!!!!!  
It's an "interpreted language" rather than a "compiled language".  
Nothing to do with "java" language.  

Javascript runs in browser with interpreters.(it can also be used in other "hosts".)  
But need to be careful with different browsers.  
Standards set by w3c  
(some web working fondamental concepts. like web server, http, client, ip addresse, dns...etc)  

## why learn js
- it's widely used and available.
- it's very versatile(polyvalant), can be used in many cases.

JavaScript can do lots of things!!!!  

## tools needed to javascript development
- a text editor
- a browser

## the scripts go to ...
since major browsers use javascript as default scripting language. `<script>` tag (without `type`) is enough. however use of the `type` attribute is "mandatory" according to w3c standards. 
But no need to add `text` attribute.

linking to an external js file by adding :
```
<script type="text/javascript" src= "the.js"></script>
```
advantages of linking!  
- code reuse. also easyer for maintanence.
- make it "cacheable"!

## here comes the first program
you can put `<script>` where ever you want in a file. but it's better make it inside the `<head>` or the `<body>`.  
it's also better to always specify the "type" attribute like:
```
<script type="text/javascript">
```
then finally the first page with javascript:
```
<html>
    <body bgcolor="white">
        <p>paragraph 1</p>
        <script type="text/javascript">
            document.bgcolor = "red";
        </script>
    </body>
</html>
```
- `document` refers to the web page "document".
- `bgcolor` sets the background color.
- `;` is used to indicate the end of a "statement".
- "parsing" = gramatical analysis = read through the code and execute them.

**The "parsing" of a web page:**

```
<html>
<body bgcolor="white">
    <p>paragraph 1</p>
    <script type="text/javascript">
        //a comment for first script block.
        alert("first script block");
    </script>

    <p>paragraph 2</p>
    <script type="text/javascript">
        document.bgcolor = "red";
        alert("second script block");
    </script>
    <p>paragraph 3</p>
</body>
</html>
```

(if it doesn't work it might be a probleme because of copying directly from pdf. replace `"` by `"` to fix it.)  

- `//` is to use for comment.
- `alert()` is a function (function = pieces of js code. it takes some information, processes it, and gives a result.) that "alert" or "inform" the user by displaying message box. the message to be dissplay is given in te "()" as *parameter*.
- the `alert()` function is a *modal*. it means that the *parsing* of the page stops (brought to a halt) when `alert()` function is used and doesn't restart until the user closes the box.
- setting properties of the page: html = static (set it once, cant change it); js = dynamic(can change it all the time.)  

**so the use of javascript is to add some sort of intelligence or logic to the page, or to add special effects.**

## some "writtings" to the page
```
<!doctype html public "-//w3c//dtd xhtml 1.0 transitional//en"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<body >
    <p id="ResultsP"></p>
    <script type="text/javascript">
    // Script block 1
    document.getElementById('ResultsP').innerHTML = 'Hello World!';
    </script>
</body>
</html>
```

- first three lines are to set the page as "xhtml". Not that important.
- give an "id" to the `<p>` tag.
- get the element who's id is XXX and set the content to "Hello World!".
- the code **should be after** the paragraph that you want to set.

## and finally some "browser" problems!
Let your page be backward compatible? or just let it "degrade gracefully"?  
(degrade gracefully = the page gives alert or still looks "OK" with older browsers.)
