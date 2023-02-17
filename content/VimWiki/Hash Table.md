## Hashing
**Hashing** the act of saving a list of variable with assigned index
**Key**: the unique identifying value
**Hashing Function**: maps the key value to array indexes.
However, it is rare that a perfect hash function can be found, which means indexes collision(different key produces same indexes) will occur.
### Dealing with collisions
1. For an object with key value given by `key`, compute the index `hash(key)`.
2. If `data[hash(key)]` does not already contain an object, then store the object in `data[hash(key)]` and end the storage algorithm.
3. If the location `data[hash(key)]` already occupied, then try index `hash(key)+1`, if it is still occupied, increment another time till vacant spot is found. When the end of the index is reached, go to the first index.
This method is called **open address hashing**
## NonInteger Keys and Java's hashCode Method
Some objects have non-Integer fields like strings, how do we hash them? They are usually handled by **encoding function** that converts the key into an integer value. All Java classes have a `hashCode` function that do such job.

## Implementations
### specification
**Table** is a collection of objects with operations for adding removing, and locating objects, controlled by a single key
### Constructor
creates with a specified capacity. 
### `size` and `capacity` method
`size()`:returns number of elelments currently in the table
`capacity()`: returns the determined capacity
### `put` method
Put a new object into the table, as we do that, we will have 2 outcome:
1. the same key is been occupied, then old object is replaced by the new object
2. if it has a key that's not in the table, then new object is added

### `containsKey` and `get` method
```java
public boolean containsKey(Object key)
//determine whether a specified key is in this table
public Object get(Object key)
//Retrieve an Object for a specified key
//The key cannot be null
//key.equals() is being used to compare objects in the table
```
### `remove`
```java
public Object remove(Object key)
// remove an object for a specided key
// null is returned when the key does not exist in the table
```
### Table -ADT
``` java
public class Table{
	private int manyItems;//size
	private Object[] keys;
	private Object[] data;
	private boolean[] hasBeenUsed;
	public Table(int capacity){
		if(capacity <= 0){
			//throw exception
		}
		keys = new Object[capacity];
		data = new Object[capacity];
		hasBeenUsed = new Object[capacity];
	}
	public boolean conatainsKey(Object key){
	
	}
	private int findIndex(Object key){
		//return -1 if not found, else return the index
		//if the object is to be put into the table, then it must be put into index hash(key), or the next index, if the index's hasBeenUsed is true, so we only need to search those indexes.
		int count = 0;
		int i = hash(key);
		while((count < data.length)&& (hasBeenUsed[i])){
			if(key.equals(keys[i]))
				return i;
			cout++;
			i = nextIndex(i);
		}
	}
}
```
### Invariants of Table ADT
1. number of elements is stored in instance variable **manyItems**
2. location for an element with a given key is at index `hash(key`. If a collision occurs, then `next-Index` is used to search forward to find the next open address. When an open address is found at an index i, then the element itself is placed in `data[i]` and element `keys[i]`,
3. And index `i` that is not currently used has `data[i]` and `keys[i]` set to `null`.
4. If an index `i` has been used at some point, then `hasBeenUsed[i]` is `true`, otherwise it is `false`.
## Java's HashTable 
## Time Analysis

