# Largest in an array using recursion

```java
import java.util.*;

public class Main
{
    static int max(int[] arr,int n){
        if(n==1){
            return arr[0];
        }
       
        return Math.max(arr[n-1],max(arr,n-1));
        
    }
	public static void main(String[] args) {
       Scanner sc = new Scanner(System.in);
	   int n = 5;
	   int[] arr = new int[n];
	
	    for(int i : arr){
	        arr[i] = sc.nextInt();
	    }
	    int res = max(arr,n);
	    System.out.print(res);
	}
}
```
