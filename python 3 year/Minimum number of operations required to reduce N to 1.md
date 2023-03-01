
  Minimum number of operations required to reduce N to 1
  
  Decrement N by 1.
  
  Increment N by 1.
  
  If N is a multiple of 3, you can divide N by 3.


## My code
```.cpp

#include<bits/stdc++.h>
using namespace std;
int main()
{
    int n;
    cin>>n;
    int count=0;
    while(n>1)
    {
        if(n%3==0)n=n/3;
        else if((n+1)%3==0)n=n+1;
        else if((n-1)%3==0)n=n-1;
        else n=n-1;
        count++;
    }
    cout<<count;
    return 0;
}

```

## GFG code

```.cpp

// C++ implementation of above approach
#include<bits/stdc++.h>
using namespace std;

// Function that returns the minimum
// number of operations to be performed
// to reduce the number to 1
int count_minimum_operations(long long n)
{

	// To stores the total number of
	// operations to be performed
	int count = 0;
	while (n > 1) {

		// if n is divisible by 3
		// then reduce it to n / 3
		if (n % 3 == 0)
			n /= 3;

		// if n modulo 3 is 1
		// decrement it by 1
		else if (n % 3 == 1)
			n--;
		else {
			if (n == 2)
				n--;
			
			// if n modulo 3 is 2
			// then increment it by 1
			else
				n++;
		}

		// update the counter
		count++;
	}
	return count;
}

// Driver code
int main()
{

	long long n = 4;
	long long ans = count_minimum_operations(n);
	cout<<ans<<endl;
	return 0;
}

// This code is contributed by mits


```
