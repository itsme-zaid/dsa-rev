    class Solution {
    public int findPeakElement(int[] nums) {
        
		if(nums.length == 1) return 0; // single element
        
        int n = nums.length;
        
		// check if 0th/n-1th index is the peak element
        if(nums[0] > nums[1]) return 0;
        if(nums[n-1] > nums[n-2]) return n-1;
		
		// search in the remaining array
        int start = 1;
        int end = n-2;
        
        while(start <= end) {
            int mid = start + (end - start)/2;
            if(nums[mid] > nums[mid-1] && nums[mid] > nums[mid+1]) return mid;
            else if(nums[mid] < nums[mid-1]) end = mid - 1;
            else if(nums[mid] < nums[mid+1]) start = mid + 1;
        }
        return -1; // dummy return statement
    }
    }

##  The constraint nums[i] !=nums[i+1] gives the hint, that means i-1,i,i+1 will not be the same element. now if they wont be the same element its either i is greater or smaller than its adjacent neighbors. make the decision based on that cause you'll find the peak if you treat the smaller element as boundary element;
