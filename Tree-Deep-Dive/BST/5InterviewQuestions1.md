# Check BST
given a BST , return yes or not its a binary tree

You can not check by visiting left or right node and by checking that every left node has greater right node and smaller left node.

ANother way is to apply inOrderTraversal and as we know that inOrder traversal gives and in ascending order , and if its ascending in order return the tree is binary search tree else return no its not a binary search tree.

https://leetcode.com/problems/validate-binary-search-tree/description/

```javascript
var isValidBST = function(root) {
 
    function inOrder(root,arr=[]){
        if(!root) return arr
        inOrder(root.left,arr);
        arr.push(root.val)
        inOrder(root.right,arr);
        return arr;
    }
    let dataarray=inOrder(root);
    for(let i=1;i<dataarray.length;i++){
        if(dataarray[i]<=dataarray[i-1]) return false

  
 
    }
           
     return true;
  
};
```

https://leetcode.com/problems/binary-tree-inorder-traversal/description/

```javascript
var inorderTraversal = function(root) {
    let arr=[]
    function inOrder(root){
 if(!root) return ;
 inOrder(root.left);
 arr.push(root.val);
  inOrder(root.right);
}
inOrder(root);

   
   return  arr;
};

//inorder traversal to retutn an array of traversal
```












