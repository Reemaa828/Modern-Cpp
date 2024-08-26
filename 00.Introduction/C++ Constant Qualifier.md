# What's a constant variable?
- We can make a variable unchangeable by deﬁning the variable’s type as **`const`**.
- any assignment to this variable will cause an error.
- it must be initialized.
- The one restriction is that we may use only those operations that cannot change an object value.

```c++
const int x =3030;

```
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/ea577d81de7502aa8a00c8beeb2df3fb/raw/image.png)
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/c8c0b76a320ecb1f0701f4e77f03557e/raw/image.png)


_____
# Reference to const
we can bind a reference to an object of a const type.To do so we use a reference to const, which is a reference that refers to a const type. Unlike an ordinary reference, a reference to const **cannot be used to change the object** to which the reference is bound.
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/97a2f52f2f68f05b72315daee6c91fd5/raw/image.png)
# Initialization of reference to const
## Exception to` type of reference must match the type of object`
- we can initialize a `reference to const` from any expression that can be converted  to the type of the reference.
- we can bind a `reference to const` to a non-const object, a literal, or a more general expression.
<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->
![](Pasted%20image%2020240825173434.png)

<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->
![](Pasted%20image%2020240825175428.png)
> [!NOTE]
> ```C++
> int a=90;
> const int &x =a;
> a=80;
> cout << a <<x; //both are 80

____
# Pointers and const
just like `reference to const`, a `pointer to const` may not be used to change the object to which the pointer points. We may store the address of a const object only in a pointer to const.
<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->
![](Pasted%20image%2020240825183139.png)
<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->
>[!NOTE] 
>it's a pointer to const but the pointer itself can hold address of another object
![](Pasted%20image%2020240825183610.png)

## Exception to` type of pointer must match the type of object`
The first exception is that we can use a pointer to const to point to a non-const object only;
<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->
![](Pasted%20image%2020240825183758.png)

<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->
![](Pasted%20image%2020240825184235.png)



___________

# pointer or reference to const affect what you can do with pointer or reference(can't change the value of object).
______


# `const` Pointers
- Unlike references, pointers are objects. Hence, as with any other object type, we can have a pointer that is itself const.
- Like any other const object, a const pointer must be initialized, and once initialized, its value (i.e., the address that it holds) may not be changed.
- The fact that a pointer is itself const says nothing about whether we can use the pointer to change the underlying object. (we can use it to change value of object).Whether we can change that object depends entirely on the type to which the pointer points.
- We indicate that the pointer is const by putting the `const` after the `*`.
<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->
![](Pasted%20image%2020240825185501.png)
<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->
![](Pasted%20image%2020240825192041.png)
_______________
# `Top-level const` AND `Low-level const`

- Top-level const indicates that an object itself is const. Top-level const can appear in any object type, i.e., one of the built-in arithmetic types, class type, or a pointer type. 
- Low-level const appears in the base type of compound types such as pointers or references.
>[!NOTE]
>pointer types, unlike most other types, can have both top-level and low-level const independently.
>`const int * const ptr=&90;`
<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->

![](Pasted%20image%2020240825194154.png)
- **The distinction between top-level and low-level matters when we copy an object. When we copy an object, top-level consts are ignored.**
- l**ow-level const is never ignored. When we copy an object, both objects must have the same low-level const**
<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->
![](Pasted%20image%2020240825194513.png)
>[!NOTE]
>we can convert a non-const to const but not the other way round.
<!--⚠️failed to create gist, net::ERR_INTERNET_DISCONNECTED-->

![](Pasted%20image%2020240825195543.png)
