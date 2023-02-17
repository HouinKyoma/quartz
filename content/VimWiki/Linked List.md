# Linked List
- A sequence of elements arranged on after another, with each element connected to the next element by a link
- **node**: data + link to next node
	- End node: we will have some special end mark on the link of the last node


## Declaring class for Nodes
## Head and Tail
## Null Reference
**Java**
Whenever a reference variable is first declared and there is not yet refering to any object, it is assigned `null`.
- Used in final node
- An empty linked list will have `null` points to its **head** and **tail**.
## Manipulating Nodes
#### Constructor for Node
#### Getter and Setter
#### Adding a New Node at the Head
- Change the head to point to the new node
- set the new node's link to the previous head node's address
#### Removing a Node from the Head
```java
head = head.getLink();
```
This single line in java will remove the node from the head
#### Adding a New Node, not from head
- finding the node just before the position you want to insert
- suppose `selection` is a reference to a node of a linked list:
```java
selection.addNodeAfter(element);

link = new IntNode(element, link);
```
#### Removing, not from Head
## Manipulating Entire Linked List
### Length
### Traversal
### Finding a Node
### Copying a Linked List
##### Method 1

##### Method 2
##### Copying Part of List
