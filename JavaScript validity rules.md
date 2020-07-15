# JavaScript validity rules

### Conditional operators

1. **Ternary operator**

```javascript
let result = condition ? Val1 : Val2;
```

   Val1 and val2 must return something since no continue or break could be used in this structure.

### Loops

1. **for** (start; condition; step) 

```javascript
for (;;) {
// infinitely
   }
```
- ; must be included or will through error

- The ‘start’ and ‘step’ parts should be valid

### Labels for break/continue statements

- Tags don't let you jump anywhere. Labels do not allow transferring control to an arbitrary place in the code.
   For example, there is no way to do the following:
   
```javascript
   break label; // does not jump to the label below
   label: for (...)
```
   
- A break / continue call is only possible inside the loop, and the label should be somewhere above this directive.
   
### Scripts

   If the src attribute is set, the contents of the script tag will be ignored. You cannot use the src attribute and the code inside the same <script> tag. The following example does not work:
   ```javascript
   <script src="file.js">
      alert(1); // содержимое игнорируется, так как есть атрибут src
   </script>
   ```
   You need to choose: either an external script <script src = "...">, or regular code inside the <script> tag.

### Comments

   Nested comments are not supported
   
### Variables

1. Variables names
   
   - The variable name must contain only letters, numbers, or the characters $ and _.
   
   - The first character must not be a number.
   
   - There is a list of reserved words that cannot be used as variable names because they are used by the language itself.
   
   - If we do not include “use strict” we can define the variable just assigning the value to it. Else we had to define it using ‘let’.

### Operators

1. Increment/decrement

Only applicable to the variables. Attempt to apply, for example to ```5++``` will cause an error.

### Data types

1. Methods

null/undefined has no methods. The special null and undefined primitives are exceptions. They have no corresponding “wrapper objects”, and they have no methods. In a sense, they are "the most primitive."Attempting to access properties of this value will return an error:
```javascript
alert(null.test); // error
```
2. Numbers

If we put one dot: ```123456.toString (36)```, then this will be a mistake because the JavaScript syntax assumes that the decimal part begins after the first dot. And if you put two points, then JavaScript understands that the decimal part is missing, and the method begins.

3. Strings

	1. Multiple strings

Another advantage of backquotes(``) is that they can occupy more than one line. But if you try to use single or double quotes in exactly the same way, there will be an error:
```javascript
let guestList = "Guests: // Error
  * John";
  ```
	2. Pattern function

Backquotes(``) also allow you to specify a “pattern function” before the first backtick.  Using single or double quotes will cause an error.

	3. Special characters

Include special characters where they are needed otherwise an error will be thrown.
```javascript
alert( 'I\'m the Walrus!' ); // I'm the Walrus!
```
	4. Length is a property  

Do not call like a function( ```str.length()``` )

	5. Strings are immutable

The contents of the string in JavaScript cannot be changed. You cannot take the symbol in the middle and replace it. As soon as a line is created, it is so forever.

4. WeakMap
Keys must be objects, not primitive types as it possible in ordinary Map

```javascript
weakMap.set("test", "Whoops"); // Ошибка, потому что "test" не объект
```


