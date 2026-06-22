# Binary search tree basic operations
### operations: add, delete, find, inorder, levelorder, minimum
```java
import java.util.*;

class  Node{
		int  data;
		Node  left;
		Node  right;
		Node(int  data){
		  this.data=data;
      left = right = null;
   }
}

class  BST{
    Node  root=null;

Node  create(Node  root,int  val){

      if(root==null){
          return  new  Node(val);
       }
      else  if(val<root.data){
          root.left=create(root.left,val);
       }
      else  if(val>root.data){
          root.right=create(root.right,val);
       }
       return root;
}

Node  rm(Node  root, int  tar){

    if(root==null){
       return  null;
    }
    else  if(tar<root.data){
         root.left=rm(root.left,tar);
     }
    else  if(tar>root.data){
         root.right=rm(root.right,tar);
     }
    else{
       if(root.left == null && root.right == null){
           return  null;
       }else  if(root.left == null){
           return  root.right;
       }else  if(root.right == null){
           return  root.left;
       }
       else{
            Node  tmp= root.right;
            min(tmp);
            root.data= tmp.data;
            root.right= rm(root.right,tmp.data);
        }
     }
       return root;
}

int  min(Node  root)
{
     while(root.left != null){
          root = root.left;
     }
     return  root.data;
}

void  inorder(Node  root){

		if(root==null){
		   return;
		}
		inorder(root.left);
		System.out.print(root.data+" ");
		inorder(root.right);
}

Node  find(Node  root,int  lmnt){
		
		if(root == null){
		   return  null;
		}

		if(lmnt < root.data){
		     return  find(root.left,lmnt);
		}

		if(lmnt > root.data){
		     return  find(root.right,lmnt);
		}
  return root;
}

void  levelorder(Node  root){
	if(root == null){
	     return;
	}
	Queue<Node> q = new  LinkedList<>();
	q.add(root);
	while(!q.isEmpty()){
		Node  tmp = q.poll();
		System.out.print(tmp.data + " ");
		if(tmp.left != null){
		q.add(tmp.left);
		}
		if(tmp.right != null){
		q.add(tmp.right);
		}
}
}
}

public  class  Main {

public  static  void  main(String[] args) {

Scanner  sc=new  Scanner(System.in);
int  n=sc.nextInt();
int  rmv = sc.nextInt();
int  fin=sc.nextInt();
BST  bst=new  BST();
for(int  i=0;i<n;i++){
		int  val=sc.nextInt();
		bst.root=bst.create(bst.root,val);
}

//inord3r

System.out.print("Inorder: ");

bst.inorder(bst.root);

System.out.println();

//delete element

bst.rm(bst.root,rmv);

System.out.print("::After deletion::");

bst.inorder(bst.root);

System.out.println();

//finding element

System.out.println((bst.find(bst.root,fin) != null)?"found":"not Found");

System.out.println("Min: " + bst.min(bst.root));

//level ord3r

System.out.print("lvlord3r: ");

bst.levelorder(bst.root);

}
}
```
