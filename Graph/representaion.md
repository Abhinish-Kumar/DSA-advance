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
    addEdge(source,dest){
        if(source>=0&&source<this.numVer && dest>=0&&dest<this.numVer){
            this.adjMatrix[source][dest]=1;
            this.adjMatrix[dest][source]=1;
        }
    }
}


let g=new Graph(5);
g.addEdge(3,2);

g.printGraph();
```

```javascript
//add an edge
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 1, 0 ]
[ 0, 0, 1, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
```



## For directed 

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
    addEdge(source,dest){
        if(source>=0&&source<this.numVer && dest>=0&&dest<this.numVer){
            this.adjMatrix[source][dest]=1;
            this.adjMatrix[dest][source]=1;
        }
    }
    
    addEdgeDir(source,dest){
        if(source>=0&&source<this.numVer && dest>=0&&dest<this.numVer){
            this.adjMatrix[source][dest]=1;
        }
    }
    
    
}


let g=new Graph(5);
g.addEdge(3,2);

g.printGraph();
console.log("================")
let dirGraph=new Graph(5);
dirGraph.addEdge(3,2);
dirGraph.printGraph();


```

```javascript
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 1, 0 ]
[ 0, 0, 1, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
================
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 1, 0 ]
[ 0, 0, 1, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
```

## Undirected Weighted

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
    addEdge(source,dest){
        if(source>=0&&source<this.numVer && dest>=0&&dest<this.numVer){
            this.adjMatrix[source][dest]=1;
            this.adjMatrix[dest][source]=1;
        }
    }
    
    addEdgeDir(source,dest){
        if(source>=0&&source<this.numVer && dest>=0&&dest<this.numVer){
            this.adjMatrix[source][dest]=1;
        }
    }
    
    addEdgWeg(source,dest,weight){
        if(source>=0&&source<this.numVer && dest>=0&&dest<this.numVer){
            this.adjMatrix[source][dest]=weight;
            this.adjMatrix[dest][source]=weight;
        }
    }
    
    
}


let g=new Graph(5);
g.addEdge(3,2);

g.printGraph();
console.log("================")
let dirGraph=new Graph(5);
dirGraph.addEdge(3,2);
dirGraph.printGraph();
console.log("================")
let undirWeight=new Graph(5);
undirWeight.addEdgWeg(3,2,500);
undirWeight.printGraph();


```


```javascript
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 1, 0 ]
[ 0, 0, 1, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
================
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 1, 0 ]
[ 0, 0, 1, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
================
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 500, 0 ]
[ 0, 0, 500, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
```

## Directed Weighted Graph



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
    addEdge(source,dest){
        if(source>=0&&source<this.numVer && dest>=0&&dest<this.numVer){
            this.adjMatrix[source][dest]=1;
            this.adjMatrix[dest][source]=1;
        }
    }
    
    addEdgeDir(source,dest){
        if(source>=0&&source<this.numVer && dest>=0&&dest<this.numVer){
            this.adjMatrix[source][dest]=1;
        }
    }
    
    addEdgWeg(source,dest,weight){
        if(source>=0&&source<this.numVer && dest>=0&&dest<this.numVer){
            this.adjMatrix[source][dest]=weight;
            this.adjMatrix[dest][source]=weight;
        }
    }
    addDirWeg(source,dest,weight){
         if(source>=0&&source<this.numVer && dest>=0&&dest<this.numVer){
            this.adjMatrix[source][dest]=weight;
        }
    }
    
}


let g=new Graph(5);
g.addEdge(3,2);

g.printGraph();
console.log("================")
let dirGraph=new Graph(5);
dirGraph.addEdge(3,2);
dirGraph.printGraph();
console.log("================")
let undirWeight=new Graph(5);
undirWeight.addEdgWeg(3,2,500);
undirWeight.printGraph();

console.log("================")
let dirWeg=new Graph(5);
dirWeg.addDirWeg(3,2,500);
dirWeg.printGraph();

```

```javascript
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 1, 0 ]
[ 0, 0, 1, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
================
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 1, 0 ]
[ 0, 0, 1, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
================
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 500, 0 ]
[ 0, 0, 500, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
================
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
[ 0, 0, 500, 0, 0 ]
[ 0, 0, 0, 0, 0 ]
```












