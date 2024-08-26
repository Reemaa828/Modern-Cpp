# What's a constant expression?
A constant expression is an expression whose value cannot change and that can
be evaluated at compile time.
- A literal is a constant expression.
- A const object that is initialized from a constant expression is also a constant expression.
- object type + initializer is how we determine it's a constant expression.
<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->
![](Pasted%20image%2020240825202334.png)
# What's `constexpr` Variables?
we can ask the compiler to verify that a variable is a `constant expression` by declaring the variable in a `constexpr` declaration. Variables declared as `constexpr` are implicitly `const `and must be initialized by constant expressions.
for example:
```c++
constexpr int mf = 20;
// 20 is a constant expression
constexpr int limit = mf + 1; // mf + 1 is a constant expression
constexpr int sz = size();
// ok only if size is a constexpr function
```

<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->
![](Screenshot%20from%202024-08-25%2020-50-03.png)

___________

# Literal Types
The types we can use in a constexpr are known as “literal types” because they are simple
enough to have literal values.
- the arithmetic, reference, and pointer types are literal types.
- `string `, `standard IO` are not literal types they can't be used to declare a constexpr.
<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->
![](Pasted%20image%2020240825212421.png)
>[!NOTE]
Literal types and literals are two different things

__________
# Pointer with `constexpr`
- the constexpr specifier applies to the pointer, not the type to which the pointer points.
<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->
![](Pasted%20image%2020240825214221.png)
>[!NOTE]
>constexpr imposes a top-level const on the objects it defines.
