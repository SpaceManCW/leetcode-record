### 2024.5.28 二叉树中的第K大层和 https://leetcode.cn/problems/kth-largest-sum-in-a-binary-tree/description/
---

### JS


---

### Java
```java
class Solution {
    public long kthLargestLevelSum(TreeNode root, int k) {
            Queue<TreeNode> stack = new LinkedList<>();
            stack.add(root);
            // 类型是Long
            List<Long> resL = new ArrayList<>();
            while (!stack.isEmpty()) {
                int s = stack.size();
                long m = 0;
                for (int i = 0; i < s; i++) {
                    TreeNode node = stack.poll();
                    m += node.val;
                    if (node.left != null) {
                        stack.add(node.left);
                    }
                    if (node.right != null) {
                        stack.add(node.right);
                    }
                }
                resL.add(m);
            }
            // 注意这里要可能k大于层数
            if (resL.size() < k) {
            return -1;
             }
            Collections.sort(resL);
            return resL.get(resL.size()-k);
        }
}
```