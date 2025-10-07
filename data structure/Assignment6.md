# Assignment 6
## Task
1.

| Step | Operation     | Stack Content (Bottom → Top) | Top Pointer |
|------|---------------|-------------------------------|-------------|
| 1    | PUSH(S,4)     | [4]                          | Top = 1     |
| 2    | PUSH(S,1)     | [4, 1]                       | Top = 2     |
| 3    | PUSH(S,3)     | [4, 1, 3]                    | Top = 3     |
| 4    | POP(S)        | [4, 1]                       | Top = 2     |
| 5    | PUSH(S,8)     | [4, 1, 8]                    | Top = 3     |
| 6    | POP(S)        | [4, 1]                       | Top = 2     |
2. 

| Step | Operation      | Queue Content (Front → Rear) | Head | Tail |
|------|----------------|-------------------------------|------|------|
| 1    | ENQUEUE(Q,4)   | [4]                          | 1    | 2    |
| 2    | ENQUEUE(Q,1)   | [4, 1]                       | 1    | 3    |
| 3    | ENQUEUE(Q,3)   | [4, 1, 3]                    | 1    | 4    |
| 4    | DEQUEUE(Q)     | [1, 3]                       | 2    | 4    |
| 5    | ENQUEUE(Q,8)   | [1, 3, 8]                    | 2    | 5    |
| 6    | DEQUEUE(Q)     | [3, 8]                       | 3    | 5    |

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
The four O(1)-time procedures to insert elements into and delete elements from both ends of a deque implemented by an array are as follows. INSERT_FRONT which checks for overflow, moves the head one step backward, and places the new element at
Q[head]. INSERT_REAR which checks for overflow, places the new element at Q[tail], and then moves the tail one step forward (wrapping around if needed). DELETE_FRONT which checks for underflow, removes the element at Q[head], and then moves the head
one step forward (wrapping around if needed). DELETE_REAR which checks for underflow, moves the tail one step backward (wrapping around if needed), and removes the element at Q[tail].
## Link
