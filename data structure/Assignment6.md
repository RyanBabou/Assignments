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

3.
   ENQUEUE(Q, x)
if ( (Q.tail + 1) % Q.length == Q.head )
    error "overflow"
else
    Q[Q.tail] = x
    Q.tail = (Q.tail % Q.length) + 1

DEQUEUE(Q)
if (Q.head == Q.tail)
    error "underflow"
else
    x = Q[Q.head]
    Q.head = (Q.head % Q.length) + 1
    return x
4. 
INSERT_FRONT(D, x)
if ( (head - 1 + D.length) % D.length == tail )
    error "overflow"
else
    head = (head - 1 + D.length) % D.length
    D[head] = x

INSERT_BACK(D, x)
if ( (tail + 1) % D.length == head )
    error "overflow"
else
    D[tail] = x
    tail = (tail + 1) % D.length

DELETE_FRONT(D)
if (head == tail)
    error "underflow"
else
    x = D[head]
    head = (head + 1) % D.length
    return x

DELETE_BACK(D)
if (head == tail)
    error "underflow"
else
    tail = (tail - 1 + D.length) % D.length
    x = D[tail]
    return x

## Link
