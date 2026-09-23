    class Solution {
    public int trap(int[] height) {
        int n = height.length-1;
        int[] nxh = new int[height.length];
        int[] pxh = new int[height.length];
        nxh[n] = height[n];
        pxh[0] = height[0];
        for(int i = n-1; i>=0; i--){
            if(height[i]>nxh[i+1]){
                nxh[i] = height[i];
            }else{
                nxh[i] = nxh[i+1];
            }
        }
        for(int i= 1; i<=n; i++){
            if(height[i]>pxh[i-1]){
                pxh[i] = height[i];
            }else{
                pxh[i] = pxh[i-1];
            }
        }

        int sum =0;
        for(int i=1; i<=n;i++){
            sum+= Math.min(pxh[i],nxh[i]) - height[i];
        }
        return sum;
        // return 0;
    }
    }
# This is the better approach not optimal, this is what came to my mind and then i applied it. 


