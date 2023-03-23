**Algorithm used - Moore's voting algorithm**

# Find the majority elements in the array.
```.cpp
// MOORE'S VOTING ALGORITHM
#include<bits/stdc++.h>
using namespace std;
int main()
{
    int n;
    cin>>n;
    vector<int>v(n,0);
    for(int i=0;i<n;i++)cin>>v[i];

    int c1=0,c2=0;
    int v1=v[0],v2=v[1];

    for(int i=2;i<n;i++)
    {
        if(v[i]==v1)c1+=1;
        else if(v[i]==v2)c2+=1;
        else
        {
            if(c1<c2)
            {
                c1=0;
                v1=v[i];
            }
            else{
                c2=0;
                v2=v[i];
            }
        }
    }
    c1=0;
    c2=0;
    for(int i=0;i<n;i++)
    {
        if(v[i]==v1)c1+=1;
        else if(v[i]==v2)c2+=1;
    }

    if(c1>n/2)cout<<v1<<endl;
    else if(c2>n/2)cout<<v2<<endl;
    else cout<<-1<<endl;
}
```
