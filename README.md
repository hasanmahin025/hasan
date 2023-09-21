#include<bits/stdc++.h>
using namespace std;
#define int  long long
int n , x;
const int N = 2e5 + 12;
int arr[N];
bool f(int k)
{
    int sum = 0;
    for(int i = 1; i <= n; i++)
    {
        if(arr[i] < k)
        {
            sum += k - arr[i];
        }
    }
    return sum <= x;
}
int32_t main()
{
   ios_base::sync_with_stdio(0);
    cin.tie(0);
    int t;
    cin >> t;
    while(t--)
    {
        cin >> n >> x;
        for(int i = 1; i <= n; i++)
        {
            cin >> arr[i];
        }
        sort(arr + 1 , arr + n + 1);
        long long l = 1  , r = 2e9 , ans = 0;
        while(l <= r)
        {
            int mid = l + (r - l) / 2;
            if(f(mid))
            {
                ans = mid;
                 l = mid + 1;
            }
            else
            {
                r = mid - 1;
            }
        }
        cout << ans << "\n";
    }

}
