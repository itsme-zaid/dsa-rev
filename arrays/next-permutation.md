    class Solution {
    private void reverse(int[] nums, int left, int right) {
        while (left < right) {
            int temp = nums[left];
            nums[left] = nums[right];
            nums[right] = temp;

            left++;
            right--;
        }
    }
    public void nextPermutation(int[] nums) {
        int elem =-1;
        for(int i=nums.length-2;i>=0;i--){
            if(nums[i]<nums[i+1]){
                elem = i;
                break;
            }    
        }
        if(elem ==-1){Arrays.sort(nums);return;}
        //System.out.println("Element " + nums[elem]);
        int s = elem+1;
        for(int i=elem + 1;i<nums.length;i++){
            if(nums[i] < nums[s] && nums[i] > nums[elem]){
                s = i;
            }
        }
        //System.out.println("Shortest on right " + nums[s]);
        // swap;
        int temp = nums[s];
        nums[s] = nums[elem];
        nums[elem] = temp;
        Arrays.sort(nums,elem+1,nums.length);
        return;
    }
    }


## Approach: easy  
*tho i did arrays.sort() the remaining part of the array where i could have just done reverse the array; that shi increased the tc*
