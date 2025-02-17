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


## leetcode 21 merge two sorted List

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} list1
 * @param {ListNode} list2
 * @return {ListNode}
 */
var mergeTwoLists = function(list1, list2) {
    if(!list1) return list2;
    if(!list2) return list1;
    
    let newList=new ListNode(list1.val);
    let current=newList;
    while(list1 && list2){
        if(list1.val<=list2.val){
            current.next=new ListNode(list1.val);
            list1=list1.next;
        }else{
            current.next=new ListNode(list2.val);
            list2=list2.next; 
        }
        current=current.next;
    }

    if(list1){
        current.next=list1;
    }
    if(list2){
        current.next=list2;
    }
return newList.next;
};
```

without extra space

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} list1
 * @param {ListNode} list2
 * @return {ListNode}
 */
var mergeTwoLists = function(list1, list2) {
    if(!list1) return list2;
    if(!list2) return list1;
    
    let newList=new ListNode(list1.val);
    let current=newList;
    while(list1 && list2){
        if(list1.val<=list2.val){
            current.next=list1;
            list1=list1.next;
        }else{
            current.next=list2;
            list2=list2.next; 
        }
        current=current.next;
    }

    if(list1){
        current.next=list1;
    }
    if(list2){
        current.next=list2;
    }
return newList.next;
};
```













