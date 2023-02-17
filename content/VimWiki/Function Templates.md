# Function Templates
#cpp 

a **function templates** is not a function but a pattern for what could be function.
```cpp
/*
*return the maximum item in array a
* Assume a.size()>0
* Comparable object must provide operator< and operator=
*/

template<typename Comparable>
const Comparable & findMax(const vector<Comparable>& a){
	int maxIndex = 0;
	for(int i = 1; i<a.size();i++){
		if(a[maxIndex]<a[i])
			maxIndex = i;
	return a[maxIndex];
	}


}

int main(){

	vector<int> v1(37);
	vector<double> v2(40);
	vector<string> v3(80);
	vector<IntCell> v4(75);
	//fill the vectors are not shown

	cout<<findMax(v1)<<endl;
	cout<<findMax(v2)<<endl;
	cout<<findMax(v3)<<endl; // all are legal
	cout<<findMax(v4)<<endl; // illegal, undefined operator<
	
}

```

When there are template and nontemplate function with same name, then nontemplate gets priority.