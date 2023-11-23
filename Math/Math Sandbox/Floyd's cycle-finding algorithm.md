Floyd's Cycle Finding Algorithm, also known as Floyd's Tortoise and Hare algorithm, is a pointer algorithm that uses two pointers, which move at different speeds, to detect a cycle in a sequence of values. It is often applied in the context of linked lists to determine whether a cycle exists and, if so, to identify the start of the cycle.

### Overview

1. **Two Pointers**: The algorithm uses two pointers, the "tortoise" and the "hare". Initially, both are set to the start of the data structure.
   
2. **Movement**: The "hare" moves twice as fast as the "tortoise". Specifically, the tortoise moves one step at a time, while the hare moves two steps.

3. **Cycle Detection**: If there is a cycle, the hare and tortoise will eventually meet within the cycle. If there is no cycle, the hare will reach the end of the data structure.

4. **Finding the Start of the Cycle**: Once a cycle is detected, one pointer is moved back to the start, and then both move at the same pace. The point at which they meet again is the start of the cycle.

### Algorithm in Detail

1. **Initialization**:
   - Set two pointers, `tortoise` and `hare`, to the head of the list.

2. **Cycle Detection Phase**:
   - While the hare is not at the end of the list:
     - Move the tortoise forward by 1 node.
     - Move the hare forward by 2 nodes.
     - If the hare and tortoise meet, a cycle is detected.

3. **Cycle Start Detection Phase** (only if a cycle is detected):
   - Move the tortoise to the start of the list.
   - Move both the hare and tortoise at the same speed (1 node at a time).
   - The node where they meet again is the start of the cycle.

### Mathematical Representation

Consider a linked list with nodes numbered from $0$ to $N-1$ and a cycle starting at node $k$. Let $d$ be the distance from the head of the list to the start of the cycle, and $c$ be the length of the cycle.

- When the tortoise enters the cycle, it has moved $d$ steps.
- The hare, moving twice as fast, has moved $2d$ steps and is $d$ steps into the cycle.
- They will meet after the hare has made an additional number of steps that is a multiple of $c$ (the cycle length).

### Python Implementation

```python
class ListNode:
    def __init__(self, x):
        self.val = x
        self.next = None

def hasCycle(head):
    if not head or not head.next:
        return False
    
    tortoise, hare = head, head.next
    while hare and hare.next:
        tortoise = tortoise.next
        hare = hare.next.next
        if tortoise == hare:
            return True

    return False

# Function to find the start of the cycle
def detectCycleStart(head):
    if not head or not head.next:
        return None

    tortoise, hare = head, head
    while True:
        tortoise = tortoise.next
        hare = hare.next.next
        if tortoise == hare:
            break

    tortoise = head
    while tortoise != hare:
        tortoise = tortoise.next
        hare = hare.next

    return tortoise
```

This algorithm is elegant in its simplicity and efficiency, requiring no additional memory beyond the two pointers, and operates in linear time complexity, making it a popular choice for cycle detection in linked lists.