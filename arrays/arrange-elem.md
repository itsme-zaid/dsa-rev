    class Solution {
    public int[] rearrangeArray(int[] nums) {
        int nnums[] = new int[nums.length];
        int p=0;
        int n=1;
        for(int i=0; i<nums.length;i++){
            if(nums[i] >=0) {nnums[p] = nums[i];p=p+2;}
            else{ nnums[n]= nums[i]; n=n+2;}
        }
        
        return nnums;
    }
    }

### easy, tho tried doing in O(1) that wasted time;
