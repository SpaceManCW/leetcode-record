### 2024.6.1 和为K的子数组 https://leetcode.cn/problems/subarray-sum-equals-k/description/
```java
    public int subarraySum(int[] nums, int k) {
        if (nums == null || nums.length == 0) {
            return 0;
        }
        int res = 0;
        for (int i = 0; i < nums.length; i++) {
            int sum = nums[i];
            // 这里注意当前值等于k的情况
            if (sum == k) {
                res++;
            }
            // 可以从 j = i 开始，上面的sum初始值为0
            for (int j = i + 1; j < nums.length; j++) {
                sum += nums[j];
                if (sum == k) {
                    res++;
                }
            }
        }
        return res;
    }
```