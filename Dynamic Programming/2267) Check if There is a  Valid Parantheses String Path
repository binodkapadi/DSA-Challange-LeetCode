class Solution {
public:
    int m, n;
    int t[101][101][201];

    bool solve(int i, int j, int openCount, vector<vector<char>>& grid) {
        openCount += (grid[i][j] == '(') ? 1 : -1;

        if(openCount < 0)
            return false;

        if(t[i][j][openCount] != -1) {
            return t[i][j][openCount];
        }
        
        if(i == m-1 && j == n-1)
            return t[i][j][openCount] = (openCount == 0);

        //mode down
        if(i+1 < m) {
            if(solve(i+1, j, openCount, grid)) 
                return t[i][j][openCount] = true;
        }

        //mode right
        if(j+1 < n) {
            if(solve(i, j+1, openCount, grid)) 
                return t[i][j][openCount] = true;
        }

        return t[i][j][openCount] = false;
    }

    bool hasValidPath(vector<vector<char>>& grid) {
        m = grid.size();
        n = grid[0].size();

        if((m+n-1) % 2 == 1) 
            return false;
        
        if(grid[0][0] == ')' || grid[m-1][n-1] == '(')
            return false;
        
        memset(t, -1, sizeof(t));

        return solve(0, 0, 0, grid);

    }
};