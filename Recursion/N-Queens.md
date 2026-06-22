# Implementation of N-Queen(recursion)
```java
import java.util.*;

public class Main {
    public static void display(char[][] mat,int n){
      for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
          System.out.print(mat[i][j]+" ");
        }
        System.out.println();
      }
      System.out.println();
    }
    public static boolean check(char[][] mat,int n,int row,int col){
      int i,j;
      for(i=row,j=col;i>=0;i--){
        if(mat[i][j]=='Q'){
          return false;
        }
      }
      for(i=row,j=col;i>=0&&j>=0;i--,j--){
        if(mat[i][j]=='Q'){
          return false;
        }
      }
      for(i=row,j=col;i>=0&&j<n;i--,j++){
        if(mat[i][j]=='Q'){
          return false;
        }
      }
      return true;
    }
    public static void func(char[][] mat,int n,int row){
      if(row==n){
        display(mat,n);
      }
      else{
        for(int col=0;col<n;col++){
          if(check(mat,n,row,col)){
            mat[row][col]='Q';
            func(mat,n,row+1);
            mat[row][col]='-';
          }
        }
      }
    }
    public static void main(String[] args) {
      Scanner sc=new Scanner(System.in);
      int n=sc.nextInt();
      char[][] mat=new char[n][n];
      for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
          mat[i][j]='-';
        }
      }
      func(mat,n,0);
    }
}
```
