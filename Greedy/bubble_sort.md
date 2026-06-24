# Bubble sort

```java

import java.util.*;

public class Main {
    public static void main(String[] args) {
      Scanner  z = new Scanner(System.in);
      int n=z.nextInt();
      int mat[]=new int[n];
      for(int i=0;i<n;i++){
        mat[i] = z.nextInt();
      }
      for(int i=1;i<n;i++){
        for(int j=0;j<n-i;j++){
          if(mat[j] > mat[j+1]){
            int tmp = mat[j+1];
            mat[j+1] = mat[j];
            mat[j] = tmp;
          }
        }
      }
      for(int i=0;i<n;i++){
        System.out.print(mat[i]+" ");
      }
    }
}
```
