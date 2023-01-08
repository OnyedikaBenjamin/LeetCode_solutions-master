### Provided Code

```java
public class Node {
    int val;
    List<Node> children;
}
```

### Solution

```java
class Solution {
    public List<List<Integer>> levelOrder(Node root) {
        if (root == null) {
            return new ArrayList();
        }
        List<List<Integer>> lists = new ArrayList();
        Deque<Node> deque = new ArrayDeque(); // use deque as a queue
        deque.add(root);
        while (!deque.isEmpty()) {
            int numNodesInLevel = deque.size();
            List<Integer> level = new ArrayList(numNodesInLevel);
            while (numNodesInLevel-- > 0) {
                Node n = deque.remove();
                level.add(n.val);
                for (Node child : n.children) {
                    deque.add(child);
                }
            }
            lists.add(level);
        }
        return lists;
    }
}
```

### Time/Space Complexity

-  Time Complexity: O(n)
- Space Complexity: O(n)

### Links

- [github.com/RodneyShag](https://github.com/RodneyShag)
