# CipherSchools-T.A.-Assessment
//Question no.: 1

#include <bits/stdc++.h>
using namespace std;
 
void findNumbers(int N)
{
    for (int i = 1; i <= N / 2; i++) {
 
 
        cout << i << ", " << -i << ", ";
    }
 
    if (N % 2 == 1)
        cout << 0;
}
 
 
int main()
{
    int N;
	cin>>N;
 
    findNumbers(N);
}





//Question no:3

#include <bits/stdc++.h>
using namespace std;
int max(int a, int b) { return (a > b) ? a : b; }
int knapSack(int W, int wt[], int val[], int n)
{
 
    if (n == 0 || W == 0)
        return 0;
    if (wt[n - 1] > W)
        return knapSack(W, wt, val, n - 1);
    else
        return max(
            val[n - 1]
                + knapSack(W - wt[n - 1],
                           wt, val, n - 1),
            knapSack(W, wt, val, n - 1));
}
 

int main()
{
    int val[] = { 60, 100, 120 };
    int wt[] = { 10, 20, 30 };
    int W = 50;
    int n = sizeof(val) / sizeof(val[0]);
    cout << knapSack(W, wt, val, n);
        return 0;
}
