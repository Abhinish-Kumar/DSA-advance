
```javascript
//find the most  frequesncy of a given Array
function frequencyCount(arr){
  let map=new Map();
  for(let i=0;i<arr.length;i++){
    if(map.has(arr[i])){
      map.set(arr[i],map.get(arr[i])+1)
    }else{
       map.set(arr[i],1);
    }
  }
  let maxFreq=-100;
  let keyy=null;
  
for(let [key,value] of map.entries()){
  if(maxFreq<value){
    maxFreq=value;
    keyy=key
  }
}
  return keyy;
}
le.log(frequencyCount([1,3,4,4,2,1,4,4,1])); //4
```

T=O(n)
S=O(n)


With array

```javascript
//find the most  frequesncy of a given Array


function frequencyCount(arr){
  arr=arr.sort((a,b)=>a-b)//you can apply any sorting algorithm with O(nlogn) time complexity
 let count=0;
 let maxFrequency=0;
 for(let i=0;i<arr.length-1;i++){
   if(arr[i]===arr[i+1]){
     count++;
   }else{
     count=1;
   }
   if(maxFrequency<=count){
     maxFrequency=count;
   }
 }
  return maxFrequency;
}


console.log(frequencyCount([1,1,1,1,1,3,3,3,3,3,3,3,3,3,3,2,2,2,2,2,2,2,2]));
```
T = O(nlogn +n)
S = O(1)

