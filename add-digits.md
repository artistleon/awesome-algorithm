# [add-digits](https://leetcode-cn.com/problems/add-digits/)

# #1

```java
class Solution {
    public int addDigits(int num) {
        return ((num - 1) % 9) + 1;
    }
}

```

