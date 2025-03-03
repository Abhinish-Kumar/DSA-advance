
```javascript
class Graph {
    constructor(numVer) {
        this.adjacencyList = new Map();
    }

    addVertex(vertex) {
        if (!this.adjacencyList.has(vertex)) {
            // If vertex is not present, create it
            this.adjacencyList.set(vertex, []);
        }
    }

    // Add an edge between two vertices
    addEdge(source, dest) {
        // If both vertices exist, connect them
        if (this.adjacencyList.has(source) && this.adjacencyList.has(dest)) {
            this.adjacencyList.get(source).push(dest);
            this.adjacencyList.get(dest).push(source); // for undirected graph
        }
    }

    // Print the graph
    printGraph() {
        for (let [vertex, neighbors] of this.adjacencyList) {
            console.log(`${vertex} -> ${neighbors.join(', ')}`);
        }
    }

    // BFS traversal starting from a given vertex
    bfs(start) {
        let visited = new Set();  // To track visited vertices
        let queue = [start];  // BFS uses a queue
        let result = [];  // To store the order of traversal

        visited.add(start);

        while (queue.length > 0) {
            let vertex = queue.shift(); // Remove the front of the queue
            result.push(vertex);

            // Add all unvisited neighbors of the current vertex to the queue
            for (let neighbor of this.adjacencyList.get(vertex)) {
                if (!visited.has(neighbor)) {
                    visited.add(neighbor);
                    queue.push(neighbor);
                }
            }
        }

        return result;
    }
}

let g = new Graph(5);
g.addVertex(3);
g.addVertex(2);
g.addVertex(4);
g.addVertex(5);
g.addVertex(6);

g.addEdge(3, 2);
g.addEdge(2, 4);
g.addEdge(4, 5);
g.addEdge(5, 6);

console.log("Graph BFS traversal starting from vertex 3:");
let bfsResult = g.bfs(3);
console.log(bfsResult);  // Output will be the BFS traversal result

```
