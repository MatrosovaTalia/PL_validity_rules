# Kotlin validity rules

### Conditional operators

1. `if` (*condition*) statement `else` other_statement

   ​	If you're using if as an expression rather than a statement (for example, returning its value or assigning it to a variable), the expression is required to have an else branch. 

2. `when` (*condition*) `case1:` statement ... `casen:` statemnt, `else` statement.

   Similar to switch/case operator. Else branch is mandatory, unless the compiler can prove that all cases are covered.	

3. **Ternary operator**
   If when is used as an expression, the else branch is mandatory, unless the compiler can prove that all possible cases are covered with branch conditions (as, for example, with enum class entries and sealed class subtypes).

4. **For loop** operates through everything that provides an iterator:

   * has a member- or extension-function `iterator()`, whose return type 
     * has a member- or extension-function `next()`, and 
     * has a member- or extension-function `hasNext()` that returns `Boolean`.

### Classes and objects

5. Primary constructor is valid if it does not contain any code.

6. Class is inheritable if it is marked as `open`.

7. Overriding methods requires explicit modifiers (*override*) for overridable members. Method is overridable if it is not marked as *final* .

8. To override property properties declared on a superclass that are then redeclared on a derived class 

* must be prefaced with `override`
* must have a compatible type
* Each declared property can be overridden by a property with an initializer or by a property with a `get` method.

9. Inheritance of multiple implementations of the same member from different immediate superclasses is valid if that member is overridden. Square class must provide its own implementation of draw() to avoid ambiguity.

```kotlin
open class Rectangle {
    open fun draw() { /* ... */ }
}

interface Polygon {
    fun draw() { /* ... */ } 
}

class Square() : Rectangle(), Polygon {
    // The compiler requires draw() to be overridden:
    override fun draw() {
        super<Rectangle>.draw()
        super<Polygon>.draw() 
    }
```

10. If the property is declared as read-only `val`, it is invalid to change its value.
11. It is valid to mark a compile time constant with `const` modifier if the property is :
    * Top-level, or member of an object declaration or a companion object;
    * Initialized with a value of type String or a primitive type;
    * there is no custom getter.
12. Interfaces can contain declarations for abstract methods as well as method implementations. 
13. If the class derives from multiple interfaces it must implement all methods, that are inherited from multiple interfaces. Even if a method has only one implementation among the interfaces.

``` kotlin
interface A {
    fun foo() { print("A") }
    fun bar()
}

interface B {
    fun foo() { print("B") }
    fun bar() { print("bar") }
}

class C : A, B {
    override fun foo() {
        super<A>.foo()
        super<B>.foo()
    }

    override fun bar() {
        super<B>.bar()
    }
}
```

Although method bar() has only implementation in interface B and declaration only in interface A, class C, that derives from A and B must implement it.

15. Visibility modifiers are not valid for local variables, functions and classes.

### Functions

16. Implicit widening is invalid. One cannot call a function, that expects Double, with Int or Float without explicit cast to Double.

    ``` kotlin
    fun main() {
        fun printDouble(d: Double) { print(d) }
    	val i = 1    
    	val d = 1.1
    	val f = 1.1f 
    
    	printDouble(d)
    //    printDouble(i) // Error: Type mismatch
    //    printDouble(f) // Error: Type mismatch
    }
    ```

17. The return type of a function cannot be omitted unless it is `Unit`.

18. Tail recursion modifier `tailrec` is valid if the function calls itself as the last operation it performs. `tailrec` modifier is invalid if `try/catch/finally` blocks are used inside the function.

19. It is possible to use `_` for unused lambda parameter.

20. 

 





























































Link to the official Kotlin grammar:
https://kotlinlang.org/docs/reference/grammar.html#whileStatement