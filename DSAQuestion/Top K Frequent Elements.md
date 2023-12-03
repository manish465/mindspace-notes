Question link : [Top K Frequent Elements - LeetCode](https://leetcode.com/problems/top-k-frequent-elements/)

### Question:
Given an integer array `nums` and an integer `k`, return _the_ `k` _most frequent elements_. You may return the answer in **any order**.
```Java
Example 1:

Input: nums = [1,1,1,2,2,3], k = 2
Output: [1,2]

Example 2:

Input: nums = [1], k = 1
Output: [1]
```
**Constraints:**

- `1 <= nums.length <= 105`
- `-104 <= nums[i] <= 104`
- `k` is in the range `[1, the number of unique elements in the array]`.
- It is **guaranteed** that the answer is **unique**.

**Follow up:** Your algorithm's time complexity must be better than `O(n log n)`, where n is the array's size.

### Solution:

- First, we need to create a frequency map using hash table, which will keep all the number and their occurrence.
- We need a Priority Queue in the form of a max heap, which will store the number in the descending order of their occurrence.
- Then return the first k elements of the max heap.

### Code:

```Java
class Solution {
    public int[] topKFrequent(int[] nums, int k) {
        Map<Integer,Integer> freq = new HashMap<>();
        for(int num: nums){
            freq.put(num, freq.getOrDefault(num, 0) + 1);
        }

        PriorityQueue<Integer> maxHeap = 
				        new PriorityQueue<>((a, b) -> freq.get(b) - freq.get(a));

        for(int num: freq.keySet()){
            maxHeap.offer(num);
        }

        int[] output = new int[k];
        for(int i=0; i < k; i++){
            output[i] = maxHeap.poll();
        }

        return output;
    }

}
```


#DSA #Question #ProrityQueue #HashMap