### How you can check that you have created a  right BST?
Note :- InOrder traversal of BST always gives Sorted result.

```javascript
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

// we have a BST 

```

```javascript
function inOrder(root){
    if(!root){
        return;
    }
    inOrder(root.left);
    console.log(root.data);
    inOrder(root.right)
}

inOrder(bstroot);
```

```javascript
//Output
2
3
5
6
7
11
12
18
```

```javascript
// we have a BST 

insert(bstroot,3);

function inOrder(root){
    if(!root){
        return;
    }
    inOrder(root.left);
    console.log(root.data);
    inOrder(root.right)
}

inOrder(bstroot);
```

```javascript
//with duplicate data
2
3
3
5
6
7
11
12
18

```








