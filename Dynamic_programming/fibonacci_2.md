```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      int  n=sc.nextInt();
      int dp[] = new int[n+1];
      if(n<=1){
        System.out.print(n);
        return;
      }
      dp[0] = 0;
      dp[1] = 1;
      for(int i=2;i<=n;i++){
        dp[i] = dp[i-1]+dp[i-2];
      }
      System.out.print(dp[n]);
    }
}
```
# model problems

### leet 509

```java
class Solution {
    public int fib(int n) {
        int[] dp = new int[n+1];
        if(n<=1){
            return n;
        }
        dp[0]=0;
        dp[1]=1;
        for(int i=2;i<n+1;i++){
            dp[i]=dp[i-1]+dp[i-2];
        }
        return dp[n];
    }
}
```


### leet 70

```java
class Solution {
    public int climbStairs(int n) {
     int dp[] = new int[n+1];
      if(n<=1){
        //System.out.print(n);
        return n;
      }
      dp[0] = 1;
      dp[1] = 2;
      for(int i=2;i<=n;i++){
        dp[i] = dp[i-1]+dp[i-2];
      }
      return dp[n-1];
    }
}
```
