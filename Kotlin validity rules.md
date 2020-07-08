# Kotlin validity rules

### Conditional operators

1. **if** (*condition*) statement **else** other_statement

   ​	If you're using if as an expression rather than a statement (for example, returning its value or assigning it to a variable), the expression is required to have an else branch. 

2. **when** (*condition*) **case1:** statement ... **casen: ** statemnt, **else** statement.

   Similar to switch/case operator. Else branch is mandatory, unless the compiler can prove that all cases are covered.	

3. **Ternary operator**
   If when is used as an expression, the else branch is mandatory, unless the compiler can prove that all possible cases are covered with branch conditions (as, for example, with enum class entries and sealed class subtypes).

4. **For loop** operates through everything that provides an iterator:
* has a member- or extension-function `iterator()`, whose return type 
  * has a member- or extension-function `next()`, and 
  * has a member- or extension-function `hasNext()` that returns `Boolean`.



### Classes and objects

1. Primary constructor is valid if it does not contain any code. 
2. Class is inheritable if it is marked as *open*.
3. Overriding methods requires explicit modifiers (*override*) for overridable members. Method is overridable if it is not marked as *final* .
4. To override property properties declared on a superclass that are then redeclared on a derived class 
   * must be prefaced with *override*
   * must have a compatible type
   * Each declared property can be overridden by a property with an initializer or by a property with a `get` method.





Link to the official Kotlin grammar:
https://kotlinlang.org/docs/reference/grammar.html#whileStatement