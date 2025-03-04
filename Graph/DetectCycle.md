```javascript
class Graph {
    constructor(vertices) {
        this.adjList = new Map();  // This will store the graph as an adjacency list.
        this.vertices = vertices;  // Total number of vertices.
    }

    // Add an edge between two vertices (undirected graph)
    addEdge(u, v) {
        if (!this.adjList.has(u)) {
            this.adjList.set(u, []);
        }
        if (!this.adjList.has(v)) {
            this.adjList.set(v, []);
        }

        this.adjList.get(u).push(v);
        this.adjList.get(v).push(u);  // Since it's an undirected graph, add both directions.
    }

    // Helper function to detect a cycle using DFS
    detectCycle(node, parent, visited) {
        visited.add(node);  // Mark the current node as visited

        // Explore all the neighbors (friends) of the current node
        for (let neighbor of this.adjList.get(node)) {
            // Skip the parent node, because we don't want to go back to where we came from.
            if (neighbor === parent) continue;

            // If the neighbor has already been visited, a cycle is detected.
            if (visited.has(neighbor)) return true;

            // Recursively call DFS for the neighbor
            if (this.detectCycle(neighbor, node, visited)) return true;
        }

        return false;  // No cycle detected from this node
    }

    // Function to check if there is a cycle in the graph
    hasCycle() {
        let visited = new Set();  // Use a Set to track visited nodes

        // Call DFS for every unvisited node
        for (let i = 0; i < this.vertices; i++) {
            console.log(this.vertices);//5 vertices
            if (!visited.has(i)) {  // If the node is not visited
                if (this.detectCycle(i, -1, visited)) {
                    return true;  // If a cycle is found, return true
                }
            }
        }
        return false;  // No cycle detected in the graph
    }
}

// Example usage:

// Create a graph with 5 vertices (0, 1, 2, 3, 4)
let g = new Graph(5);

// Add edges to create a graph that will form a cycle
g.addEdge(0, 1);  // 0 - 1
g.addEdge(1, 2);  // 1 - 2
g.addEdge(2, 3);  // 2 - 3
g.addEdge(3, 4);  // 3 - 4
g.addEdge(4, 1);  // 4 - 1 (This creates a cycle)

// Check for a cycle
if (g.hasCycle()) {
    console.log("Graph contains a cycle.");
} else {
    console.log("Graph does not contain a cycle.");
}
```

