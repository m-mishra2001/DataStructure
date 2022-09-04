# Subset of Array
[problem Statement](https://leetcode.com/problems/subsets/)
![image](https://user-images.githubusercontent.com/60498472/188309191-e2b5046b-e74b-4a00-82ff-a090bba824d0.png)

# Approach
- Brutforce
```Java
  class Solution {
    
  
    public static void subset(int[]nums,int i,List<Integer>temp,List<List<Integer> >result){
        
         System.out.println("result2="+result);
        
        if(i==nums.length){
            System.out.println(temp);
            result.add(temp);
            return;
        }
        subset(nums,i+1,new ArrayList<Integer>(temp),result);
        temp.add(nums[i]);
        
        subset(nums,i+1,new ArrayList<Integer>(temp),result);
        
     
       
    }
    
    public List<List<Integer>> subsets(int[] nums) {
        
        List<Integer>temp=new ArrayList<Integer>();
        
      List<List<Integer>>result=new ArrayList<List<Integer>>(); 
        subset(nums,0,temp,result);
        
        return result;
    }
}
```

