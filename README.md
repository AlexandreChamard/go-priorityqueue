# go-priorityqueue
Implements a generic Priority Queue in Golang (1.18)

# Install

```sh
go get github.com/AlexandreChamard/go-priorityqueue
```

# Examples

```golang
import (
    "github.com/AlexandreChamard/go-priorityqueue"
)

pqueue := priorityqueue.NewPriorityQueue(func(a, b int) bool { return a < b })

n := 10000

for i := n - 1; i >= 0; i-- {
    pqueue.Push(i)
}
for i := 0; i < n; i++ {
    fmt.Println(pqueue)
    if pqueue.Empty() {
        t.Fatalf("%d: pqueue.Empty(): expected %v got %v", i, false, pqueue.Empty())
    }
    if pqueue.Size() != n-i {
        t.Fatalf("%d: pqueue.Size(): expected %d got %d", i, n-i, pqueue.Size())
    }
    if pqueue.Front() != i {
        t.Fatalf("%d: pqueue.Front(): expected %d got %d", i, i, pqueue.Front())
    }
    pqueue.Pop()
}
if !pqueue.Empty() {
    t.Fatalf("pqueue.Empty(): should be empty at the end")
}
```
