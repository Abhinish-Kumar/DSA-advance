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

