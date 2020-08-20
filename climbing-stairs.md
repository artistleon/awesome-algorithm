# [climbing-stairs](https://leetcode.com/problems/climbing-stairs/)

# #1

```java
class Solution {
    public int climbStairs(int n) {
       int a = 1, b = 1;
        for (int i = 2; i <= n; i++) {
            int sum = a + b;
            a = b;
            b = sum;
        }
        return b;
    }
}
```

# #2

```java
class Solution {
   public int climbStairs(int n) {
        int a = 1, b = 1;
        while (n-- > 0) a = (b += a) - a;
        return a;
    }
}
```

