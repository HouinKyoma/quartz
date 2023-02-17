# Pointers
**Pointer Variable** : stores the address of another object
Example code:
```cpp
int main(){
	IntCell *m;
	m = new IntCell(0);
	m->write(5);
	cout<<"Cell contents: "<<m->read()<<endl;

	delete m;
	return 0;



}
```

## Declaration
`int* m;` declares a pointer to a `int`;
**value** of m is the address it points at.
**No check is performed in c++ to check whether a pointer is initialized or not**
- always initialize with a value, or `NULL`.


## Dynamic Object Creation
`new` returns a pointer to the newly created object.

## Garbage Collection and `delete`
When an object is allocated by `new`, the `delete` operation must be applied to the object.
- use **automatic variable** when it can be used instead

## Assignment and Comparison
the `==` comparison returns true if the address two pointers pointed to are the same.
## Accessing Members through Pointers
If a pointer points to a class type, `->`can  be used to access visible members

## Other Operations
[[pointer arthmetics]]

