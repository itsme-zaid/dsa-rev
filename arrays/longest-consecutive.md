    class Solution {
        public int longestConsecutive(int[] nums) {
            Set<Integer> numSet = new HashSet<>();

            for (int num : nums) {
            numSet.add(num);
            }

            int longest = 0;

            for (int n : numSet) {
                if (!numSet.contains(n - 1)) {
                    int length = 1;
  
                    while (numSet.contains(n + length)) {
                        length++;
                    }
  
                    longest = Math.max(longest, length);
                }
            }

          return longest;
        }
      }

## Approach : thought of the optimal method but implemented hashmap;;
*thought of the set method but didn't implement it tho i was trying hashmap and could've done it but it was messy*
