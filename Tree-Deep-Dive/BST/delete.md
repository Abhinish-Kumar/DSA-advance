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

if you found the element relace it with the 
1. smallest element at right or
2. larget element at left sub tree

Only then the resultent BST will be a BST



```javascript
//another logic to insert at left os subtree
class Node{
constructor(data=null){
this.data=data;
this.left=null;
this.right=null;
}
}

//create a insertion method to create a tree with given array
let bstroot=null; //create a root node

let arr=[6,3,11,5,7,18,12,2];

for(let i=0;i<arr.length;i++){
bstroot= insert(bstroot,arr[i]);
}


function insert(root,data){
    if(!root) return new Node(data);
    if(root.data<data){
        root.right=insert(root.right,data);
    }else {
         root.left=insert(root.left,data);
    }
    return root;
}



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
        }else{
            //find gratest element from left subtree
            let child=root.left;
            let parent=root;
            //run until you found the right most element 
            while(child.right){
                parent=child;
                child=child.right;
            }
            //we have gratest element as child and its parent 
            //if gratest parent element is not equal to root 
            if(root!=parent){
                parent.right=child.left;// we are going to right but if it has lefft node then connect it to parent 
                child.left=root.left;
                child.right=root.right;
                return child;
            }else{
                child.right=root.right;
                return child;
            }
        }
     
    }
 return root;  //return updated tree;
    
}
deletee(bstroot,3);



console.log(bstroot);

```









