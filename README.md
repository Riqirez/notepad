//행렬 곱 연산
#include <iostream>
#include <vector>

using namespace std;

int main(){
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    int m,r,n;
    cout << "m, r, n input : ";
    cin >> m >> r >> n;
    vector<vector<int>>v1(m, vector<int>(r));
    vector<vector<int>>v2(r, vector<int>(n));
    vector<vector<int>>res(m, vector<int>(n));
    
    for(int y=0; y<m; y++){
        for(int x=0; x<r; x++)
            cin >> v1[y][x];
    }

    for(int y=0; y<r; y++){
        for(int x=0; x<n; x++)
            cin >> v2[y][x];
    }

    for(int y=0; y<m; y++){
        for(int x=0; x<n; x++){
            int sum = 0;

            for(int k=0; k<r; k++)
                sum += v1[y][k] * v2[k][x];   
            
            res[y][x] = sum;
        }
    }

    for(int y=0; y<m; y++){
        for(const int &i : res[y])
            cout << i << ' ';
        cout << '\n';
    }

    return 0;
}
