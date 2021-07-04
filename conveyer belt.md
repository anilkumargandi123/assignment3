#include <bits/stdc++.h>
using namespace std;
        int shipWithinDays(vector<int>& a, int days) {
        int l = *max_element(begin(a), end(a)), r = accumulate(begin(a), end(a), 0);
        while(l < r) {
            int m = l + (r - l) / 2, sum = 0, d = 1;
            for(auto n : a) {
                sum += n;
                if(sum > m) sum = n, d++;
            }
            if(d > days) l = m + 1;
            else r = m;
        }
        return l;
    }
int main()
{
    int n,d,s;
    cin>>n>>d;
    vector<int>a;
    for(int i=0;i<n;i++)
    {
        cin>>s;
        a.push_back(s);
    }
    
   int m= shipWithinDays(a,d);
   cout<<m;
}
