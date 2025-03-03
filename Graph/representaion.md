```javascript
class Graph{
    constructor(numVer){
        this.numVer=numVer;
        this.adjMatrix=[];
        for(let i=0;i<this.numVer;i++){
             this.adjMatrix[i]=[];
            for(let j=0;j<this.numVer;j++){
                this.adjMatrix[i][j]=0;
            }
        }
    }
    printGraph(){
        for(let i=0;i<this.numVer;i++){
            let newRow=[];
            for(let j=0;j<this.numVer;j++){
               newRow[j]=this.adjMatrix[i][j];
            }
            console.log(newRow);
        }
    }
}


let g=new Graph(5);
console.log(g)
g.printGraph();
```

```javascipt
//output
Graph {
  numVer: 5,
  adjMatrix: [
    [ 0, 0, 0, 0, 0 ],
    [ 0, 0, 0, 0, 0 ],
    [ 0, 0, 0, 0, 0 ],
    [ 0, 0, 0, 0, 0 ],
    [ 0, 0, 0, 0, 0 ]
  ]
}
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
```
