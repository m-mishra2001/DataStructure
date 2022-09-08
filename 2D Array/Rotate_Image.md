# Rotate Matrix

[Problem Statement](https://leetcode.com/problems/rotate-image/)

## Approach 

- Brute Force

![image](https://user-images.githubusercontent.com/60498472/189032951-a0c5a79d-f5e6-49b8-9678-49d0074ebe89.png)


Step 1:- we firstly take a 1d Array result and Store values  in it in similar row wise as we want in result for example if we consider above case
then we firstly store 7,4,1 then 8,5,2 and so on so the result will be

[7,4,1,8,5,2,9,6,3]
now traverse this result and Modify or rewrite the main 2d matrix by row wise storing result's value in it.

### Code
``` java
class Solution {
    public void rotate(int[][] matrix) {
        ArrayList<Integer> result=new ArrayList<Integer>();
        for(int i=0;i<matrix[0].length;++i){
            for(int j=matrix.length-1;j>=0;--j){
                result.add(matrix[j][i]);
            }
        }
        int k=0;
      for(int i=0;i<matrix.length;++i){
          for(int j=0;j<matrix[0].length;++j){
              matrix[i][j]=result.get(k);
              ++k;
          }
      }
    }
}


```
