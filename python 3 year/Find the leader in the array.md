**QUESTION -> Find the Leader in the array**

```.cpp

#include<bits/stdc++.h>
using namespace std;
int main()
{
    int n;
    cin>>n;
    vector<int>v(n,0);
    for(int i=0;i<n;i++)
    {
        cin>>v[i];
    }
    stack<int>st;
    vector<int>ans;
    
    for(int i=n-1;i>=0;i--)
    {
        if(st.empty())
        {
            st.push(v[i]);
            ans.push_back(v[i]);
        }
        else
        {
            while(st.size()!=0 and st.top()<=v[i])
            {
                st.pop();
            }
            if(st.size()==0)
            {
                ans.push_back(v[i]);
                st.push(v[i]);
            }
            else
            {
                ans.push_back(st.top());
            }
        }
    }

    reverse(ans.begin(),ans.end());
    unordered_set<int>ans2;
    for(auto i:ans)ans2.insert(i);
    for(auto i:ans2)cout<<i<<" ";

}

```
## method 2 : using a max variable

```.cpp

#include<bits/stdc++.h>
using namespace std;
int main()
{
    int n;
    cin>>n;
    vector<int>v(n,0);
    for(int i=0;i<n;i++)
    {
        cin>>v[i];
    }
    stack<int>st;
    vector<int>ans;
    int mx=v[n-1];

    ans.push_back(mx);
    for(int i=n-1;i>=0;i--)
    {
        if(v[i]>mx)
        {
            mx=v[i];
            ans.push_back(mx);
        }
    }

    reverse(ans.begin(),ans.end());
    
    for(auto i:ans)cout<<i<<" ";

}
```
