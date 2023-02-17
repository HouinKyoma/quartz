# Reference Variables
#cpp 
some times a local reference variable is being used to rename a long varaible names

```cpp
string x = findMax(a);
cout<<X<<endl;



const string& x = findMax(a);
cout<<x<< endl;


list<T> & whichList = theLists[ hash(x, theLists.size())];
if(find(whichList.begin(),whichList.end(),x) != whichList.end())
	return false;
else 
	whichList.push_back(x);

// reference variable is being used so complex expression does not have to be wrtten and evaluated four times
```

