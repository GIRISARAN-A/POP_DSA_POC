# #@minimum coin change

```java

import java.util.*;

public class Main {
    public static void main(String[] args) {
      Scanner sc=new Scanner(System.in);
      int n=sc.nextInt();
      int coins[] = new int[n];
      int am=sc.nextInt();
      for(int i=0;i<n;i++){
        coins[i] = sc.nextInt();
      }
       int count=0;
      for(int i=0;i<n;i++){
        if(am >= coins[i]){
              am = am - coins[i];
              count++;
        }
        else{
          break;
        }
      }
      System.out.print(count);
    }
}
```
