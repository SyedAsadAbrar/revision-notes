# **Javascript**

## **Passing Arguments**

* In Javascript, arguments are **passed by value** i.e. the value is copied and passed instead of the original variable being passed
  * **Primitives** and **Objects** can be modified but there would be no change to the original calling parameter [^1]
  * Modifying a **property value** on an object however will cause the original [calling parameter's property value to change](../behind-the-scenes/primitive-vs-objects.md/#objects)
    * This is because even though the **argument** is **passed by value** but in the case of a **reference type**, the value is actually a memory address and not a primitive value

* Javascript **DOES NOT** have **passing by reference**, but we are **passing A reference** when the argument of a function is a **reference type**

[^1]: Although, we should not change/mutate parameters of a function because it is not a good programming practice
