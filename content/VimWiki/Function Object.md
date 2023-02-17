# Function Object in C++

#### Case
So sometimes for a `Comparable` in a template, the defined comparison operator does not fit our need, so now we want our own defined function.
We want to pass this function along with the data.

An Object contains both data and function, so we can make an object we only function, and pass an instance. This is called **Function Object**.

```cpp
template <typename Object, typename Comparator>
const Object & findMax( const vector<Object> & arr, arr[i])
{
	int maxIndex = 0;
	for(int i = 1;i<arr.size();i++){
		if(cmp.isLessThan(arr[maxIndex],arr[i] ) ) 
			maxIndex = i;
	return arr[maxIndex];
			}
}


class CaseInsensitiveCompare{

	public:
		bool isLessThan(const string & lhs, const string & rhs) const
			{return stricmp(lhs.c_str(),rhs.c_str())<0; 
			//string.c_str returns a pointer to c string of the string object
			
			};


}

int main(){


	vector<string> arr(3);
	arr[0] = "ZEBRA"; arr[1] = "alligator";arr[2] = "crocodile";
	cout<<findMax(arr, CaseInsensitiveCompare())<<endl;

	return 0;
}







```


### Same function, another example
```cpp
template <typename Object, typename Comparator>
const Object & findMax( const vector<Object> & arr, Comparator isLessThan)
{
	int maxIndex = 0;
	for(int i = 1; i < arr.size();i++){
		if( isLessThan( arr[maxIndex], arr[i]))
			maxIndex = i;
	return arr[ maxIndex ];
	}
}

//Generic findMax
#include<functional>
template<typename Object>
const Object & findMax(const vector<Object> & arr){
	return findMax(arr,less<Object>());

}
class CaseInsensitiveCompare
{
	public:
		bool operator()(const string & lhs, const string & rhs) const
		{return stricmp(lhs.c_str(),rhs.c_str())<0;}
};

int main()
{
	vector<string> arr(3);
	arr[0] = "ZEBRA"; arr[1] = "alligator";arr[2] = "crocodile";
	cout<<findMax(arr, CaseInsensitiveCompare())<<endl;

	return 0;
}



```