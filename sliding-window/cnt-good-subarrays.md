      class Solution {
    int cal(int [] arr, int goal){
        if(goal<0) return 0;
        int r,l,sum;
        r = 0;
        l = 0;
        sum = 0;
        int cnt =0;
        for(r = 0; r<arr.length;r++){
            sum+=arr[r];
            while(sum>goal && l<=r){
                sum-= arr[l];
                l++;
            }
            cnt+= r-l+1;  
        }
        return cnt;
    }
    public int numberOfSubarrays(int[] nums, int k) {
        for (int i = 0; i < nums.length; i++) {
            if (nums[i] % 2 == 0)
                nums[i] = 0;
            else
                nums[i] = 1;
        }
## Its just count binary subarray with given sum if you convert the odd ones to 1 and even to zeros. also for counting atmost you gotta count in not out the subarray 
        return cal(nums,k) - cal(nums,k-1);
    }
}
