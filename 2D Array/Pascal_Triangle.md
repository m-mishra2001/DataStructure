# Pascal Triangle
[Problem Statement](https://leetcode.com/problems/pascals-triangle/)

## Approach
- BruteForce
### 
 Step 1:- Create a ArrayList Result that store actual ans.
step 2:- Add two rows in result [[1],[1,1]]
the resultant Pascal Triagle afte step 1 and 2  will be 


![image](https://user-images.githubusercontent.com/60498472/189031533-a6c75e7e-b563-40f8-8ad5-b3eff0836f59.png)

step 3:-run for loop from i=2------number of rows,in for loop we calculate the values of next row and add that row in result .In this way we call calculateRow in Each 
iteration and calculate values in each row .

![image](https://user-images.githubusercontent.com/60498472/189032011-bf34cdd2-fe67-4e20-894c-52ddfe72a676.png)

```java
class Solution {
    public static List<Integer> calculateRow(List<Integer> prev){
       int i=0;
        int j=i+1;
        List<Integer> temp=new ArrayList<Integer>();
        temp.add(1);
        while(j<prev.size()&&i<prev.size()){
           temp.add(prev.get(i)+prev.get(j)); 
            ++i;
            j=i+1;
        }
        System.out.println(temp);
        return temp;
        
    }
    public List<List<Integer>> generate(int numRows) {
     
        List<List<Integer>> result=new ArrayList<List<Integer>>();
     
        result.add(new ArrayList<Integer>());
        result.get(0).add(1);
        if(numRows==1){
            return result;
        }
        result.add(new ArrayList<Integer>());
        result.get(1).add(1);
        result.get(1).add(1);
        if(numRows==2){
            return result;
        }
         for(int i=2;i<numRows;++i){
        
            List<Integer> temp=new ArrayList<Integer>();
             temp=calculateRow(result.get(i-1));
             
             temp.add(1);
             result.add(temp);
             
         }
           
    
       
         return result;
    }
   
}





