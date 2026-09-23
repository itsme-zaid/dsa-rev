    class Solution {
    public List<List<Integer>> fourSum(int[] nums, int target) {
        List<List<Integer>> ans = new ArrayList<>();
        Arrays.sort(nums);
        for(int i=0; i<nums.length-3;i++){
            if(i!=0 && nums[i] == nums[i-1]) continue;
            for(int j = i+1;j<nums.length-2;j++){
                if(j>i+1 && nums[j] == nums[j-1])continue;
                int p = j+1;
                int k = nums.length - 1;
                while(p<k){
                    long s = (long) nums[i] + nums[j] + nums[p] + nums[k];
                    if(s == target){
                        ans.add(new ArrayList<>(Arrays.asList(nums[i],nums[j],nums[k],nums[p])));
                        p++;
                        
                        while(nums[p]==nums[p-1] && p<k) p++;
                    }else if(s<target){
                        p++;
                    }else{
                        k--;
                    }
                }
            }
        }
        return ans;

## canonically same as 3sum; lock one element then its 3sum, lock another then its 2sum;
        
    }
}
