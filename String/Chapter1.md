## 1. Reverse a String
Given a string, reverse it without using the built-in `reverse()` method.

```javascript
let str="My name is abhinish";
  let revst="";
 revst[0]="1"
console.log(revst)

//we can not modify string
```

strings in JavaScript are immutable, meaning their characters cannot be changed individually after the string is created. Specifically, the line revst[0] = "1" attempts to modify the first character of revst, but since strings are immutable, you cannot modify a string in this way.

Other ways to modify string in javascript.

```javascript

let revst = "";  // Initialize empty string
revst += "1";  // Append '1' to the empty string
console.log(revst);  // Output will be "1"

```
change character of string at middle 

```javascript
let str = "My name is Abhinish";
let position = Math.floor(str.length / 2); // Find the middle position
let newChar = "X"; // New character to insert

// Insert the new character at the middle position
let result = str.slice(0, position) + newChar + str.slice(position);

console.log(result); // Output: "My name is XAbhinish"

```

```javascript

//final ans with extra space
let str="My name is abhinish";
  let revst="";

  let l=str.length;
for(let i=l-1;i>=0;i--){

revst+=str[i];

}
console.log(revst)
```

```javascript
//without using extra space
//reverse string without i=using built in method

let name="abhinish Kumar";

//you can not modify the string with index so convert it to Array

let arr=name.split("");
console.log(arr);

let f=0;
let l=arr.length-1;

while(f<l){
  [arr[f],arr[l]]=[arr[l],arr[f]];
  f++;
  l--;
}

name=arr.join("");
console.log(name);
```


```javascript
//with method
let name="abhinish";
console.log(name.split("").reverse().join(""));
```







