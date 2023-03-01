/*
Given a positive number n, efficiently generate binary numbers between 1 and n using the queue data structure in linear time.
*/


```.cpp

#include<bits/stdc++.h>
using namespace std;
int main()
{
    int n;
    cin>>n;
    queue<string>q;
    q.push("1");
    for(int i=1;i<=n;i++)
    {
        q.push(q.front()+'0');
        q.push(q.front()+'1');
        cout<<q.front()<<" ";
        q.pop();
    }
    return 0;
}

```
