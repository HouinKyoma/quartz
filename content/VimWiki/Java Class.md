# JAVA Class 


# Defining Class
**Syntax**:
```java
public class Sample{

	private int pop;
	private int pos; // instance variable

}
```
## Instance Variable
- private: means that you cannot read or change the data directly'

## Constructors
- has acesses to class instance variable and responsible for initializing them
- before any constructors begin its work, all **instance variables** are assigned a Java default value
- you can define **instance variable** value at its declaration, and this value will replace the Java default
- Constructor name must be same as class name
- **In reality**, constructor is not a method, so it does not have a return value.

## Zero-Parameter Constructors
- if you does not write a constructor for your class at all, then Java will provide a default, though some special case may result in problem

## Methods
- setters and getters

# Using Class
`Myclass me = new Myclass();`
- `new` keyword
- remember in java, every method will comes after an object
## Creating and Using Objects
- When a program has several objects of the same type, each object has its own copies of the instance variables.
- **Reference Variables**, any created object are called reference variable because they are refering to an Object
## Null Reference
when an object is declared but not defined, it is refering to `null`.
## Assignment Statement With Reference Variable
```java
Sample s1;
Sample s2;

s1 = new Sample s1;
s2 = s1;
```

Here `s2 = s1` is different when they primitive data type, it means **make `s2` refer to the same object that s1 is refering to**. 


## Testing for Equality for Reference Variables
Any `t1 == t2`, where both are reference variables, will compare the memory address and return true is both refering to the same address.

# Packages
## Declaring a Package
- use your Internet domain name
- *pacakage declaration* must be made on top of each .java file of the package.
	- `package edu.stonybrook.samplepackage;`
- Steps to follow:
	- underneath the class directory, create a directory called edu
	- under edu, create a directory `stonybrook`
	- under `stonybrook`, create the sample class directory
	- all the .java and .class file must be in the `samplepackage` directory
	
## Import statement
```java
import edu.stonybrook.sample.*; // import all
import edu.stonybrook.sample.myclass;

```
# Parameter, `equals()`, and `clone()`
## Static Methods
see [[static keyword in java]]
## Parameters that are Objects
- **when a parameter is an object, the parameter is initialized so that it refers to the same object that the actual argument refers to**
- thus any change that can change the passed parameter, will affect the the data.
- A method may access private instance variables of an object as long as the method is declared within the same class.
### Parameters changed during methods
- If it is **8 primitive types**:
	- change to the value does not affect the arguement, since each parameter passed in are initialized with value
- if it is **reference variables**:
	- the passed in parameters are initialized so it refers to the same object as the argument, change will affect the argument



## Returning an Object
```java
public static Location midpoint(Location p1, Location p2){
	//p1 p2: two location, has x and y data field
	// returns: a location halfway between p1 and p2
	// answer is null if either location is null
	double xMid, yMid;
	xMid = (p1.x/2)+ (p2.x/2);
	yMid = (p1.y/2)+ (p2.y/2);


	//returning
	Location answer = new Location(xMid, yMid);
	return answer;
	//this will create a new object, and now we have three locations object




}
```
## Java's Object Type
[[Object in Java]]
## Implementing `equals()`
different tan `==` operator, we want this method to be indicative of whether the datas of two objects are the same, rather than the memory address.
```java
public boolean equals(Object obj){

	if(obj instanceof DesiredClass{
		DesiredClass d = (DesiredClass) obj；
		//compare the datas that you want to
		//return true if they are same, else return false
	}
	else{
		return false;
	}

}

```

There is a [[typecasting in java|typecasting in java]] needed in the code above.



## Implementing `clone()`
- to create a copy of an object
- the change on copy will not change the original


### 1 modify the Class Head
`public class MyClass implements Cloneable`

### 2 use `super.clone()`
```java
public MyClass clone(){
	MyClass answer;
	try{
		answer = (MyClass) super.clone();
	
	}
	catch(CloneNotSupportedException e){
		throw new RuntimeException("Class does not implements cloneable")
	
	}
}
```
### 3 Make necessary modifications and return
- must be returned as `Object`(before Java 5)
- If you don't care about backward comparability, then returned as-is is fine.












[[abstract data type]]
members: methods, data, construtors of a class
instance variables: refers to the data field of a class
constructors
arithmetic overflow
reference variable: used to refer to objects
	null refererence: when an object is declared but not created yet
	a reference variable is a pointer to the data, so if reference variable a =b, and b.value-5 will also result in a.value-5
NullPointerException
Assignment Statement with Reference Variables
Clones: when an object is exactly like another object, but separate
Test for Equality
	a == b returns true if two reference variable points to the same address
Packages
	to group together stuff , one level above classes
	
package declaration
Static Methods
Parameters that are objects
   when a parameter is an object, then the parameter is initialized so that it refers to the same object that the actual argument refers to
   Subsequently, the changes made to reference variable passed to a method, will stay, unlike the eight primitive types.
method may access private memebers within class

