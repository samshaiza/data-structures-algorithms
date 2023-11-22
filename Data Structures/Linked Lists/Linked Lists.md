#data-structure 

JavaScript [[Arrays]] are **not** arrays (i.e `const a = []`).

Array's kinda suck...
- We can't delete items (we just replace them nothing)
- We can't insert items (we just replace them)
- We can't grow them (their size is fixed on init)

So let's look at Linked Lists, our first "real" data structure

## How do they work?

A linked list is a linear collection of data where each item in the collection points to the next item. We refer to those items as 'nodes.

In a 'singly linked list', a node contains data and a reference to the next node.

In a 'doubly linked list', nodes will also have a reference to the previous node.

![[linked list.png]]

There are no *indexes* in linked lists. We just handle the nodes. 

Inserting into a linked list is O(1).

Deleting an item in a linked list is O(1).
 - We need to point the target's previous node to the target's next node

Setting a value to an item is O(1)