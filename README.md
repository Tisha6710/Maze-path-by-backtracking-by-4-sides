# Maze-path-by-backtracking-by-4-sides
package BackTracking;

public class bestratmaze {
    public static void main(String[] args) {
        int rows=3;
        int col=4;
        int[][]maze={{1,0,1,1},
                {1,1,1,1},
                {0,1,1,1}};


        print(0,0,rows-1,col-1,"",maze);

    }
    private static void print(int sr, int sc, int er, int ec,String s,int [][] maze) {
        if(sr<0 || sc<0) return;
        if(sr>er || sc>ec) return;
        if(sr==er && sc==ec){
            System.out.println(s);
            return;
        }
        if(maze[sr][sc]==0) return;
        if(maze[sr][sc]==-1) return;
        maze[sr][sc]=-1;
        // go down
        print(sr+1,sc,er,ec,s+"D",maze);
        // gp ryt
        print(sr,sc+1,er,ec,s+"R",maze);
        // go left
        print(sr,sc-1,er,ec,s+"L",maze);
        // gp right
        print(sr-1,sc,er,ec,s+"U",maze  );
        // backtracking
        maze[sr][sc]=1;
    }
}
