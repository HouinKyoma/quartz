# Java Array
#java 

## Declaration
`int[] scores;`
`scores = new int[4];` -- define the array as having 4 elements, and scores contains now a reference to the the array of 4 elements.
- Java array is a reference to to the actual array, so it is a [[Reference Variables]].
- Java will fill the array with default value of the type initially

`int[] b = new int[] {10,20,30};`
Another way of definition

## Array length
`length` is an instance variable every array has. And it is not a method
## Assignment Statement
```java
int[] scores;
int[] exams;
scores = {1,2,3};
exams = scores;
```
Using assignment statement to let two array variable refers to the same array.
## Clones of Array
```java
exams = scores.clone();
```

## Array as Parameter
Since array is a reference variable, any changes made with in the method to the passed array variable will be reflected on the actual array.

# [[Enhanced For-Loop]]