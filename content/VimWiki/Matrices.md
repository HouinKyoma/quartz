# Matrices in C++
#cpp 
The c++ library does not provide a matrix class, but we will write one here

## Data member, constructor and accessors

```cpp
#ifndef MATRIX_H
#define MATRIX_H

#include<vector>
using namespace std;
template<typename Object>
class matrix{
	public:
		matrix(int rows, int cols) : array( rows ){
			for(int i = 0; i<rows;i++)//first declare rows, and then resize each columnd
				array[i].resize(cols);
				
		}
	const vector<Object & operator[](int row) const
		{return array[row];}
	vector<Object> & operator[](int row)
		{return array[row];}
	int numrows() const //since these are accessors, add const to make sure nothing is changed
		{return array.size();}
	int numcols() const
		{return numrows()? array[0].size():0; }
	private:
		vector<vector<Object>>array;
};

#endif
```

- We have two `operator[]` because when we want to copy, which requires us to use constant reference and plain reference at the same time, we will need both version.
- 