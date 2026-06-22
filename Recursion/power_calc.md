# finding power using recursion
```java
public class Main
{
    static int pow(int n,int m){
        if(m==0){
            return 1;
        }
        return n*pow(n,m-1);
    }
	public static void main(String[] args){
	 int n=2;
	 int m=3;
	 System.out.print(pow(n,m));
	}
}
```
