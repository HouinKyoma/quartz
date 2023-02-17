# Parameter Passing
#cpp 

```cpp
double avg(const vector<int> &arr, int n, bool & errorFlag);

```

Code above illustrates the 3 ways of passing parameters
-`arr` **call by constant reference**
-`n` **call by value**
-`error flag` **call by reference**

### General rule of passing parameters
1. if the parameter should be able to change the value of the actual argument, then you must use **call by reference**.
2. If the value should not be changed:
	1. if it is primitive type, use **call by value**
	2. if it is class type, use **call by constant reference**



## Parameter passing options
1. Call by value is appropriate for small objects that can't be altered
2. Call by constant reference is appropriate for large object that can't be altered
3. Call by reference is appropriate for all objects that may be altered
