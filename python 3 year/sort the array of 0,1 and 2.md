## sort the array of 0,1 and 2
```.cpp

#include<bits/stdc++.h>
using namespace std;
int main()
{
    int n;
    cin>>n;
    vector<int>v(n,0);
    for(int i=0;i<n;i++)cin>>v[i];

    int l=0;
    int mid=0;
    int h=v.size()-1;
    
    while(mid<=h)
    {
        if(v[mid]==0)
        {
            swap(v[mid],v[l]);
            l++;
            mid++;
        }
        else if(v[mid]==1)
        {
            mid++;
        }
        else
        {
            swap(v[mid],v[h]);
            h--;
            // mid++;
        }
        
    }
    for(auto i:v)cout<<i<<" ";
}

```
