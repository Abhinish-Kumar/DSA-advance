### leetcode 83 remove duplicate 

```javascript
  if(!head) return null;
   let arr=[];
   arr.push(head.val);
   let current=head.next;
   while(current){
    if(arr[arr.length-1]==current.val){
        arr.pop();
        continue;  
    }else if(arr[arr.length-1]!=current.val){
        arr.push(current.val)
    }
     current=current.next;
   }

   current=head;
   let index=0;
   while(index<arr.length){
    current.val=arr[index];
    index++;
    current=current.next;
   }

   let size=arr.length-1;
   current=head;
   while(size){
    current=current.next;
    size--;
   }
   current.next=null;
   return head;
```

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var deleteDuplicates = function(head) {
    if(!head) return null;
  let current=head.next;
  let prev=head;
  while(current){
    if(current.val==prev.val){
        prev.next=current.next;
        current=prev.next;
    }else{
        prev=prev.next;
        current=current.next;
    }
  }
   return head;
};
```
