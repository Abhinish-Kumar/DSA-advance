### delete operation in BST

delete lea node 
```javascript
function deletee(root,target){
    if(!root) return null;
    if(root.data>target){
        root.left= deletee(root.left,target);
        return root;
    }else if(root.data<target){
        root.right= deletee(root.right,target)
        return root;
    }else{
        //if it is leaf node
        if(!root.left && !root.right){
            return null;
        }
     
    }
 return root;  //return updated tree;
    
}
deletee(root,7);
deletee(root,22);
```


delete node with 1 child node 
```javascript

function deletee(root,target){
    if(!root) return null;
    if(root.data>target){
        root.left= deletee(root.left,target);
        return root;
    }else if(root.data<target){
        root.right= deletee(root.right,target)
        return root;
    }else{
        //if it is leaf node
        if(!root.left && !root.right){
            
            return null;
        }else if(!root.left){//if left node is null check right node 
        root=root.right;
        return root;
        }else if(!root.right){
            root=root.left;
            return root;
        }
     
    }
 return root;  //return updated tree;
    
}
deletee(bstroot,18);

```

delete node with 2 child (little complex)









