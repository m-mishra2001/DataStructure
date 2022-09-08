# Set Matrix Zero
[Problem Statement](https://leetcode.com/problems/set-matrix-zeroes/)


![image](https://user-images.githubusercontent.com/60498472/188310054-d63e301c-60d8-4f80-a4eb-68578f8fb4e2.png)

# Approach 
- BruteForce

Step 1:- we will take a ArrayList arr and store row index and column index of values 0 in matrix

for example in 

![image](https://user-images.githubusercontent.com/60498472/189039073-a2b80201-1152-4629-9c1d-2a1d87475dc1.png)

arr=[0,0],[0,3]]

Step 2:- Run the for loop from i=0-----arr.size()
call make row zero
and make column zero 


IN 1st pass [0,0]
MakeRow zero produce
![image](https://user-images.githubusercontent.com/60498472/189039777-019dd38a-f8a8-4917-b375-421f41e66f60.png)

Make column zero produce
![image](https://user-images.githubusercontent.com/60498472/189039899-0075ee13-4c1f-4f46-b9f7-284b6da84907.png)

IN  second pass i.e is for [0,3]
MakeRow zero produce
![image](https://user-images.githubusercontent.com/60498472/189039777-019dd38a-f8a8-4917-b375-421f41e66f60.png)

MakeColumn Zero Produce
![image](https://user-images.githubusercontent.com/60498472/189040097-b1eb0017-c048-4454-96f6-6326574169cf.png)

loop ends and this will be the final ans

# Code

``` java 
class Solution {
    public static void makerowzero(int[][]matrix,int row){
        for(int i=0;i<matrix[0].length;++i){
            matrix[row][i]=0;
        }
    }
    public static void makecolzero(int[][]matrix,int col){
        for(int i=0;i<matrix.length;++i){
            matrix[i][col]=0;
        }
    }
    public void setZeroes(int[][] matrix) {
     ArrayList<ArrayList<Integer>> arr=new ArrayList<ArrayList<Integer>>();
     int k=0;
     for(int i=0;i<matrix.length;++i){
         for(int j=0;j<matrix[0].length;++j){
             if(matrix[i][j]==0){
                 arr.add(new ArrayList<Integer>());
                 arr.get(k).add(i);
                 arr.get(k).add(j);
                 ++k;
             }
         }
     }
        
        for(int i=0;i<arr.size();++i){
            makerowzero(matrix,arr.get(i).get(0)) ;
            makecolzero(matrix,arr.get(i).get(1));
        }
        
    }
}

```

