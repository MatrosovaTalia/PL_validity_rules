# Kotlin validity rules

### Conditional operators

1. **if** (*condition*) statement **else** other_statement

   ​	If you're using if as an expression rather than a statement (for example, returning its value or assigning it to a variable), the expression is required to have an else branch. 

2. **switch** (*condition*) **case1:** statement ... **casen: ** statemnt.

   no ternary since if/else is an expression.

3. **Ternary operator**

   If when is used as an expression, the else branch is mandatory, unless the compiler can prove that all possible cases are covered with branch conditions (as, for example, with enum class entries and sealed class subtypes).
   
   
### Loops

1. For loop
2. While loop