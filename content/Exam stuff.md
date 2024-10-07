# Question 1
 **string literal is a non-modifiable Lvalue. Explain:**
 Answer:
 - String literals can't be safely pointed to (not with write permission)
 - If you do this, it interferes with the optimization of string literals in C++

**HOWEVER**
these properties argue for classifying string literals as Lvalues:
- strings literals are in RAM
- it has a pointer type (const char*, const wchar_t*)
- using address opperator, you can get the address to it (=> lvalue)
- able to make an extra pointer to it
- even make a non-const char pointer to it, using const_cast. writing to this location will crash
# Question 2
**Given a function: void MyFunction(std::string param);**

1) **when this is called, what std::string member function gets called?**
2) **Is there a problem with this function? If so, how would you solve it?**

Answer:
1) The function can get called in 3 ways:
	- 1. the arg is of type std::string
	- 2. the arg is of a type in the constructor of std::string
	- 3. the arg can be implicitly converted to std::string
	1) if the type of arg is std::string, it's value category determines what function gets called
		- Lvalue => std::string copy constructor
		- Xvalue => std::string move constructor
		- Prvalue expression (a.k.a. initializer expression) => if a constructor matches the initialization data, it will fire that constructor
	2) if the arg matches a constructor of std::string, it will fire that constructor (if not set to explicit)
	3) if the arg isn't of type std::string and does not match a constructor, it will get implicitly converted to one that does match an arg of a constructor of std::string (possibly using implicit conversion function)
2)  There is no problem. We would sometimes prefer const std::string&, or std::string&&. It depends on what you want it to do.