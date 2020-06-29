# JavaScript validity rules

### Conditional operators

1. **if** (*condition*) statement **else** other_statement

   Is always valid. 

2. **switch** (*condition*) **case1:** statement ... **casen: ** statemnt.

   Is always valid.

3. **Ternary operator**

   Val1 and val2 must return something since no continue or break could be used in this structure.

### Loops

1. **for** (start; condition; step) 

	for (;;) {
      // infinitely
   }
   ; must be included or will through error

   The ‘start’ and ‘step’ parts should be valid

2. **while - do** or **do-while**
   
   Is always valid

### Labels for break/continue statements

   Tags don't let you jump anywhere
   
   Labels do not allow transferring control to an arbitrary place in the code.
   For example, there is no way to do the following:

   break label; // does not jump to the label below
   label: for (...)
   
   A break / continue call is only possible inside the loop, and the label should be somewhere above this directive.
   
### Scripts

   If the src attribute is set, the contents of the script tag will be ignored. You cannot use the src attribute and the code inside the same <script> tag. The following example does not work:
   
   <script src="file.js">
      alert(1); // содержимое игнорируется, так как есть атрибут src
   </script>
   
   You need to choose: either an external script <script src = "...">, or regular code inside the <script> tag.

### Comments

   Nested comments are not supported
   
### Variables

1. Variables names
   
   The variable name must contain only letters, numbers, or the characters $ and _.
   
   The first character must not be a number.
   
   There is a list of reserved words that cannot be used as variable names because they are used by the language itself.
   
   If we do not include “use strict” we can define the variable just assigning the value to it. Else we had to define it using ‘let’.
