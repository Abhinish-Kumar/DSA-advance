
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
