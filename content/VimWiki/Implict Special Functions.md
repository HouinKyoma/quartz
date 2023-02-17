## Destructors

```cpp
~IntCell();
```
called whenever an object goes out of scope or is being `delete`.
- Jobs includes, `delete` any `new`, close file
- default destructor simply applies destructor on each data member.
## Copy Constructor
A special constructor required to construt a copy of a same type object.
- decalaration with initialization

```cpp
IntCell B = C;
IntCell B(C);

IntCell( const IntCell & rhs);
//cases when copy constructor is being used
```
- an object passed using call by value
- an object returned by value

**default**: the copy constructor is being applied to each data member, for primitive types, the simple assignment is done.


## `operator=`
```cpp
const IntCell & operator=(const IntCell &rhs);
```
**copy assignment operator** is called when `=` is applied to two objects after they have both been previously constructed. 
`lhs = rhs` is intended to copy the state of `rhs` into `lhs`. 
**default**: applying `=` to each data member in turn.

### Problem of the default
if our class is consisted of primitive types and class objects that the default make sense, then default is good.

**when a class member contains a ponter**:
Suppose we have an object contains one pointer points to a dynamically allocated object.
- the default destructor does nothing for pointer, as we need to `delete` ourselves
- copy constructor and `=operator` both just copy the value(the address) of the pointer.
	- Thus we just have two object point to one same address, which is **shallow copy**, though we would typically want a **deep copy**.
### When default does not work
- contains pointer type member, and the member is allocated by member function
