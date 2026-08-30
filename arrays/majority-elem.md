`class Solution {
    public int majorityElement(int[] nums) {
        // always exist in the array
        int cnt =1;
        int elem = 0;
        for(int i=1; i<nums.length;i++){
            if(nums[i] != nums[elem]){
                cnt--;
            }else cnt++;
            if(cnt==0){
                cnt =1;
                elem = i;
            }
        }
        return nums[elem];
    }
}`

## Approach:
**voting ts, easy took 2 mins**
