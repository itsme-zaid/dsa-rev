    class Solution {
        public int maxScore(int[] nums, int K) {
        int total = 0;
        for (int i = 0; i < K; i++) total += nums[i];
        int best = total;
        for (int i = K - 1, j = nums.length - 1; i >= 0; i--, j--) {
            total += nums[j] - nums[i];
            best = Math.max(best, total);
        }
        return best;
    }
    }

# Pretty easy, not really any sliding window -< calculate sum from of the first k elements, and then while keeping the maximum, you decrease the sum from left and increase from right, a simple O(K) solution;;;;
