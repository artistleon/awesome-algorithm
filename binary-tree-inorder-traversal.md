# [binary-tree-inorder-traversal](https://leetcode.com/problems/binary-tree-inorder-traversal)

# #1

```Java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        trace(root,result);
        return result;
    }

    private void trace(TreeNode root,List<Integer> result) {
        if (root == null) return;
        trace(root.left,result);
        result.add(root.val);
        trace(root.right,result);
    }
}
```

