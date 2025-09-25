# 🌳 Trees in JavaScript – Notes

## 1. What is a Tree?
- A **non-linear hierarchical data structure** consisting of **nodes** connected by edges.
- Each tree has:
  - **Root** → topmost node.
  - **Parent & Child** → direct relationships.
  - **Leaf** → node with no children.
  - **Height** → longest path from root to leaf.

📌 **Why Trees?**
- Efficient for searching & sorting (Binary Search Tree).
- Represent hierarchical structures → e.g., file system, DOM in HTML.

---

## 2. Types of Trees
- **Binary Tree** → each node has at most 2 children.
- **Binary Search Tree (BST)** → left < parent < right.
- **Balanced Trees (AVL, Red-Black Tree)** → keep height small, ensure O(log n).
- **N-ary Tree** → node can have more than 2 children (DOM, XML).

---

## 3. Tree Representation in JS
```js
class Node {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

class BinaryTree {
  constructor() {
    this.root = null;
  }

  insert(value) {
    const newNode = new Node(value);

    if (!this.root) {
      this.root = newNode;
      return;
    }

    let current = this.root;
    while (true) {
      if (value < current.value) {
        if (!current.left) {
          current.left = newNode;
          return;
        }
        current = current.left;
      } else {
        if (!current.right) {
          current.right = newNode;
          return;
        }
        current = current.right;
      }
    }
  }
}

4. Tree Traversals
🔹 Depth First Search (DFS)

Inorder (Left → Root → Right) → gives sorted order in BST.

function inorder(node) {
  if (node !== null) {
    inorder(node.left);
    console.log(node.value);
    inorder(node.right);
  }
}


Preorder (Root → Left → Right) → used for copying a tree.

function preorder(node) {
  if (node !== null) {
    console.log(node.value);
    preorder(node.left);
    preorder(node.right);
  }
}


Postorder (Left → Right → Root) → used for deleting a tree.

function postorder(node) {
  if (node !== null) {
    postorder(node.left);
    postorder(node.right);
    console.log(node.value);
  }
}

🔹 Breadth First Search (BFS)

Level order traversal using a queue.

function bfs(root) {
  if (!root) return;
  let queue = [root];

  while (queue.length) {
    let node = queue.shift();
    console.log(node.value);

    if (node.left) queue.push(node.left);
    if (node.right) queue.push(node.right);
  }
}

5. Complexity
Operation	Average	Worst
Search (BST)	O(log n)	O(n)
Insert (BST)	O(log n)	O(n)
Delete (BST)	O(log n)	O(n)
Traversal (DFS/BFS)	O(n)	O(n)
6. Real-World Examples

DOM Tree Traversal → Browsers represent HTML as a tree.

Autocomplete (Tries) → Efficient word lookups.

Databases (B-Trees, B+ Trees) → Used in indexing.

File System → Directories & files are trees.