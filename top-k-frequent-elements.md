# [top-k-frequent-elements](https://leetcode.com/problems/top-k-frequent-elements/)

# #1

```Java
class Solution {
     public int[] topKFrequent(int[] nums, int k) {
       int[] result = new int[k];
        Map<Integer,Integer> map = new HashMap<>();
        for (Integer num:nums) map.put(num, map.getOrDefault(num, 0) + 1);
        PriorityQueue<Map.Entry<Integer, Integer>> queue = new PriorityQueue<>((a,b) -> b.getValue() - a.getValue());
        for (Map.Entry<Integer,Integer> entry:map.entrySet()) queue.offer(entry);
        for (int i = 0;i < k; ++i) result[i] = queue.poll().getKey();
        return result;
    }
}
```

