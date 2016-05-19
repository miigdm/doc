# Pixelant JavaScript Style Guide

##Frontend workflow

We start from general rules, that help developers define and maintain consistent coding styles between different editors and IDEs.  
Every developer should use these rules in all files, to have identical code style for all developers. So if you join a project when it has already started, it will be better, if 
code style is the same, as you usually use. Also it helps to avoid git mistakes with line 
endings and spaces.

**Rules:**  
1. Document charset = utf-8
2. Replace tabs by spaces. Indent style = space
3. Indent size = 4 (whitespaces)
4. Line ending = lf (Unix)
5. Remove any whitespace characters preceding newline characters
6. Every file should ends with a newline when saving

So the better way to use this rules, is "[EditorConfig](http://editorconfig.org/)" plugin.  

Example of .editorconfig file:

```
root = true

[*]
indent_style = space
indent_size = 4
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

[*.md]
trim_trailing_whitespace = false
```
###JavaScript Code Style checkers:
* [JSCS](https://github.com/mdevils/node-jscs#configuration) 
* [JsHint](http://www.jshint.com/docs/options/)

###Pixelant JSCS rules:
* Requires curly braces after statements ( "if", "else", "for" etc...)  
"requireCurlyBraces": ["if", "else", "for", "while", "do", "try", "catch", "case", "default"]

* Requires space after keyword ("if", "else", "for" etc...)  
"requireSpaceAfterKeywords": ["if", "else", "for", "while", "do", "switch", "return", "try", "catch"]  

Valid 
```javascript
return true;
 if (x) {x++;}
```

* Requires space before {} in function declarations  

Valid 
```javascript
 function() {}
 function a() {}
 ```
Invalid
```javascript
 function(){}
 function a(){}
 ```
 
 * Disallows space before () in function declarations  
 "disallowSpacesInFunctionExpression": { "beforeOpeningRoundBrace": true }  

Valid
```javascript
 function() {}
 function a() {}
 ```
Invalid
```javascript
 function () {}
 function a () {}
 ```
 
* Disallows multiple var declaration  
"requireMultipleVarDecl": true

Valid
```javascript
 var x = 1,
     y = 2,
     z;
```
Invalid
```javascript
   var x = 1;
   var y = 2;
   var z;
```

* Disallows empty blocks  
"disallowEmptyBlocks": true

* Requires space after opening object curly brace and before closing  
"disallowSpacesInsideObjectBrackets":"all"

Valid 
```javascript
var x = { a: { b: 1 } };
```
Invalid
```javascript
 var x = {a: {b: 1}};
```

* Disallows space after opening array square bracket and before closing  
"disallowSpacesInsideArrayBrackets": true

Valid 
```javascript
 var x = [1];
```
Invalid
```javascript
 var x = [ 1 ];
```

* Disallows space after opening round bracket and before closing  
"disallowSpacesInsideParentheses": true

Valid 
```javascript
var x = (1 + 2) * 3;
```
Invalid
```javascript
 var x = ( 1 + 2 ) * 3;
```

* Disallows space after object keys  
"disallowSpaceAfterObjectKeys": true  

Valid 
```javascript
var x = {a: 1};
```
Invalid
```javascript
 var x = {a : 1};
```

* Requires operators to appear before line breaks and not after  
"requireOperatorBeforeLineBreak": ["?", "+", "-", "/", "*", "=", "==", "===", "!=", "!==", ">", ">=", "<", "<="] 

Valid 
```javascript
x = y ?
      1 : 2;
```
Invalid
```javascript
  x = y
      ? 1 : 2;
```
* Disallows sticking operators to the left  
"disallowLeftStickedOperators": ["?", "+", "-", "/", "*", "=", "==", "===", "!=", "!==", ">", ">=", "<", "<="]  

* Requires sticking operators to the right   
"requireRightStickedOperators": ["!"]

* Disallows sticking operators to the right  
"disallowRightStickedOperators": ["?", "/", "*", ":", "=", "==", "===", "!=", "!==", ">", ">=", "<", "<="]

* Requires sticking operators to the left  
"requireLeftStickedOperators": [","]

* Requires sticking unary operators to the right  
"disallowSpaceAfterPrefixUnaryOperators": ["++", "--", "+", "-", "~", "!"]

* Requires sticking unary operators to the left  
"disallowSpaceBeforePostfixUnaryOperators": ["++", "--"]

* Disallows sticking binary operators to the left  
"requireSpaceBeforeBinaryOperators": ["+", "-", "/", "*", "=", "==", "===", "!=", "!=="]

* Disallows sticking binary operators to the right  
"requireSpaceAfterBinaryOperators": ["+", "-", "/", "*", "=", "==", "===", "!=", "!=="]  

* Disallows multiple blank lines in a row  
"disallowMultipleLineBreaks": true

* Disallows placing keywords on a new line  
"disallowKeywordsOnNewLine": ["else"]  

Valid 
```javascript
 if (x < 0) {
     x++;
 } else {
     x--;
 }
````

Invalid
```javascript
 if (x < 0) {
     x++;
 } 
 else {
     x--;
 }
```

* Requires placing line feed at file end  
"requireLineFeedAtFileEnd": true

* Option to check var that = this expressions  
"safeContextKeyword": "that"

Valid
```javascript
 var that = this;
```
Invalid
```javascript
 var _this = this;
```
* Requires member expressions to use dot notation when possible  
"requireDotNotation": true

* Disables style checking for specified paths  
"excludeFiles": ["node_modules/**", "jquery.js"]


---
###Pixelant jshint rules:

* This option allows you to force all variable names to use either camelCase style or UPPER_CASE with underscores  
"camelcase": "true"

Valid
```javascript
 var camelCase = 0;
 var UPPER_CASE = 4;
```
Invalid
```javascript
 var camelcase = 0;
```
* This options prohibits the use of == and != in favor of === and !==  
	"eqeqeq": "true"


* This option prohibits the use of immediate function invocations without wrapping them in parentheses  
	"immed": "true"
    
Valid
```javascript
 var a = (function() { return 1; })();
 var b = (function() { return 2; }());
```
Invalid
```javascript
 var a = function() { return 1; }();
 var b = function() { return 2; }();
```
* This option prohibits the use of a variable before it was defined  
	"latedef": "true"

* This option requires you to capitalize names of constructor functions
	"newcap": "true"
    
Valid 
```javascript
 var a = new Constr();
```
Invalid
```javascript
 var a = new constr();
```

* This option enforces the consistency of quotation marks used throughout your 
code  
"quotmark": "single"

Valid 
```javascript
 var x ='x';
```
Invalid
```javascript
  var x = "x";
```
* This option prohibits the use of explicitly undeclared variables  
	"undef": "true"

* This option warns when you define and never use your variables  
	"unused": "true"

* This option makes it an error to leave a trailing whitespace in your code  
	"trailing": "true"

* This option enforces specific tab width for your code  
	"indent": "4"


---

###Plugin for Sublime Text 3:  
https://github.com/SublimeLinter/SublimeLinter3  
https://github.com/SublimeLinter/SublimeLinter-jscs  
https://github.com/SublimeLinter/SublimeLinter-jshint  

In root of every project, you should have this files .jshintrc and .jscs.json  with our rules.  

**File [.jscs.json]:**
```javascript
{
    "requireCurlyBraces": ["if", "else", "for", "while", "do", "try", "catch", "case", "default"],
    "requireSpaceAfterKeywords": ["if", "else", "for", "while", "do", "switch", "return", "try", "catch"],
    "requireSpacesInFunctionExpression": { "beforeOpeningCurlyBrace": true },
    "disallowSpacesInFunctionExpression": { "beforeOpeningRoundBrace": true },
    "requireMultipleVarDecl": true,
    "disallowEmptyBlocks": true,
    "requireSpacesInsideObjectBrackets": "all",
    "disallowSpacesInsideArrayBrackets": true,
    "disallowSpacesInsideParentheses": true,
    "disallowSpaceAfterObjectKeys": true,
    "requireOperatorBeforeLineBreak": ["?", "+", "-", "/", "*", "=", "==", "===", "!=", "!==", ">", ">=", "<", "<="],
    "disallowLeftStickedOperators": ["?", "+", "/", "*", "=", "==", "===", "!=", "!==", ">", ">=", "<", "<="],
    "requireRightStickedOperators": ["!"],
    "disallowRightStickedOperators": ["?", "/", "*", ":", "=", "==", "===", "!=", "!==", ">", ">=", "<", "<="],
    "requireLeftStickedOperators": [","],
    "disallowSpaceAfterPrefixUnaryOperators": ["++", "--", "+", "-", "~", "!"],
    "disallowSpaceBeforePostfixUnaryOperators": ["++", "--"],
    "requireSpaceBeforeBinaryOperators": ["+", "-", "/", "*", "=", "==", "===", "!=", "!=="],
    "requireSpaceAfterBinaryOperators": ["+", "-", "/", "*", "=", "==", "===", "!=", "!=="],
    "disallowKeywords": ["with"],
    "disallowMultipleLineBreaks": true,
    "disallowKeywordsOnNewLine": ["else"],
    "requireLineFeedAtFileEnd": true,
    "safeContextKeyword": "that",
    "requireDotNotation": true,
    "excludeFiles": ["node_modules/**", "jquery.js"]
}
```

**File [.jshintrc]:**
```javascript
{
    "node": true,
    "esnext": true,
    "browser": true,
    "camelcase": true,
    "curly": true,
    "eqeqeq": true,
    "immed": true,
    "latedef": true,
    "newcap": true,
    "quotmark": "single",
    "undef": true,
    "unused": true,
    "trailing": true,
    "jquery": true,
    "nonew": true,
    "expr": true,
    "multistr": true,
    "indent": 4
}
```


---


###jQuery Style Guide

* Always use var to declare variables

Valid
```javascript
 var x = $('.class');
```
Invalid
```javascript
  x = $('.class');
```
* Use camelCase when naming objects, functions, and variables	

Valid
```javascript
 var variableName = $('.class');
```
Invalid
```javascript
  var variablename = $('.class');
  var variable-name = $('.class');
  var variable_name = $('.class');
  var VariableName = $('.class');
```
* Start every jQuery object variables names with a $  

Valid 
```javascript
 var $variableName = $('.class');
```
Invalid
```javascript
 var variableName = $('.class');
```
* Use cache

Valid
```javascript
 $element = $('.classOne'); 
 var h = $element.height();
 $element.css('height', h - 20);
```
Invalid
```javascript
 var h = $('.classOne').height();
 $('.classOne').css('height', h - 20);
```

* For events use .on()

Valid
```javascript
 var $varName = ('.class');

 $varName.on('click', function() {
     $varName.css('color', 'blue');
 });

 $varName.on('hover', function() {
     $varName.css('color', 'blue');
 });
```
Bad variant
```javascript
 var $varName = ('.class');
 
$varName.click(function() {
     $varName.css('color', 'blue');
 });

 $varName.hover(function() {
     $varName.css('color', 'blue');
 });
```

* Don't use .find() in selectors stream. Only with cached objects  
You can test this, using this code in Chrome.
Open foundation.pixelant.nu site and insert in console this code:  

```javascript
var $cache = $('.main-menu');

console.time("MyTimer");
$('.main-menu').find('li').hide();
console.timeEnd("MyTimer");

console.time("MyTimer");
$('.main-menu li').hide();
console.timeEnd("MyTimer");

console.time("MyTimer");
$cache.find('li').hide();
console.timeEnd("MyTimer");

```
