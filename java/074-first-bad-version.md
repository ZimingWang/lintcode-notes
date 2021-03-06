[074. First Bad Version](http://www.lintcode.com/problem/first-bad-version)

- [prev: 073. Construct Binary Tree from Preorder and Inorder Traversal](073-construct-binary-tree-from-preorder-and-inorder-traversal.md)
- [next: 075. Find Peak Element](075-find-peak-element.md)

---

Simple application of binary search.

```java
/**
 * public class SVNRepo {
 *     public static boolean isBadVersion(int k);
 * }
 * you can use SVNRepo.isBadVersion(k) to judge whether 
 * the kth code version is bad or not.
*/
class Solution {
    /**
     * @param n: An integers.
     * @return: An integer which is the first bad version.
     */
    public int findFirstBadVersion(int n) {
        if ( n < 1) {
            return -1;
        }
        
        int start = 1, end = n;
        
        while (start + 1 < end) {
            int mid = start + (end - start) / 2;
            if (SVNRepo.isBadVersion(mid)) {
                end = mid;
            } else {
                start = mid;
            }
        }
        
        if (SVNRepo.isBadVersion(start)) {
            return start;
        }
        
        if (SVNRepo.isBadVersion(end)) {
            return end;
        }
        
        return -1;
    }
}

```

---

- [prev: 073. Construct Binary Tree from Preorder and Inorder Traversal](073-construct-binary-tree-from-preorder-and-inorder-traversal.md)
- [next: 075. Find Peak Element](075-find-peak-element.md)
