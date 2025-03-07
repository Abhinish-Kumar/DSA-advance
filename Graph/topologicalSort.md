```javascript
class Graph {
  constructor(numVer) {
    this.adjacencyList = new Map(); // stores the adjacency list
  }

  // Add a vertex to the graph
  addVertex(vertex) {
    if (!this.adjacencyList.has(vertex)) {
      this.adjacencyList.set(vertex, []);
    }
  }

  // Add a directed edge from source to dest
  addEdge(source, dest) {
    if (this.adjacencyList.has(source) && this.adjacencyList.has(dest)) {
      this.adjacencyList.get(source).push(dest); // directed edge from source -> dest
    }
  }

  // Add a weighted directed edge
  addEdgeWeight(source, dest, weight) {
    if (this.adjacencyList.has(source) && this.adjacencyList.has(dest)) {
      this.adjacencyList.get(source).push({ vertex: dest, weight }); // directed weighted edge
    }
  }

  // Perform topological sort using Kahn's Algorithm
  topologicalSort() {
    let indegree = new Map(); // stores the indegree of each vertex
    let queue = []; // stores vertices with indegree 0
    let sortedList = []; // stores the result of topological sort

    // Initialize indegree for each vertex to 0
    for (let vertex of this.adjacencyList.keys()) {
      indegree.set(vertex, 0);
    }

    // Calculate indegree of each vertex
    for (let [vertex, neighbors] of this.adjacencyList) {
      for (let neighbor of neighbors) {
        indegree.set(neighbor, indegree.get(neighbor) + 1); // increase indegree for destination vertices
      }
    }

    // Add vertices with indegree 0 to the queue
    for (let [vertex, degree] of indegree) {
      if (degree === 0) {
        queue.push(vertex);
      }
    }

    // Process the graph and build the topological sort
    while (queue.length > 0) {
      let vertex = queue.shift(); // dequeue the vertex
      sortedList.push(vertex); // add to the sorted list

      // Decrease the indegree of adjacent vertices
      for (let neighbor of this.adjacencyList.get(vertex)) {
        let neighborVertex = neighbor;
        indegree.set(neighborVertex, indegree.get(neighborVertex) - 1);

        // If indegree of a neighbor becomes 0, enqueue it
        if (indegree.get(neighborVertex) === 0) {
          queue.push(neighborVertex);
        }
      }
    }

    // If the sorted list contains all vertices, the graph is a DAG and we have a valid topological sort
    if (sortedList.length === this.adjacencyList.size) {
      return sortedList;
    } else {
      console.log("The graph has a cycle, so topological sorting is not possible.");
      return [];
    }
  }

  // Print the graph
  printGraph() {
    for (let [vertex, neighbors] of this.adjacencyList) {
      console.log(`${vertex} -> ${neighbors.map(n => n.vertex ? n.vertex : n).join(', ')}`);
    }
  }
}

// Example usage
let g = new Graph();
g.addVertex(3);
g.addVertex(2);
g.addVertex(1);
g.addVertex(4);
g.addEdge(3, 2);
g.addEdge(2, 1);
g.addEdge(4, 1);

console.log("Topological Sort of the given graph:");
let sorted = g.topologicalSort();
if (sorted.length > 0) {
  console.log(sorted.join(" "));
}

g.printGraph();

```
