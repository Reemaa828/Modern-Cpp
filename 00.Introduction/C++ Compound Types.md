# What's a compound type?
A compound type is a type that is defined in terms of another type. two of which -pointers and references-.

# References
A reference defines an alternative name to an object.A reference type “refers to” another type.We define a reference type by writing a declarator of the form &d, where d is the name being declared.
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/7e2f06b54def6eea9320428e1aecc330/raw/image.png)
- it must be initialized with a l value.
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/872f122837008bd1429220188c4c63c5/raw/image.png)

- it must be initialized cause you can't rebind the reference to another object. it remains bounded to it's initial object .
- A reference is not an object. Instead, a reference is just another name for an already existing object.
- after defining the reference you can't bound it to another object, but every operation done on the reference also appear on the object that's bounded to it.
- also any operation done to the object that's bounded to it appear on the reference.
<!--⚠️failed to create gist, net::ERR_CONNECTION_RESET-->
![](Pasted%20image%2020240824211259.png)
- when using a reference as an initializer 
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/58d6a88672a695cde60f9e6cb15acbba/raw/image.png)
- the type of a reference and the object to which the reference refers must match exactly.
- Because references are not objects, they don’t have addresses of it's own.
```c++
int i = 42;       // 'i' is an integer variable with its own memory location
int &r2 = i;      // 'r2' is a reference to 'i'

// Getting the address of 'i' using the reference 'r2'
std::cout << &i << std::endl;   // Outputs the address of 'i'
std::cout << &r2 << std::endl;  // Also outputs the address of 'i'

```


# Pointers
- A pointer is a compound type that “points to” another type.
- Like references, pointers are used for indirect access to other objects. 
- Unlike a reference, a pointer is an object in its own right.
- a single pointer can point to several different objects over its lifetime. 
- Unlike a reference, a pointer need not be initialized at the time it is defined.
- We define a pointer type by writing a declarator of the form *d, where d is the name being defined.
- A pointer has an address because it's an object.
- the types of the pointer and the object to which it points must match.
- A pointer cannot be defined by a reference because it does have an address.
```c++
int x = 10;
int &ref = x;   // ref is a reference to x
int *ptr = &ref; // ptr is a pointer to the address of x (since ref is an alias to x)

```
- A pointer holds the address of another object.
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/efddd361cdd0ec65de1dfb8e9f2d8f1e/raw/image.png)
# Pointer values
1. Point to an object:
```c++
int x = 42;
int* ptr = &x;  // ptr now holds the address of x

```
2. **Pointing to the Location Just Past the End of an Object**:

```c++
int arr[5] = {1, 2, 3, 4, 5};
int* ptr = arr + 5;  // ptr points to the location just past the last element of arr

```
3. Null pointer:
```c++
int *ptr = nullptr;
int *ptr = 0;
int *ptr = NULL;

```
4. Invalid Pointer:
An invalid pointer is any pointer that doesn't fit into the previous three categories.
>[!TIP]
>- trying to access a invalid pointer will cause segmentation fault during runtime.
> ![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/9cc7ebd6cad7088991c14613c28c8eb0/raw/image.png)
> what's a segmentation fault? (compiler doesn't catch segmentation fault)
> it's trying to access a memory that we are not allowed to access.

## Pointer accessing object
- When a pointer points to an object, we can use the deference operator (the * operator) to access that object.
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/da423e61ed3be51237962358d5ad56d5/raw/image.png)
- we can say `*p` is a lvalue that acts like the object it's pointing to. because we can do this
```c++
*p = 40;
int &r1 = *p;
```
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/1498d00ff3e2806595b363f3d9e20723/raw/image.png)
<!--⚠️failed to create gist, net::ERR_SOCKET_NOT_CONNECTED-->
![](Pasted%20image%2020240825002526.png)

# Void Pointer
The type void* is a special pointer type that can hold the address of any object. Like any other pointer, a void* pointer holds an address, but the type of the object at that address is unknown.
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/3ff642f60bede06deb1c60333359832f/raw/image.png)
>[!TIP]
>- Using a void pointer has it's limitation since the type of object is unknown we cannot perform operations on it.
>![](Pasted%20image%2020240825005839.png)<!--⚠️failed to create gist, net::ERR_CONNECTION_RESET-->

# Compound type Declaring
- a variable definition consists of a base type and a list of declarators. Each declarator can relate its variable to the base type differently from the other declarators in the same definition.
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/142b89dafe51f33b1713cf02342c01ea/raw/image.png)

![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/0b9d918c5df28641c111deb57da56998/raw/image.png)
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/2f489015aac0aa8b376acdf28491013d/raw/image.png)

# Pointer to Pointer
there are no limits to how many type modifiers ( * , &) can be applied to a declarator.
- A pointer is an object in memory, so like any object it has an address. Therefore, we can store the address of a pointer in another pointer. We indicate each pointer level by its own *. That is, we write ** for a pointer to a pointer, *** for a pointer to a pointer to a pointer, and so on.
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/c0de1544b36809698c3d8ea2084abc5d/raw/image.png)
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/d46512faa253ef8f35bd99aff530822f/raw/image.png)
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/a630db6843de101da4dea2fe225c071f/raw/image.png)

# Reference to Pointer
A reference is not an object. Hence, we may not have a pointer to a reference. However, because a pointer is an object, we can define a reference to a pointer.
- The easiest way to understand the type of r is to read the definition right to left.
```c++
int ival=90;
int ival1=88;
int *p1 = &ival1;
int *&r1=p1;
r1=&ival;
*r1=99;
```
> The symbol closest to the name of the variable (in this case the & in &r) is the one that has the most immediate effect on the variable’s type. Thus, we know that r is a reference. The rest of the declarator determines the type to which r refers. The next symbol, * in this case, says that the type r refers to is a pointer type. Finally, the base type of the declaration says that r is a reference to a pointer to an int.
![image.png](https://itg.singhinder.com?url=https://gist.githubusercontent.com/Reemaa828/a7d012ed52d375c3594657c965d81b1d/raw/image.png)
