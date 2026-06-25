# @# LCS
```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      String s1 = sc.nextLine();
      String s2 = sc.nextLine();
      int n = s1.length();
      int m = s2.length();
      int[][] dp = new int[n+1][m+1];
      for(int i=1;i<=n;i++){
        for(int j=1;j<=m;j++){
          if(s1.charAt(i-1) == s2.charAt(j-1)){
            dp[i][j] = 1+dp[i-1][j-1];
          }else{
            dp[i][j] = Math.max(dp[i-1][j] ,dp[i][j-1]);
          }
        }
      }
      System.out.print(dp[n][m]);
    }
}


```
# Model problem


### leetcode 1143

```java
class Solution {
    public int longestCommonSubsequence(String text1, String text2) {
         int n = text1.length();
      int m = text2.length();
      int[][] dp = new int[n+1][m+1];
      for(int i=1;i<=n;i++){
        for(int j=1;j<=m;j++){
          if(text1.charAt(i-1) == text2.charAt(j-1)){
            dp[i][j] = 1+dp[i-1][j-1];
          }else{
            dp[i][j] = Math.max(dp[i-1][j] ,dp[i][j-1]);
          }
        }
      }
      return dp[n][m];
    }
}
```
