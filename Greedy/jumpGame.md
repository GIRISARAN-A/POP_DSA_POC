# JumpGame(leetcode 55)
```java
import java.util.*;

class Main {
     public static boolean canJump(int[] nums) {
        int max=0;
        for(int i=0;i<nums.length;i++){
            if(max<i){
                return false;
            }
           max = Math.max(max,i+nums[i]);
        }
        return true;
    }
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] nums = new int[n];
        for(int i=0;i<n;i++){
            nums[i] = sc.nextInt();
        }
        boolean res = canJump(nums);
        System.out.print((res==true)?"can":"cant");
    }
}
```
