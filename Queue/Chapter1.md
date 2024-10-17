# Queue


Defination:- A	queue	is	an	ordered	list	in	which	insertions	are	done	at	one	end	(rear)	and
 deletions	are	done	at	other	end	(front).	The	first	element	to	be	inserted	is	the	first	one	to	be
 deleted.	Hence,	it	is	called	First	in	First	out	(FIFO)	or	Last	in	Last	out	(LILO)	list.

 Similar	to	Stacks,	special	names	are	given	to	the	two	changes	that	can	be	made	to	a	queue.	When
 an	element	is	inserted	in	a	queue,	the	concept	is	called	EnQueue,	and	when	an	element	is
 removed	from	the	queue,	the	concept	is	called	DeQueue.

DeQueueing	an	empty	queue	is	called	underflow	and	EnQueuing	an	element	in	a	full	queue	is
 called	overflow. 	Generally,	we	treat	them	as	exceptions.	

 
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20220816162225/Queue.png" />


EnQueue :- New Element ready to enter in Queue.
DeQueue :- Elements ready to be served.



Note :- it is not a physical data structure its a logical data structure or a concept that give us functionality like a real queue with best possible features , that we can use to solve real world problems easily. 

types of queue = https://www.javatpoint.com/ds-types-of-queues
## 	How	are	Queues	Used?

## Queue	ADT
- Basic Possible operations of Queue.
- Insertions	and	deletions	in	the	queue	must
 follow	the	FIFO	scheme.

1.  Main	Queue	Operations
-  EnQueue(int	data):	Inserts	an	element	at	the	end	of	the	queue.
-   int	DeQueue():	Removes	and	returns	the	element	at	the	front	of	the	queue.

2.  Auxiliary	Queue	Operations.
- int	Front():	Returns	the	element	at	the	front	without	removing	it.
-  int	QueueSize():	Returns	the	number	of	elements	stored	in	the	queue.
-  int	IsEmptyQueueQ:	Indicates	whether	no	elements	are	stored	in	the	queue	or	not.

## Exceptions

Similar	to	other	ADTs,	executing	DeQueue	on	an	empty	queue	throws	an **“Empty	Queue Exception”** and	executing	EnQueue	on	a	full	queue	throws	**“Full	Queue	Exception”**.

 ## Applications

### Direct	Application

1. Operating	systems	schedule	jobs	(with	equal	priority)	in the	order	of	arrival	(e.g.,	a print	queue).
2. Simulation	of	real-world	queues	such	as	lines	at	a	ticket	counter	or	any	other	first come	first-served	scenario	requires	a	queue.
3. Multiprogramming.
4. Asynchronous	data	transfer	(file	IO,	pipes,	sockets).
5. Waiting	times	of	customers	at	call	center
6. Determining	number	of	cashiers	to	have	at	a	supermarket.

##  Indirect	Applications

1. Auxiliary	data	structure	for	algorithms.
2.  Component	of	other	data	structures.

1. Simple	circular	array	based	implementation.
2. Dynamic	circular	array	based	implementation.
3. Linked	list	implementation.

# Why	Circular	Arrays?

First lets see the problem with simple array by implementing a queue.


```javascript
class Queue {
  constructor(size = 3) {
    this.f = -1;
    this.r = -1;
    this.size = size;
    this.queue = [];
  }

  add(e) {
    if (this.r == this.size - 1) {
      return "Queue is full";
    }
    if (this.f == -1) {
      this.f = 0;
      this.r = 0;
      this.queue[this.r] = e;
    } else {
      this.r++;
      this.queue[this.r] = e;
    }
    return this.queue;
  }

  remove() {
    if (this.r - this.f < 0) {
      return "No element to remove";
    }
    let x = this.queue[this.f];
    this.f++;
    return x;
  }

  peek() {
    if (this.r - this.f <= 0) {
      return "No element to remove";
    }
    return this.queue[this.f];
  }
  isEmpty() {
    if (this.r - this.f <= 0) {
      return true;
    }
    return false;
  }
  sizze() {
    if (this.f == -1 || this.f == this.r) {
      return "Size is " + 0;
    }
    return "Size is " + Math.floor(this.r - this.f + 1);
  }
}

let x = new Queue(4);
console.log(x.isEmpty()); //true
console.log(x.add(100)); //[100]
console.log(x.add(200)); //[100, 200]
console.log(x.sizze()); //Size is 2
console.log(x.isEmpty()); //false
console.log(x.peek()); //100
console.log(x.add(300)); //[100, 200, 300]
console.log(x.add(400)); //[100, 200, 300, 400]
console.log(x.add(500)); //Queue is full
console.log(x.remove()); //100
console.log(x.remove()); //200
console.log(x.remove()); //300
console.log(x.remove()); //400
console.log(x.add(400)); //Queue is full
console.log(x.isEmpty()); //true
console.log(x.sizze()); //size is 0

```
Problem with array implementation is that we can only use the space only once.
Solution :- Circular queue.


