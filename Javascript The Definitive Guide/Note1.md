Javascript The Definitive Guide
===

page xiii
單字：recouped  regain recover (re-couper)
condone to disregard or overlook; to pardon or forgive


example codes in the book
http://examples.oreilly.com/9780596805531/examples/

## Chapter 1 Intro
page 1

單字：ubiquitous existing or being everywhere at the same time (omnipresent)
triad a group of three

Introduction to the book, a tour of all contents.

## Chapter 2 Lexical Structure
page 21
### charactar set
use Unicode as char set(support all knowen writen language)
Javascript is case sensitive, but HTML is not(XHTML is). Might sometimes be confusing, ex:onClick in HTML must be onclick in JS. 

### Spaces
Whitespaces and Line breaks are ignored. 
regular space character(\u0020), tab(\u0009), vertical tab (\u000B), form feed (\u000C), nonbreaking space (\u00A0), byte order mark (\uFEFF), and any character in Unicode category Zs are recognized as Whitespace.
line terminators: line feed (\u000A), carriage return (\u000D), line separator (\u2028), and paragraph separator (\u2029). 

### Unicode
 Unicode format control characters (category Cf), such as RIGHT-TO-LEFT MARK (\u200F) and LEFT-TO-RIGHT MARK (\u200E), control the visual presentation of the text they occur in. They are important for the proper display of some non-English languages and are allowed in JavaScript comments, string literals, and regular expression literals, but not in the identifiers (e.g., variable names) of a JavaScript program. As a special case, ZERO WIDTH JOINER (\u200D) and ZERO WIDTH NON-JOINER (\u200C) are allowed in identifiers, but not as the first character. As noted above, the byte order mark format control character (\uFEFF) is treated as a space character.(不是很懂……)
 
  ### Unicode Escape Sequences
  The Unicode escape for the character é, for example, is \u00E9, and the following two JavaScript strings are identical: "café" === "caf\u00e9"   // => true 
  ### Normalization
  . JavaScript assumes that the source code it is interpreting has already been normalized and makes no attempt to normalize identifiers, strings, or regular expressions itself.

page 23
### Comments
 // and the end of a line is treated as a comment and is ignored by JavaScript. Any text between the characters /* and */ is also treated as a comment; these comments may span multiple lines but may not be nested. 

### Literals
(字面常數?直接量??)
numeric literals, string literals RegExp literals, array literals, object literals

### Identifiers & Reserved Words
RW
break          delete         function       return         typeof case           do             if             switch         var catch          else           in             this           void continue       false          instanceof     throw          while debugger       finally        new            true           with default        for            null           try JavaScript also reserves certain keywords that are not currently used by the language but which might be used in future versions. ECMAScript 5 reserves the following words:
class     const     enum      export    extends   import    super
In addition, the following words, which are legal in ordinary JavaScript code, are reserved in strict mode: implements     let            private        public         yield interface      package        protected      static Strict mode also imposes restrictions on the use of the following identifiers. They are not fully reserved, but they are not allowed as variable, function, or parameter names: arguments      eval ECMAScript 3 reserved all the keywords of the Java language, and although this has been relaxed in ECMAScript 5, you should still avoid all of these identifiers if you plan to run your code under an ECMAScript 3 implementation of JavaScript: abstract       double         goto           native         static boolean        enum           implements     package        super byte           export         import         private        synchronized char           extends        int            protected      throws class          final          interface      public         transient const          float          long           short          volatile

JavaScript predefines a number of global variables and functions, and you should avoid using their names for your own variables and functions: arguments           encodeURI           Infinity  Number          RegExp Array               encodeURIComponent  isFinite  Object          String Boolean             Error               isNaN     parseFloat      SyntaxError Date                eval                JSON      parseInt        TypeError decodeURI           EvalError           Math      RangeError      undefined decodeURIComponent  Function            NaN       ReferenceError  URIError

### Semicolons (or not?)
looks like it's better to only use semicolon when necessary!

## Chapter 3 Types, Values, and Variables

page 
