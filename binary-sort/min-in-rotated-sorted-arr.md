    class Solution {
    public int findMin(int[] nums) {
        int low = 0;
        int high = nums.length-1;
        int min = Integer.MAX_VALUE;
        while(low<=high){
            // return the minimum element;
            int mid = low + (high - low) /2;
            if(nums[mid] >= nums[low]){
                min = Math.min(min,nums[low]);
                low = mid+1;
            }else{
                min = Math.min(min,nums[mid]);
                high = mid-1;
            }
        }
        return min;
    }
    }

## If one side is not sorted than the other would be;
