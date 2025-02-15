### Create a BST with given Array  in javascript, java , c++;

Javascript

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

console.log(bstroot)

function insert(root,data){
//base case if root is  null
if(root===null) return  new Node(data);

//if root node exist compare tis value
if(root.data>data){ //move left
//return subtree attach with root.left
root.left= insert(root.left,data);
}else {
//return subtree attach with root.right
root.right= insert(root.right,data);
}
return root; //return updated root
}

```


```javascript
//Output 
Node {
  data: 6,
  left: Node {
    data: 3,
    left: Node { data: 2, left: null, right: null },
    right: Node { data: 5, left: null, right: null }
  },
  right: Node {
    data: 11,
    left: Node { data: 7, left: null, right: null },
    right: Node { data: 18, left: [Node], right: null }
  }
}
```


```javascript
//Tree representaion
        6
       / \
      3   11
     / \  / \
    2  5 7  18
         /
        12

```












