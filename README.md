# Count-sort-in-cpp
c++

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
cout<<sb.countsort(s);
return 0;
}
