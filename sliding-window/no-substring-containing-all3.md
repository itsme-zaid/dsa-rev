      class Solution {
    public int numberOfSubstrings(String s) {
       int[] count = new int[3]; // For 'a', 'b', 'c'
        int res = 0;
        int l = 0;
        for (int r = 0; r < s.length(); r++) {
            count[s.charAt(r) - 'a']++;
            
            // While all three characters are in the window
            while (count[0] > 0 && count[1] > 0 && count[2] > 0) {
                // Add the number of substrings that can start from l and end at or after r
                res += s.length() - r;
                count[s.charAt(l) - 'a']--;
                l++;
            }
        }
        return res;
    }
    }

### This can be the template for all the substring problems
## for(fill your map here)
## while(right<length)
##    do your count here
##    while( the window is valid according to the quesiton) { minimize the window if you wanna and do stuff here }
