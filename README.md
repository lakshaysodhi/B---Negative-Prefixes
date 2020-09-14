# B---Negative-Prefixes
#include <bits/stdc++.h>
using namespace std;
#define ll long long
#define ld long double


int main() {

   int t;
   cin>>t;
   while(t--){
        int n;
        cin>>n;
        vector<int> A(n);
        for(int i=0;i<n;i++){
            cin>>A[i];
        }
        unordered_map<int,int> fixed;
        for(int i=0;i<n;i++){
            int x;
            cin>>x;
            if(x==1){
                fixed[i]++;
            }
        }
        priority_queue<int> biggest;
        for(int i=0;i<n;i++){
            if(fixed.count(i)==0){
                biggest.push(A[i]);
            }
        }
        for(int i=0;i<n;i++){
            if(fixed.count(i)==0){
                A[i]=biggest.top();
                biggest.pop();
            }
        }
        for(int i=0;i<n;i++){
            cout<<A[i]<<" ";
        }
         cout<<endl;
   }

}


