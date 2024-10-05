### 1. Print natural number from 1 to n

```javascript
function increadingOder(n){
//base case
if(n===1){
console.log(n);
return
}

increadingOder(n-1);
console.log(n)
}

increadingOder(5) //1 2 3 4 5
```

```javascript
function decreasingOrder(n){
//base case
if(n===1){
console.log(n);
return
}
console.log(n)
decreasingOrder(n-1);
}

decreasingOrder(5) //5 4 3 2 1
```


### 2. Factorial of n!

```javascript

//5! = 5*4*3*2*!
function factorial(n){
if(n===1){
return 1;
}
return n*factorial(n-1)
}
console.log(factorial(5)); //120

```

### 3. Nth Fibonaci series print 

```javascript
//add pre and preprev
//0 1 1 2 3 5 8 13

function fibonaci(n){
//base case
if(n===0||n===1){
return n
}
return fibonaci(n-1)+fibonaci(n-2);
}

console.log(fibonaci(5))//5
console.log(fibonaci(6))//8
```


### 3. N Fibonaci series print 

```javascript
//add pre and preprev
//0 1 1 2 3 5 8 13

function fibonaci(n){
//base case
if(n===0||n===1){
return n
}
return fibonaci(n-1)+fibonaci(n-2);
}

let n=8;
for (let i = 0; i < n; i++) {
console.log(fibonaci(i))  // 0 1 1 2 3 5 8 13
}
```









