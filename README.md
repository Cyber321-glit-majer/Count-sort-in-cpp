# Count-sort-in-cpp
c++

**for string**

```
#include<bits/stdc++.h>
using namespace std;
class Solution{
    public:
    //Function to arrange all letters of a string in lexicographical 
    //order using Counting Sort.
    string countSort(string arr){
     int n=arr.size();
     int size=256;
     char output[n];
     int count[size];
     for(int i=0;i<size;i++)
     {
         count[i]=0;
         
     }
     for(int i=0;i<n;i++)
     {
         count[arr[i]]++;
     }
     for(int i=1;i<=size;i++)
     {
         count[i]+=count[i-1];
     }
     for(int i=0;i<n;i++)
     {
         output[count[arr[i]]-1]=arr[i];
         count[arr[i]]--;
     }
     for(int i=0;i<n;i++)
     {
         arr[i]=output[i];
     }
     return arr;
     
    }
};
int main()
{
string s="anbsfh";
Solution sb;
cout<<sb.countSort(s);
return 0;
}


```

**for integer**

```
/******************************************************************************

Welcome to GDB Online.
GDB online is an online compiler and debugger tool for C, C++, Python, Java, PHP, Ruby, Perl,
C#, OCaml, VB, Swift, Pascal, Fortran, Haskell, Objective-C, Assembly, HTML, CSS, JS, SQLite, Prolog.
Code, Compile, Run and Debug online from anywhere in world.

*******************************************************************************/
#include <iostream>

using namespace std;
void count(int a[],int n)
{
    int count[10];
    int output[10];
    int mx=a[0];
    for(int i=0;i<n;i++)
    {
        if(a[i]>mx)
        {
            mx=a[i];
        }
    }
    for(int i=0;i<=mx;i++)
    {
        count[i]=0;
    }
    for(int i=0;i<n;i++)
    {
        count[a[i]]++;
    }
    for(int i=1;i<=mx;i++)
    {
        count[i]+=count[i-1];
    }
    for(int i=mx-1;i>=0;i--)
    {
        output[count[a[i]]-1]=a[i];
        count[a[i]]--;
    }
    for(int i=0;i<n;i++)
    {
        a[i]=output[i];
    }
}
int main()
{
    int a[]={1,5,8,3,2,7,4,2};
    int n=sizeof(a)/sizeof(a[0]);
    count(a,n);
    for(int i=0;i<n;i++)
    {
        cout<<a[i]<<" ";
    }

    return 0;
}
