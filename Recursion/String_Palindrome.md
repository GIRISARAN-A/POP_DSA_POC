# String is palindrome or ! (using recursion):
```java
public class Main
{
    static boolean pali(String s,int i , int j){
        if(i>=j){
            return true ;
        }
        if(s.charAt(i) != s.charAt(j)){
          return false;
        }
        return pali(s,i+1,j-1);
        
    }
	public static void main(String[] args) {
	    String s = "iri";
	    boolean res = false;
	    String ans=" ";
	    int i=0;
	    int j=s.length()-1;
	    res = pali(s,i,j);
	    System.out.print(res);
	}
}
```
