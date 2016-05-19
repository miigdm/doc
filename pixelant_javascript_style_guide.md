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