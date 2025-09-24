# Containers: LinkedList, DoubleLinkedList, TTree, SmartPtr

## `Alice::LinkedList`
- Singly linked base with `PushBack`, `Remove`, and `Next<T>()`.

## `Alice::DoubleLinkedList`
- Doubly linked node with movement operators `<<` and `>>`, `InsertBefore`, `InsertAfter`, `Append`, and `LeaveList`.

## `Alice::TTree`
- Tree node with `AppendChild`, `InsertBefore`, `InsertAfter`, `RemoveChild`, traversal helpers `LeftSibling<T>`, `RightSibling<T>`, `Child<T>`, `Parent<T>`, `LastChild<T>`.

## `SmartPtr<T>`
- Retain-release smart pointer for objects exposing `retain()` / `release()` (e.g., `Object`-derived types).

### Usage
```cpp
#include "Runtime/Utils/TTree.h"
#include "Runtime/Utils/SmartPtr.h"

class Node : public Alice::TTree { /* ... */ };

void sample() {
    Node* a = new Node();
    Node* b = new Node();
    a->AppendChild(b);

    SmartPtr<Node> hold(b); // calls retain()
    // ...
} 
```
