
#Chapter 1

### **1940s: Who First Conceptualized the Queue?**  
**Alan Turing** (the father of modern computing) introduced the **"First-In-First-Out" (FIFO)** principle while working on early computing systems during **World War II**.  

<img src="https://th.bing.com/th/id/OIP.AnirGjFqZalCkNUKw-oDTQHaEK?rs=1&pid=ImgDetMain" />

---

### **🔍 Problem Turing Wanted to Solve:**  
During WWII, **electromechanical machines** (like the Bombe and Colossus) were used to decrypt enemy communications. These machines had to:  
1. **Process multiple tasks** (decryption jobs, calculations, etc.).  
2. **Manage limited memory & resources** efficiently.  
3. **Ensure fairness**—no task should get stuck indefinitely.  

❌ **Without a Queue:**  
- Tasks could get **lost or delayed**.  
- Important messages might **wait too long** while less critical ones got processed.  
- Machines would **waste time** deciding what to compute next.  

---

### **💡 Turing’s Solution: The FIFO Queue**  
He proposed:  
1. **Tasks enter from one end (Rear)** and **exit from the other (Front)**.  
2. **Order matters**: The first task submitted is the first one processed.  
3. **No starvation**: Every task eventually gets its turn.  

**Example:**  
Imagine a **wartime message center**:  
- **Message 1** (Urgent: "Enemy movement at Normandy") → **Processed FIRST**.  
- **Message 2** (Routine: "Supplies delayed") → **Processed NEXT**.  

If processed out of order, soldiers could get **wrong intelligence**!  

---

### **⚙️ Why FIFO Worked for Early Computers:**  
1. **Simplicity**: Easy to implement in mechanical systems.  
2. **Predictability**: Engineers knew **exactly** which task would run next.  
3. **Fairness**: No task could "cut the line."  

*(Fun Fact: This same logic later became the backbone of **CPU scheduling** in operating systems!)*  

---

### **🚀 Legacy of Turing’s Queue:**  
- **Modern OS** (Windows, Linux) use queues for:  
  - **Printer jobs**  
  - **Network packet handling**  
- **Every app you use** (WhatsApp, YouTube) relies on queues to manage requests.  


"अगर Turing ने Queue नहीं बनाई होती, तो आज आपका **WhatsApp message** भी सही ऑर्डर में नहीं आता! 


# Chapter 2 

### **Who Created the First Queue Data Structure?**  
The concept of a **queue** as a data structure was **formalized in the 1950s–60s** during early computer science research, but its **first practical implementation** is credited to:  

#### **🔹 Creator:**  
**Alan Turing** (1940s) – Proposed the **FIFO (First-In-First-Out)** principle for task scheduling in early computers.  
**Donald Knuth** (1960s) – Later formalized queues in his book *"The Art of Computer Programming"* (1968).  

#### **🔹 First Programming Language with Queues:**  
- **Assembly Language (1940s–50s)** – Early computers manually managed queues in machine code.  
- **FORTRAN (1957)** – One of the first high-level languages to support queue-like structures via arrays.  
- **ALGOL (1958)** – Introduced more structured data handling, influencing later queue implementations.  

#### **🔹 First Explicit Queue Implementation:**  
- **1960s (IBM’s PL/I language)** – One of the earliest languages with built-in queue support.  
- **1972 (C language)** – Queues became widely used via **linked lists** and **arrays** (thanks to Dennis Ritchie).  

---

### **📜 Timeline of Queue Evolution**  
| **Year** | **Milestone** | **Language/System** |  
|----------|--------------|---------------------|  
| **1940s** | Turing’s FIFO concept | Theoretical (no code) |  
| **1957** | Arrays used as queues | FORTRAN |  
| **1960** | Queue formalized in algorithms | Knuth’s papers |  
| **1964** | PL/I introduces queue structures | IBM’s PL/I |  
| **1972** | Queue in C (linked lists) | C Language |  
| **1980s** | Standard libraries (C++, Java) | OOP Languages |  

---



# Chapter 3

# Types of Queues and Their Applications

Queues are fundamental data structures that follow the First-In-First-Out (FIFO) principle. There are several specialized types of queues, each designed to solve specific problems efficiently. Here are the main types:

## 1. **Simple Queue (Linear Queue)**
   - **Structure**: Basic FIFO structure with front and rear pointers
   - **Operations**: Enqueue at rear, dequeue at front
   - **Why needed**: Most basic queue implementation for straightforward FIFO processing
   - **Use cases**: Printer task scheduling, call center systems

## 2. **Circular Queue**
   - **Structure**: Rear connects back to the front forming a circle
   - **Operations**: Enqueue and dequeue with modulo arithmetic
   - **Why needed**: Solves the space wastage problem in linear queues
   - **Use cases**: Memory management, traffic systems, CPU scheduling

## 3. **Priority Queue**
   - **Structure**: Elements have associated priorities
   - **Operations**: Dequeue removes highest priority element first
   - **Why needed**: When processing order depends on priority rather than arrival time
   - **Use cases**: Hospital emergency rooms, operating system process scheduling

## 4. **Double-Ended Queue (Deque)**
   - **Structure**: Allows insertion and removal at both ends
   - **Operations**: AddFront, addRear, removeFront, removeRear
   - **Why needed**: When flexibility to add/remove from either end is required
   - **Use cases**: Undo-redo operations, browser history, job stealing algorithms

## 5. **Blocking Queue**
   - **Structure**: Thread-safe queue that blocks when empty or full
   - **Operations**: Blocking enqueue/dequeue operations
   - **Why needed**: For safe inter-thread communication
   - **Use cases**: Producer-consumer problems, message passing systems

## 6. **Bounded Queue**
   - **Structure**: Queue with fixed capacity
   - **Operations**: Enqueue fails when queue is full
   - **Why needed**: To prevent resource exhaustion
   - **Use cases**: Systems with limited memory/resources

## 7. **Concurrent Queue**
   - **Structure**: Thread-safe implementation for parallel access
   - **Operations**: Atomic enqueue/dequeue operations
   - **Why needed**: For multi-threaded environments
   - **Use cases**: Multi-core processing, parallel algorithms

Each queue type addresses specific requirements in computing systems, from basic ordering to complex priority handling and concurrency control.



# Chapter 4 

# **The Simple Queue: A Masterclass in FIFO Magic**

## **🌌 The Birth of the Queue Concept**
The linear queue was **first formalized by Alan Turing** in the 1940s while working on early computing systems. But it was **Donald Knuth** in *"The Art of Computer Programming" (1968)* who gave it a proper data structure identity.  

**Why?** Because computers needed a **fair, ordered way** to handle tasks—just like humans stand in line at a ticket counter!  

---

## **⚡ The Simple Queue: Structure & Operations**
### **🔧 Structure**
```javascript
class Queue {
    constructor() {
        this.items = [];  // Stores elements
        this.front = 0;   // Points to the front element
        this.rear = -1;   // Points to the rear element (starts at -1 when empty)
    }
}
```

### **🚀 Core Operations**
#### **1. `enqueue(item)` → Adds to the rear**
```javascript
enqueue(item) {
    this.rear++;
    this.items[this.rear] = item;
}
```
**What happens?**  
- `rear` moves forward.  
- New item is placed at the end.  

#### **2. `dequeue()` → Removes from the front**
```javascript
dequeue() {
    if (this.isEmpty()) return "Queue is empty!";
    const item = this.items[this.front];
    this.front++;
    return item;
}
```
**What happens?**  
- `front` moves forward.  
- The oldest item is returned.  

#### **3. `isEmpty()` → Checks if empty**
```javascript
isEmpty() {
    return this.front > this.rear;
}
```
**Why?**  
- If `front` surpasses `rear`, the queue is empty.  

#### **4. `peek()` → See the front element**
```javascript
peek() {
    if (this.isEmpty()) return "Queue is empty!";
    return this.items[this.front];
}
```

---

## **🔥 3 Real-World Uses (With Code!)**
### **1. Printer Task Scheduling 🖨️**
**Problem:** Multiple print requests arrive. How to ensure fairness?  
**Solution:** A queue processes them in order.  

```javascript
const printerQueue = new Queue();
printerQueue.enqueue("Resume.pdf");
printerQueue.enqueue("Thesis.docx");
printerQueue.enqueue("Photo.jpg");

while (!printerQueue.isEmpty()) {
    console.log(`Printing: ${printerQueue.dequeue()}`);
}
// Output: 
// Printing: Resume.pdf  
// Printing: Thesis.docx  
// Printing: Photo.jpg
```

### **2. Call Center Systems 📞**
**Problem:** Calls come in faster than agents can handle.  
**Solution:** A queue holds callers until an agent is free.  

```javascript
const callQueue = new Queue();
callQueue.enqueue("Caller #1");
callQueue.enqueue("Caller #2");

// Agent takes the next call
function takeCall() {
    if (!callQueue.isEmpty()) {
        console.log(`Connecting: ${callQueue.dequeue()}`);
    } else {
        console.log("No calls waiting.");
    }
}

takeCall(); // "Connecting: Caller #1"
takeCall(); // "Connecting: Caller #2"
takeCall(); // "No calls waiting."
```

### **3. Breadth-First Search (BFS) in Graphs 🌐**
**Problem:** How to explore a graph level by level?  
**Solution:** A queue tracks nodes to visit next.  

```javascript
function BFS(graph, startNode) {
    const queue = new Queue();
    const visited = new Set();
    
    queue.enqueue(startNode);
    visited.add(startNode);

    while (!queue.isEmpty()) {
        const current = queue.dequeue();
        console.log(`Visited: ${current}`);

        for (const neighbor of graph[current]) {
            if (!visited.has(neighbor)) {
                visited.add(neighbor);
                queue.enqueue(neighbor);
            }
        }
    }
}

const graph = {
    'A': ['B', 'C'],
    'B': ['D'],
    'C': ['E'],
    'D': [],
    'E': []
};

BFS(graph, 'A');
// Output: A → B → C → D → E (Level-order traversal!)
```

---

## **💡 Why This Matters**
- **Fairness:** Ensures first-come, first-served order.  
- **Efficiency:** O(1) for enqueue/dequeue (if implemented well).  
- **Foundation:** Used in **OS scheduling, networking, algorithms (BFS), and more!**  

---

## **🚀 Pro Tips & Common Mistakes**
✅ **Use a Circular Queue** if you want to reuse empty spaces.  
✅ **Linked List-based Queues** avoid shifting elements.  

❌ **Mistake:** Not checking `isEmpty()` before `dequeue()` → **Crash!**  
❌ **Mistake:** Using an array without tracking `front` & `rear` → **Wastes memory!**  

---

## **🎯 Final Verdict**
The **Simple Queue is the unsung hero of computing**—silently managing tasks, calls, and even graph traversals. **Every programmer must master it!**  


# Chapter 5

# **Circular Queue: The Infinite Loop of Efficiency**  

## **🌌 The Birth of the Circular Queue**  
Linear queues have a **fatal flaw**: When you `dequeue`, the front space becomes **unusable forever** (imagine a printer that can’t reuse empty paper slots!).  

**Solution?**  
- **1962:** **Edsger Dijkstra** (yes, the Dijkstra’s Algorithm guy!) proposed **circular buffering** for efficient memory use.  
- **1970s:** Became a standard in **OS kernels** (like Unix) for process scheduling.  

**Why?** Because computers needed a way to **reuse empty spaces** without shuffling data.  

---

## **⚡ Structure: A Ring of Power**  
A **circular queue** uses a **fixed-size array** but connects the **rear** back to the **front** like a ring.  

```javascript
class CircularQueue {
    constructor(size) {
        this.items = new Array(size);
        this.front = -1;  // Empty queue starts at -1
        this.rear = -1;
        this.size = size;
    }
}
```
**Key Insight:**  
- **No wastage:** When `rear` hits the end, it loops back to `0`.  
- **Modulo arithmetic (`%`)** makes it circular.  

---

## **🚀 Core Operations (With Genius Modulo Math)**  
### **1. `enqueue(item)` → Adds to the rear**  
```javascript
enqueue(item) {
    if (this.isFull()) return "Queue is full!";
    
    if (this.front === -1) this.front = 0;  // First element?
    this.rear = (this.rear + 1) % this.size;  // Wrap around!
    this.items[this.rear] = item;
}
```
**What happens?**  
- If `rear` is at **end**, `(rear + 1) % size = 0` → jumps to start!  
- Example: `size=3`, `rear=2` → Next `rear = (2+1)%3 = 0`.  

### **2. `dequeue()` → Removes from the front**  
```javascript
dequeue() {
    if (this.isEmpty()) return "Queue is empty!";
    
    const item = this.items[this.front];
    if (this.front === this.rear) {
        this.front = -1;  // Reset if last element
        this.rear = -1;
    } else {
        this.front = (this.front + 1) % this.size;  // Wrap front too!
    }
    return item;
}
```
**What happens?**  
- `front` moves forward **in a circle**.  
- If `front` hits `rear`, the queue is empty.  

### **3. `isFull()` → Checks if full**  
```javascript
isFull() {
    return (this.rear + 1) % this.size === this.front;
}
```
**Logic:**  
- If `rear + 1` circles back to `front`, the queue is full.  

### **4. `isEmpty()` → Checks if empty**  
```javascript
isEmpty() {
    return this.front === -1;
}
```

---

## **🔥 3 Real-World Uses (With Code!)**  
### **1. CPU Task Scheduling 🖥️**  
**Problem:** OS needs to **cycle through processes** fairly without wasting memory.  
**Solution:** Circular queue in **round-robin scheduling**.  

```javascript
const taskQueue = new CircularQueue(3);
taskQueue.enqueue("Chrome");
taskQueue.enqueue("VS Code");
taskQueue.enqueue("Spotify");

// CPU cycles through tasks endlessly
setInterval(() => {
    const task = taskQueue.dequeue();
    console.log(`Running: ${task}`);
    taskQueue.enqueue(task);  // Re-add to the queue
}, 1000);

// Output: "Running: Chrome" → "VS Code" → "Spotify" → "Chrome" → ...
```

### **2. Traffic Light Systems 🚦**  
**Problem:** Lights must **cycle** (Green → Yellow → Red → Green...).  
**Solution:** Circular queue ensures **no infinite waits**.  

```javascript
const trafficLights = new CircularQueue(3);
trafficLights.enqueue("🟢 Green");
trafficLights.enqueue("🟡 Yellow");
trafficLights.enqueue("🔴 Red");

function changeLight() {
    const light = trafficLights.dequeue();
    console.log(light);
    trafficLights.enqueue(light);  // Loop forever
    setTimeout(changeLight, 3000);
}
changeLight();
// Output: 🟢 → 🟡 → 🔴 → 🟢 → 🟡 → ...
```

### **3. Music Playlist Looping 🎵**  
**Problem:** Spotify needs to **loop songs** without reallocating memory.  
**Solution:** Circular queue for **efficient playlist cycling**.  

```javascript
const playlist = new CircularQueue(3);
playlist.enqueue("Blinding Lights");
playlist.enqueue("Save Your Tears");
playlist.enqueue("Starboy");

function playNext() {
    const song = playlist.dequeue();
    console.log(`🎶 Now playing: ${song}`);
    playlist.enqueue(song);  // Requeue for looping
    setTimeout(playNext, 2000);
}
playNext();
// Output: "Blinding Lights" → "Save Your Tears" → "Starboy" → "Blinding Lights" → ...
```

---

## **💡 Why Circular Queues Are Genius**  
✅ **No Wasted Space:** Reuses empty slots (unlike linear queues).  
✅ **O(1) Operations:** Enqueue/dequeue are **constant time**.  
✅ **Perfect for Hardware:** Used in **buffers (keyboard, network packets)**.  

---

## **🚨 Common Mistakes**  
❌ **Forgetting Modulo:** `rear = (rear + 1) % size` is the **magic line**.  
❌ **Not Resetting on Empty:** If `front === rear`, set both to `-1`.  
❌ **Off-by-One Errors:** `isFull` checks `(rear + 1) % size === front`.  

---

## **🎯 Final Wisdom**  
> "A circular queue is like a **merry-go-round**—no matter how many times you go, you always come back to where you started, efficiently!"  



# Chapter7


# **Priority Queue: The VIP Lane of Data Structures**  

## **🌌 The Birth of Priority Queues**  
Priority queues were **first formalized in 1964** by **Charles Antony Richard Hoare** (the creator of **Quicksort**) while working on **operating system scheduling**.  

**Why?** Because not all tasks are equal—some need **urgent attention** (like a heart attack patient in an ER or a system-critical OS process).  

---

## **⚡ Structure: Priority Meets Order**  
A priority queue can be implemented in **2 ways**:  
1. **Unsorted List** (Simple but slow).  
2. **Heap** (Fast—O(log n) for insert/extract).  

### **🔧 Best Implementation: Binary Heap**  
```javascript
class PriorityQueue {
    constructor() {
        this.heap = [];
    }
}
```
**Key Insight:**  
- **Highest priority** is always at the **root** (index `0`).  
- **Insertion/Extraction** rebalances the heap.  

---

## **🚀 Core Operations**  
### **1. `enqueue(item, priority)` → Insert with Priority**  
```javascript
enqueue(item, priority) {
    const node = { item, priority };
    this.heap.push(node);
    this.#bubbleUp(this.heap.length - 1);
}

#bubbleUp(index) {
    while (index > 0) {
        const parentIndex = Math.floor((index - 1) / 2);
        if (this.heap[parentIndex].priority >= this.heap[index].priority) break;
        [this.heap[parentIndex], this.heap[index]] = [this.heap[index], this.heap[parentIndex]];
        index = parentIndex;
    }
}
```
**What happens?**  
1. New node is **added to the end**.  
2. **"Bubbles up"** until its priority is respected.  

### **2. `dequeue()` → Extract Highest Priority**  
```javascript
dequeue() {
    if (this.heap.length === 0) return null;
    const max = this.heap[0];
    const end = this.heap.pop();
    if (this.heap.length > 0) {
        this.heap[0] = end;
        this.#sinkDown(0);
    }
    return max.item;
}

#sinkDown(index) {
    const leftChild = 2 * index + 1;
    const rightChild = 2 * index + 2;
    let largest = index;

    if (leftChild < this.heap.length && this.heap[leftChild].priority > this.heap[largest].priority) {
        largest = leftChild;
    }
    if (rightChild < this.heap.length && this.heap[rightChild].priority > this.heap[largest].priority) {
        largest = rightChild;
    }
    if (largest !== index) {
        [this.heap[index], this.heap[largest]] = [this.heap[largest], this.heap[index]];
        this.#sinkDown(largest);
    }
}
```
**What happens?**  
1. **Root (highest priority)** is extracted.  
2. **Last node moves to root** and **"sinks down"** to its correct position.  

---

## **🔥 3 Real-World Uses (With Code!)**  
### **1. Hospital Emergency Room 🏥**  
**Problem:** Patients arrive with **different urgency levels** (e.g., heart attack vs. flu).  
**Solution:** Priority queue processes **most critical first**.  

```javascript
const ER = new PriorityQueue();
ER.enqueue("Flu patient", 1);
ER.enqueue("Broken arm", 2);
ER.enqueue("Heart attack", 5); // Highest priority!

console.log(ER.dequeue()); // "Heart attack"
console.log(ER.dequeue()); // "Broken arm"
console.log(ER.dequeue()); // "Flu patient"
```

### **2. OS Process Scheduling 💻**  
**Problem:** The CPU must prioritize **system processes** over background tasks.  
**Solution:** Priority queue schedules **high-priority tasks first**.  

```javascript
const osQueue = new PriorityQueue();
osQueue.enqueue("Background backup", 1);
osQueue.enqueue("User app", 2);
osQueue.enqueue("Kernel process", 10); // Critical!

setInterval(() => {
    const task = osQueue.dequeue();
    if (task) console.log(`Running: ${task}`);
}, 1000);
// Output: "Kernel process" → "User app" → "Background backup"
```

### **3. Traffic Management (Ambulance Clearing Traffic) 🚑**  
**Problem:** Emergency vehicles need **priority at traffic lights**.  
**Solution:** Priority queue forces lights to **turn green for ambulances**.  

```javascript
const trafficQueue = new PriorityQueue();
trafficQueue.enqueue("Regular car", 1);
trafficQueue.enqueue("Bus", 2);
trafficQueue.enqueue("Ambulance", 10); // Top priority!

function changeSignal() {
    const vehicle = trafficQueue.dequeue();
    console.log(vehicle ? `🚦 Green for: ${vehicle}` : "No vehicles");
    if (vehicle) trafficQueue.enqueue(vehicle, vehicle.includes("Ambulance") ? 10 : 1);
    setTimeout(changeSignal, 2000);
}
changeSignal();
// Output: "Ambulance" → "Bus" → "Regular car" → "Ambulance" → ...
```

---

## **💡 Why Priority Queues Are Game-Changers**  
✅ **Urgency Handling:** Critical tasks **skip the line**.  
✅ **Efficient:** Heaps ensure **O(log n)** operations.  
✅ **Versatile:** Used in **AI (A* search), networking (QoS), and more**.  

---

## **🚨 Common Mistakes**  
❌ **Using Unsorted Arrays:** Leads to **O(n) searches** for max priority.  
❌ **Forgetting Heap Rebalancing:** Causes **incorrect priorities**.  
❌ **Priority Inversion:** Low-priority tasks **blocking high-priority ones**.  

---

## **🎯 Final Wisdom**  
> "A priority queue is like a **bouncer at a club**—VIPs get in first, no matter when they arrived!"
> 


# Chapter 7

# **Double-Ended Queue (Deque): The Two-Way Powerhouse**  

## **🌌 The Birth of the Deque**  
The **deque (pronounced "deck")** was first introduced in **1960-1970** as a **generalization of stacks and queues**.  
- **Early Use:** LISP programming language (1960s) used deque-like structures.  
- **Formalized By:** Donald Knuth in *"The Art of Computer Programming" (1968)*.  

**Why?** Because sometimes, **you need to push/pop from both ends**—like a **double-sided line** at a theme park’s express pass!  

---

## **⚡ Structure: A Double-Headed Beast**  
A deque can be implemented using:  
1. **Doubly Linked List** (Best for dynamic resizing).  
2. **Circular Array** (Efficient memory usage).  

### **🔧 JavaScript Implementation (Doubly Linked List)**  
```javascript
class Node {
    constructor(value) {
        this.value = value;
        this.next = null;
        this.prev = null;
    }
}

class Deque {
    constructor() {
        this.front = null;
        this.rear = null;
        this.size = 0;
    }
}
```

---

## **🚀 Core Operations (Flexibility Unleashed!)**  
### **1. `addFront(item)` → Insert at Front**  
```javascript
addFront(item) {
    const newNode = new Node(item);
    if (!this.front) {
        this.front = this.rear = newNode;
    } else {
        newNode.next = this.front;
        this.front.prev = newNode;
        this.front = newNode;
    }
    this.size++;
}
```
**What happens?**  
- New node becomes the **new front**.  
- Old front’s `prev` points to it.  

### **2. `addRear(item)` → Insert at End**  
```javascript
addRear(item) {
    const newNode = new Node(item);
    if (!this.rear) {
        this.front = this.rear = newNode;
    } else {
        newNode.prev = this.rear;
        this.rear.next = newNode;
        this.rear = newNode;
    }
    this.size++;
}
```
**What happens?**  
- New node becomes the **new rear**.  
- Old rear’s `next` points to it.  

### **3. `removeFront()` → Delete from Front**  
```javascript
removeFront() {
    if (!this.front) return null;
    const removed = this.front;
    this.front = this.front.next;
    if (this.front) this.front.prev = null;
    else this.rear = null; // Queue is now empty
    this.size--;
    return removed.value;
}
```
**What happens?**  
- **Front node** is removed.  
- Next node becomes the **new front**.  

### **4. `removeRear()` → Delete from End**  
```javascript
removeRear() {
    if (!this.rear) return null;
    const removed = this.rear;
    this.rear = this.rear.prev;
    if (this.rear) this.rear.next = null;
    else this.front = null; // Queue is now empty
    this.size--;
    return removed.value;
}
```
**What happens?**  
- **Rear node** is removed.  
- Previous node becomes the **new rear**.  

---

## **🔥 3 Real-World Uses (With Code!)**  
### **1. Undo-Redo Operations in Text Editors ✏️**  
**Problem:** Users need to **undo/redo** actions in any order.  
**Solution:** Deque stores history (front = newest, rear = oldest).  

```javascript
const history = new Deque();
history.addFront("Type 'Hello'");
history.addFront("Bold text");
history.addFront("Italicize");

// Undo = removeFront()
console.log(`Undo: ${history.removeFront()}`); // "Italicize"
console.log(`Undo: ${history.removeFront()}`); // "Bold text"

// Redo = addFront()
history.addFront("Bold text");
console.log(`Redo: Bold text added back!`);
```

### **2. Browser History Navigation 🌐**  
**Problem:** Users **go back/forward** in their browsing history.  
**Solution:** Deque tracks pages (front = current, rear = oldest).  

```javascript
const browserHistory = new Deque();
browserHistory.addFront("Google");
browserHistory.addFront("YouTube");
browserHistory.addFront("GitHub");

// Click "Back" button = removeFront()
console.log(`Back to: ${browserHistory.removeFront()}`); // "GitHub" → "YouTube"

// Click "Forward" = addFront()
browserHistory.addFront("GitHub");
console.log(`Forward to: GitHub`);
```

### **3. Job Stealing Algorithms (Parallel Computing) ⚡**  
**Problem:** In multi-threaded systems, idle threads **steal tasks** from others.  
**Solution:** Each thread has a **deque** (front = local tasks, rear = stealable tasks).  

```javascript
class Thread {
    constructor() {
        this.taskDeque = new Deque();
    }

    addLocalTask(task) {
        this.taskDeque.addFront(task); // Local tasks go at front
    }

    stealTask() {
        return this.taskDeque.removeRear(); // Others steal from rear
    }
}

const threadA = new Thread();
threadA.addLocalTask("Task 1");
threadA.addLocalTask("Task 2");

const threadB = new Thread();
threadB.addLocalTask("Task 3");

// Thread B steals from Thread A
console.log(`Stolen task: ${threadA.stealTask()}`); // "Task 1"
```

---

## **💡 Why Deques Are Revolutionary**  
✅ **Ultimate Flexibility:** Insert/delete from **both ends in O(1)**.  
✅ **Hybrid Power:** Combines **stack (LIFO) + queue (FIFO)**.  
✅ **Memory Efficient:** No shifting elements (unlike arrays).  

---

## **🚨 Common Mistakes**  
❌ **Not Updating Both `prev` and `next`** → Breaks links.  
❌ **Forgetting Edge Cases** (Empty deque, single-node deque).  
❌ **Using Arrays** → `removeFront` becomes **O(n)** due to shifting.  

---

## **🎯 Final Wisdom**  
> "A deque is like a **double-door fridge**—you can grab snacks from either side without moving everything around!"  


# Chapter 8
























