    class Solution {
    public boolean searchMatrix(int[][] matrix, int target) {
        int row = 0;
        int col = matrix[0].length-1;
        while(row < matrix.length && col >= 0){
            if(matrix[row][col] == target) return true;
            if(matrix[row][col] > target) col--;
            else row++;
        }
        return false;
    }
    }

# No need for any binary search a simple O(m+n) solution is optimal. start at the last element of the first row, if its greater than target then naturally the element in its col will also be greater than it so col--, if its less than target then row++ 
