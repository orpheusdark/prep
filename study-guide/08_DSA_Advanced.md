# 📁 FOLDER 08 — DSA ADVANCED 🟡 MEDIUM PRIORITY

## Covers: Trees · Graphs (BFS/DFS) · Dynamic Programming · Binary Search Advanced

---

## SECTION A: TREES ⭐

### Concept Overview

```
Binary Tree:       BST:
      1             4
     / \           / \
    2   3         2   6
   / \           / \
  4   5         1   3
```

| Term | Meaning |
|------|---------|
| Binary Tree | Each node has at most 2 children |
| BST | Binary Search Tree: left < root < right |
| Height | Longest path from root to leaf |
| Balanced tree | Height difference of left/right subtrees ≤ 1 |

---

### Q1. Tree Traversals ⭐ 🔥

```java
// Preorder: Root → Left → Right
void preorder(TreeNode node) {
  if (node == null) return;
  System.out.print(node.val + " ");
  preorder(node.left);
  preorder(node.right);
}

// Inorder: Left → Root → Right (gives SORTED order for BST!)
void inorder(TreeNode node) {
  if (node == null) return;
  inorder(node.left);
  System.out.print(node.val + " ");
  inorder(node.right);
}

// Postorder: Left → Right → Root
void postorder(TreeNode node) {
  if (node == null) return;
  postorder(node.left);
  postorder(node.right);
  System.out.print(node.val + " ");
}

// Level-order (BFS)
void levelOrder(TreeNode root) {
  Queue<TreeNode> q = new LinkedList<>();
  q.offer(root);
  while (!q.isEmpty()) {
    TreeNode node = q.poll();
    System.out.print(node.val + " ");
    if (node.left != null) q.offer(node.left);
    if (node.right != null) q.offer(node.right);
  }
}
```

**🧠 Remember:**
- Pre = Root **Pre**fix (root first)
- In = Root **In** middle (left, root, right)
- Post = Root **Post** (root last)
- Inorder of BST = sorted output!

---

### Q2. Find Height of Binary Tree ⭐
```java
int height(TreeNode root) {
  if (root == null) return 0;
  return 1 + Math.max(height(root.left), height(root.right));
}
```

---

### Q3. Check if Tree is Balanced
```java
boolean isBalanced(TreeNode root) {
  return checkHeight(root) != -1;
}
int checkHeight(TreeNode node) {
  if (node == null) return 0;
  int left = checkHeight(node.left);
  int right = checkHeight(node.right);
  if (left == -1 || right == -1) return -1;
  if (Math.abs(left - right) > 1) return -1;
  return 1 + Math.max(left, right);
}
```

---

### Q4. Lowest Common Ancestor (LCA) ⭐
```java
TreeNode lca(TreeNode root, TreeNode p, TreeNode q) {
  if (root == null || root == p || root == q) return root;
  TreeNode left = lca(root.left, p, q);
  TreeNode right = lca(root.right, p, q);
  if (left != null && right != null) return root; // p and q on different sides
  return left != null ? left : right;
}
```

---

## SECTION B: GRAPHS ⭐

### Concept Overview

- **Graph:** Collection of nodes (vertices) connected by edges
- **Directed:** Edges have direction (A→B)
- **Undirected:** Edges are bidirectional
- **Weighted:** Edges have costs
- **Representation:** Adjacency list (most common) or adjacency matrix

---

### Q5. BFS vs DFS ⭐ 🔥

| Feature | BFS | DFS |
|---------|-----|-----|
| Data structure | **Queue** | **Stack** (or recursion) |
| Order | Level by level | Go deep first |
| Use case | **Shortest path** (unweighted) | Connected components, cycle detection |
| Space | O(w) — width of graph | O(h) — height/depth |

```java
// BFS — shortest path in unweighted graph
void bfs(int start, List<List<Integer>> adj) {
  boolean[] visited = new boolean[n];
  Queue<Integer> q = new LinkedList<>();
  q.offer(start);
  visited[start] = true;
  while (!q.isEmpty()) {
    int node = q.poll();
    System.out.print(node + " ");
    for (int neighbor : adj.get(node)) {
      if (!visited[neighbor]) {
        visited[neighbor] = true;
        q.offer(neighbor);
      }
    }
  }
}

// DFS — recursive
void dfs(int node, boolean[] visited, List<List<Integer>> adj) {
  visited[node] = true;
  System.out.print(node + " ");
  for (int neighbor : adj.get(node)) {
    if (!visited[neighbor]) dfs(neighbor, visited, adj);
  }
}
```

**🧠 Remember:** BFS=Queue=breadth=shortest, DFS=Stack/Recursion=depth

---

### Q6. Detect Cycle in Directed Graph (Topological Sort)
- Use DFS with 3 states: unvisited (0), in-progress (1), done (2)
- If you visit an in-progress node → cycle exists
- **Topological sort** only works on DAG (Directed Acyclic Graph)
- Order: nodes such that for every edge u→v, u comes before v

---

### Q7. Dijkstra's Algorithm
- Find shortest path with **non-negative weighted edges**
- Use **priority queue (min-heap)**
- Time: O((V + E) log V)

**When to use:**
- Unweighted graph → BFS
- Non-negative weights → Dijkstra
- Negative weights → Bellman-Ford

---

### Q8. Number of Islands ⭐ 🔥
```java
// BFS/DFS on 2D grid
int islands = 0;
for (int i = 0; i < grid.length; i++) {
  for (int j = 0; j < grid[0].length; j++) {
    if (grid[i][j] == '1') {
      islands++;
      bfs(grid, i, j); // mark all connected '1's as visited
    }
  }
}
```

---

## SECTION C: DYNAMIC PROGRAMMING ⭐

### Concept Overview

**DP = Overlapping subproblems + Optimal substructure**

- **Overlapping subproblems:** Same subproblems computed multiple times
- **Optimal substructure:** Optimal solution built from optimal solutions of subproblems
- **Memoization (top-down):** Recursion + cache results
- **Tabulation (bottom-up):** Iterative, fill table from base cases

---

### Q9. Fibonacci using DP ⭐
```java
// Memoization
int[] memo = new int[n + 1];
int fib(int n) {
  if (n <= 1) return n;
  if (memo[n] != 0) return memo[n];
  return memo[n] = fib(n-1) + fib(n-2);
}

// Tabulation (O(n) time, O(1) space)
int a = 0, b = 1;
for (int i = 2; i <= n; i++) { int c = a + b; a = b; b = c; }
return b;
```

---

### Q10. Climbing Stairs ⭐
```
n stairs, can climb 1 or 2 steps. Ways to reach top?
dp[i] = dp[i-1] + dp[i-2]  (same as Fibonacci!)
```
```java
int[] dp = new int[n + 1];
dp[0] = 1; dp[1] = 1;
for (int i = 2; i <= n; i++) dp[i] = dp[i-1] + dp[i-2];
return dp[n];
```

---

### Q11. Coin Change ⭐
```
Min coins to make amount. dp[i] = min coins for amount i.
dp[i] = min(dp[i], dp[i - coin] + 1) for each coin
```
```java
int[] dp = new int[amount + 1];
Arrays.fill(dp, amount + 1); // infinity
dp[0] = 0;
for (int i = 1; i <= amount; i++) {
  for (int coin : coins) {
    if (coin <= i) dp[i] = Math.min(dp[i], dp[i - coin] + 1);
  }
}
return dp[amount] > amount ? -1 : dp[amount];
```

---

### Q12. 0/1 Knapsack ⭐
```
n items, each with weight and value. Max value with capacity W.
dp[i][w] = max value using first i items with weight w
```
```java
int[][] dp = new int[n + 1][W + 1];
for (int i = 1; i <= n; i++) {
  for (int w = 0; w <= W; w++) {
    dp[i][w] = dp[i-1][w]; // don't take item i
    if (weights[i-1] <= w)
      dp[i][w] = Math.max(dp[i][w], values[i-1] + dp[i-1][w - weights[i-1]]);
  }
}
```

---

### Q13. Longest Common Subsequence (LCS) ⭐
```java
int[][] dp = new int[m + 1][n + 1];
for (int i = 1; i <= m; i++) {
  for (int j = 1; j <= n; j++) {
    if (s1.charAt(i-1) == s2.charAt(j-1)) dp[i][j] = 1 + dp[i-1][j-1];
    else dp[i][j] = Math.max(dp[i-1][j], dp[i][j-1]);
  }
}
return dp[m][n];
```

---

### Q14. How to Identify a DP Problem? ⭐

**Signs this is a DP problem:**
1. "Count number of ways" → DP
2. "Minimum/maximum" of something → DP
3. "Can you achieve X?" → DP (boolean)
4. Problem has choices at each step
5. Brute force has exponential time

**🧠 Remember:** If you see "optimal" + "choices" + "overlapping" → think DP

---

## SECTION D: Binary Search Advanced ⭐

### Q15. Find First/Last Occurrence
```java
// First occurrence
int lo = 0, hi = arr.length - 1, result = -1;
while (lo <= hi) {
  int mid = lo + (hi - lo) / 2;
  if (arr[mid] == target) { result = mid; hi = mid - 1; } // go left
  else if (arr[mid] < target) lo = mid + 1;
  else hi = mid - 1;
}
```

---

### Q16. Search in Rotated Sorted Array ⭐
```java
// One half is always sorted
while (left <= right) {
  int mid = left + (right - left) / 2;
  if (arr[mid] == target) return mid;
  if (arr[left] <= arr[mid]) { // left half sorted
    if (arr[left] <= target && target < arr[mid]) right = mid - 1;
    else left = mid + 1;
  } else { // right half sorted
    if (arr[mid] < target && target <= arr[right]) left = mid + 1;
    else right = mid - 1;
  }
}
```

---

## 🔑 QUICK MEMORY TRICKS

- **Tree traversals:** Pre=Root-first, In=Root-middle(sorted BST), Post=Root-last
- **BFS=Queue=Shortest**, **DFS=Stack=Deep**
- **DP signs:** "optimal + choices + overlapping" = DP
- **Coin Change = unbounded knapsack** variant
- **Climbing stairs = Fibonacci** pattern

---

## ⚠️ COMMON MISTAKES

1. Forgetting to mark nodes as visited in BFS/DFS → infinite loop
2. Confusing BFS (queue) with DFS (stack/recursion)
3. Initializing DP table with 0 instead of infinity for minimization problems
4. Tree traversal: confusing inorder vs preorder
5. For rotated binary search — not checking which half is sorted
