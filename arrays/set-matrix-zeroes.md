    public void setZeroes(int[][] matrix) {
        boolean fr = false;
        boolean fc = false;
        for(int i=0; i<matrix[0].length;i++){
            if(matrix[0][i] == 0) {fr = true;break;}
            
        }
        for(int i=0; i<matrix.length;i++){
            if(matrix[i][0] == 0) {fc = true;break;}
            
        }
        // marking zeros
        for(int i=1; i<matrix.length; i++){
            for(int j=1; j<matrix[0].length;j++){
                if(matrix[i][j] == 0){
                    matrix[i][0] =0;
                    matrix[0][j] =0;
                }
            }
        }
        //converting zeroes based on first column
        for(int i=1; i<matrix.length;i++){
            if(matrix[i][0] == 0){
                for(int j = 1; j<matrix[0].length;j++){
                    matrix[i][j] = 0;
                }
            }
        }
        // converting to zereos based on first roww
        for(int i=1; i<matrix[0].length;i++){
            if(matrix[0][i] == 0){
                for(int j = 1; j<matrix.length;j++){
                    matrix[j][i] = 0;
                }
            }
        }
        if(fr){
            for(int i=0;i<matrix[0].length;i++){
               
                matrix[0][i] = 0;
            }
        }
        if(fc){
            for(int i=0;i<matrix.length;i++){
                matrix[i][0] = 0;
            }
        }

## Approach:
### thought of using the first row and first col to mark the rows and col that would be entirely converted to zero;
*Note: tho the approach is simple, and i did it completely by myself, i took 45mins because of some tricky stuff like if there are initial zeroes in the first row and first column we won't know which one's what cause like if theres a zero in first row then the entire row has to be converted to zero*
### the solution i thought was to using two flags for first row and col before we mark zeroes, so that if they are true we would just convert the entire row/col to zero at end only. 

# 45mins fmo sol
