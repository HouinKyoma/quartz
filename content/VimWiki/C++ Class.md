## Basic Syntax
All of the data structure will be objects
with stored data and functions that manipulates them
```cpp
/**
* A class example
*/
class Intcell
{
	public:
	/*
	*Constructors
	*/
	Intcell(){
	storedValue = 0;
	}

	/*
	Member functions
	
	*/
	int read(){
	return storedValue;
	
	}

	private:
		int storedValue;


}

```

**private**: accessible only by methods in this class
All members are private by default, the initial **public** is not optional


## Extra Constructor Syntax and Accessors
### Default Parameters
As the code block above shows, the two constructor, one zero parameter and one with 1 parameter. The `storedValue = 0` is called **default parameter**.

### Initializer List
- Used to initialize the data members directly
- Saves time when the data members are complex type with complex initialization
- Case when it is necessary
	- if a data member is [[const]] [[`const`|]] than the data member can **only be initialzed in initializer list**
	- If a data member is a class type that does not have zero-parameter constructor.

```cpp
/*
** example of initializer list
*/
public:
	explicit Intcell( int initial value = 0): 
		storedValue( initialValue) { }

```
### [[explicit]] Constructors
- make all one-parameter constructors `explicit` to avoid behind the scene type conversions.

### Constant Member Function
refers to the **mutator** and **accessor** functions.
## Separation of Interface and Implementation

### Preprocessor Commands
to prevent the header file being read more than once:
```cpp
#ifndef IntCell_H
#define IntCell_H



#endif
```
skip to the `#endif` when being read already

### Scoping Operator
`::` is called the **scoping operator**.
to Signify what class the member function belongs
### Signature
The header and the implementation function generator must match exactly, including the keywords

### Objects Declaration
In c++, the objects are declared like primitive types:
```cpp
Intcell obj1; //zero parameter constructor
Intcell obj2(12); // one parameter constructor
Intcell obj3 = 37; //incorrect when the constructor is explicit
Intcell obj4(); // incorrect this is function declaration
```

## vector and String
c++ standard has two classes: `vector` and `string`.
**difference btw built-in array and vector**
- array does not behave like a first-class object
- can not be copied with `=`
- does not remember how many item it can store
- indexing operator does not check validity
