# maximum profit
```java

import java.util.*;

public class Main {
    public static void main(String[] args) {
      Scanner sc=new Scanner(System.in);
      int n=sc.nextInt();
      int temp;
      int[] profit=new int[n];
      int[] cost=new int[n];
      for(int i=0;i<n;i++){
        profit[i]=sc.nextInt();
      }
      for(int i=0;i<n;i++){
        cost[i]=sc.nextInt();
      }
      int amount=sc.nextInt();
      for(int i=1;i<n;i++){
        for(int j=1;j<n-i;j++){
          if(profit[j]/cost[j] < profit[j+1]/cost[j+1]){
            temp=profit[j];
            profit[j]=profit[j+1];
            profit[j+1]=temp;

            temp=cost[j];
            cost[j]=cost[j+1];
            cost[j+1]=temp;
          }
        }
      }
      int sum=0;
      for(int i=0;i<n;i++){
        if(amount<cost[i]){
          sum+=(profit[i]/cost[i])*amount;
          break;
        }
        sum+=profit[i];
        amount-=cost[i];
      }
      System.out.println(sum);
    }
}
```
