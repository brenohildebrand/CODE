//NOI 07 - Hole
//Idea: https://github.com/Rockbet/Problems/blob/master/NOI/2007/Hole.cpp

#include <bits/stdc++.h>
using namespace std;

const int MAXN = 1030;
int n,k, ans;
int matrix[MAXN][MAXN];
int prefix[MAXN][MAXN];

void binarysearch(){

	int l = 1, r = n, mid;

	while(l <= r){

		mid = (l+r)/2;

		bool ok = false;
		for(int i=1; i<=n; i++){
			for(int j=1; j<=n; j++){

				//Checking limits
				if(i - mid + 1 < 1 || j - mid + 1 < 1) continue;

				//Checking if it's possible to build a square
				if(prefix[i][j] - prefix[i-mid][j] - prefix[i][j-mid] + prefix[i-mid][j-mid] == 0) ok = true;

			}
		}

		if(ok){
			ans = mid;
			l = mid+1;
		}else r = mid-1;
	
	}

}

int main(){

	ios_base::sync_with_stdio(0);cin.tie(0);cout.tie(0);

	cin >> n >> k;

	for(int i=1; i<=k; i++){
		int a,b;
		cin >> a >> b;
		matrix[a+1][b+1] = 1;
	}	

	//Calculating prefixes

	for(int i=1; i<=n; i++)
		for(int j=1; j<=n; j++)
			prefix[i][j] = prefix[i-1][j] + prefix[i][j-1] - prefix[i-1][j-1] + matrix[i][j];

	//Let's use binary search

	binarysearch();

	cout << ans << "\n";

	return 0;

}
