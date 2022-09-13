#  Removing Stars From a String

[Problem Statement](https://leetcode.com/problems/removing-stars-from-a-string/)

## Approach

- Steps

*step 1:-* Push character of the string in stack till we encounter '*'

*step2:-* when an * encounter pop char from stack

### Dry Run

we have :- s = "leet**cod*e"


push leet in stack 

![image](https://user-images.githubusercontent.com/60498472/189838648-a52a6aaa-0f5d-4da7-9bfb-6f3e236fb95e.png)

since '*' encounter 

pop char from top 

The resultant stack will be

![image](https://user-images.githubusercontent.com/60498472/189839172-edc5c20b-a124-4e47-9ad4-bbe87507741b.png)

repeat the process till we traverse all the element of the string


we have stack after traversing whole string like

![image](https://user-images.githubusercontent.com/60498472/189839669-0146e9f5-7c1e-4af6-ac57-3aeba9d2dd66.png)

Now store elements in string and return string :- "lecoe"

``` java
class Solution {
    public String removeStars(String s) {
      
      Stack<Character>  stack=new Stack<>();
        for(int i=0;i<s.length();++i){
            if(s.charAt(i)=='*')
            stack.pop();
            else{
                stack.push(s.charAt(i));
            }
        }
       
       
        String str="";
       while(!stack.empty()){
           str=stack.pop()+str;
       }
        
        return str;
    }
}
```

