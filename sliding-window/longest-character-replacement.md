    class Solution {
    public int characterReplacement(String str, int k) {
        int[] count = new int[26];
        int start = 0, maxCount = 0, result = 0;

        for (int end = 0; end < str.length(); end++) {
            int p = str.charAt(end) - 'A';
            count[p]++;
            maxCount = Math.max(maxCount, count[p]);

            // window is invalid
            if (end - start + 1 - maxCount > k) {
                // (simple logic -> if the substring length - maxElement length is greater than k then the window is invalid);
                count[str.charAt(start) - 'A']--;
                start++;
            }

            result = Math.max(result, end - start + 1);
        }

        return result;
    }
    }


## Approach is easy
### overcomplicated the solution (didn't really try) tho the intuition was same, just keep track of the subarray - maximum it has to be greater than k theres really no need for extra while loop or anything else;
