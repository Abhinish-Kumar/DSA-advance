### If found return Node else Not found
Given :- root node and target element


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

```

```javascript
function search(root,target){
if(!root) return "Not found";
if(root.data===target) return root;
if(root.data>target){
return search(root.left,target);
}else {
return search(root.right,target);
}
}

console.log(search(bstroot,3));

```

```javascript
//Output
Node {
  data: 3,
  left: Node { data: 2, left: null, right: null },
  right: Node { data: 5, left: null, right: null }
}
```



