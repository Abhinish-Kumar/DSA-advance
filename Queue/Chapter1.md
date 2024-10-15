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


```

















 
