    class Solution {
    public int[][] merge(int[][] combinedIntervals) {
        Arrays.sort(combinedIntervals, (a, b) -> Integer.compare(a[0], b[0]));
        List<int[]> res = new ArrayList<>();
        for (int i = 0; i < combinedIntervals.length; i++) {
            int intervalToAdd[] = new int[2];
            intervalToAdd[0] = combinedIntervals[i][0];
            intervalToAdd[1] = combinedIntervals[i][1];
            // this condition refers to while the ith interval has not ended but the i+1 interval has started;
            while (i+1<combinedIntervals.length && intervalToAdd[1]>=combinedIntervals[i+1][0]) {
                // to increase interval we will take the smaller start and larger end of both the intervals;
                // since the combined intervals are still sorted by start there's no need to update the start
                intervalToAdd[1] = Integer.max(intervalToAdd[1], combinedIntervals[i+1][1]);
                i++;
            }
            
            // add the interval;
            res.add(intervalToAdd);
        }

        return res.toArray(new int[res.size()][]); 
    }
    }

### buh, did the approach, tho too lazy to actually write the code again;
