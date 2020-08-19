# [sliding-window-maximum](https://leetcode.com/problems/sliding-window-maximum/)

# #1

```Java
 class Solution {
    public int[] maxSlidingWindow(int[] nums, int k) {
        if(nums == null || nums.length == 0)  return new int[0];
        int[] result = new int[nums.length + 1 - k];
        int index = 0;
        Deque<Integer> queue = new ArrayDeque<>();
        for(int i = 0; i < nums.length; i++) {
             //window move, removes the head of the queue
            if (!queue.isEmpty() && i - queue.peek() >= k) {
                queue.poll();
            }
            while (!queue.isEmpty() && nums[i] > nums[queue.peekLast()]) {
                queue.pollLast();
            }
            queue.offer(i);
            if (i >= k - 1) result[index++] = nums[queue.peek()];
        }
        return result;
    }
}
```

