# Assignment 6
## Task
1.

| Step | Operation     | Stack Content (Bottom → Top) |
|------|---------------|------------------------------|
| 1    | PUSH(S,4)     | [4]                          | 
| 2    | PUSH(S,1)     | [4, 1]                       | 
| 3    | PUSH(S,3)     | [4, 1, 3]                    |
| 4    | POP(S)        | [4, 1]                       |
| 5    | PUSH(S,8)     | [4, 1, 8]                    |
| 6    | POP(S)        | [4, 1]                       |
2. 

| Step | Operation      | Queue Content (Front → Rear) |
|------|----------------|------------------------------|
| 1    | ENQUEUE(Q,4)   | [4]                          |
| 2    | ENQUEUE(Q,1)   | [4, 1]                       | 
| 3    | ENQUEUE(Q,3)   | [4, 1, 3]                    | 
| 4    | DEQUEUE(Q)     | [1, 3]                       | 
| 5    | ENQUEUE(Q,8)   | [1, 3, 8]                    | 
| 6    | DEQUEUE(Q)     | [3, 8]                       | 

3. Enque(Q,x)
  if NEXT(Q.tail) == Q.head  
    error "overflow"
else
    Q[Q.tail]= x
    if Q.tail == Q.length
        Q.tail = 1
    else
        Q.tail = Q.tail + 1
Deque(Q)
if Q.head == Q.tail  
    error "underflow"
else
    x = Q[Q.head]
    if Q.head == Q.length
        Q.head = 1
    else
        Q.head = Q.head + 1
    return x
4.
A deque is like a queue that works at both ends. With an array and two pointers, you can add or remove items in constant time. To insert at the front, first check if it’s full; if not, move the head one step
back  and put the item there. To insert at the rear, check for overflow, place the item at the tail, then move the tail one step forward. To delete from the front, make sure it’s not empty, take out the item at the head,
and move the head forward. To delete from the rear, check underflow, move the tail one step back, and remove that item. This is ecause each step is just a small pointer move and one assignment. All four operations run in O(1) time
## Link
https://drive.google.com/file/d/1C6ZGyrUbdinMJ0ofKNtT9qGlp72UQzql/view?usp=sharing
