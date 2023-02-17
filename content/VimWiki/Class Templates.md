# Class Templates
#cpp 
```cpp
template<typename Object>
class MemoryCell
{
	public:
		explicit MemoryCell(const Object & initialValue = Object()): storedValue(initialValue){ } // Object()-- a zero parameter constructor
		const Object & read() const{
		 return storedValue;}
		void write(const Object &x){
			storedValue = x}
	private:
		Object storedValue;


}

int main(){
	MemoryCell<int> m1;
	MemoryCell<string> m2;("hello");

	m1.write(37);
	m2.write(m2.read()+"world");
	cout<<m1.read()<<endl<<m2.read()<<endl;
	return 0;
}

```
The template above work for any type `object`, if the `object` have zero-parameter constructor, a [[copy constructor]], and a copy assignment operator.

Notice:
- that `Object` is passed by constant reference.
- default value for the constructor is not 0, as 0 in c++ may not be a valid `Object`.
- 