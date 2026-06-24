# Activity Scheduling
```java

import java.util.*;

public class Main {
    public static void main(String[] args) {
      Scanner  z = new Scanner(System.in);
      int n=z.nextInt();
      int tmp;
      int end[]=new int[n];
      int start[] = new int[n];
      for(int i=0;i<n;i++){
        start[i] = z.nextInt();
      }
      for(int i=0;i<n;i++){
        end[i] = z.nextInt();
      }
      for(int i=1;i<n;i++){
        for(int j=0;j<n-i;j++){
          if(end[j] > end[j+1]){
            tmp = start[j+1];
            start[j+1] = start[j];
            start[j] = tmp;

            tmp = end[j+1];
            end[j+1] = end[j];
            end[j] = tmp;
          }
        }
      }
      
      System.out.println();
     System.out.print("0 ");
     int pr=end[0];
     for(int i=0;i<n;i++){
      if(pr <=start[i]){
        System.out.print(i+" ");
        pr=end[i];
      }
     }
    }
}

```
