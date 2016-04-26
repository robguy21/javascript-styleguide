# Rob's Javascript Styleguidelines 
(not to be confused with an actual styleguide)

### Language Rules

### Style Rules

#### Commenting
This is the first section as it is one of the most important and sometimes overlooked aspect when writing javascript. Comments should explain code lines or code blocks,  never justify code written through comments.

If a comment is relevant to only one line it should be placed in-line

```
var x = someResultantValue; // Store some resultant value here.
```

If a comment is relevant to multiple lines of codes it should be stated beforehand with no line break before the code

```
// Some random function to do some or other thing
function fnName () {
	...
};
```

A block of code inside a function should be wrapped around a comment block

A start of a comment block is indicated by `//-->` 
An end of a comment block is indicated by `// end //`

```
function makeCodeGreatAgain () {
	//--> initializing variables
	var walls, moneys;
	var hair = {};
	// end //
}
```

Comments which are longer than one line should be styled accordingly:

```
/*
 * Multi line comments look neater when you don't use the first
 * or last line. At least in my opinion. And this is my styleguide.
 * So suck it.
 */
```


### Declarations

Variable declarations should be as verbose as possible. Do not use variable names such as `let x = someResultantValue;`. An exception to this is when you are using counters where variable names such as `let i|x|y|a|b = ...` is accepted.

Verbose variable names allow your code to be more legible and will make debugging ever so slightly easier.

All variables should be placed at the most logical beggining point. Some times it is not useful to put a variable declaration on ln9 if it is only used a lot further down in the document.

Variables should be declared with scope in mind. If you have a stack of functions such as...
```
function one () {}.
function two () {};
function three () {}.
```
 
and each function may have a requirement from their parent's scope, function one may need `const varOne = 180';` and function three may need `const varThree = 'exodus'` so place these declarations as such...

```
const varOne = 180;

function one () {};

function two () {};

const varThree = 'exodus';

function three () {};

```

Please remember that this rule should ONLY apply when your files are getting unfortunately long (which is a point of concern already) and if you need to follow the above mentioend rule it probably means that you're file is too long and is becoming difficult to read. So keep it short and hopefully you'll be able to do what everyone says and declare your vars at the top of your file.

With es6 we are encouraged to use let and const as replacements of var. As such when declaring variables use either let or const. `var` should be reserved for function declarations only.

```
const trans = "formers";

let pi = 3.16;

var exodus = function () {};
```
