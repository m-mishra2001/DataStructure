# All Possible permutaion of Array

[Problem Statement](https://leetcode.com/problems/permutations/)

![image](https://user-images.githubusercontent.com/60498472/188354467-6bdcb614-b718-4b12-9fe7-49d011cdfdea.png)

## Optimised Approach

```java


package Recursion;
import java.util.*;
public class Permutation {

	public static void swap(int l,int i,int num[]) {
		int temp=num[l];
		num[l]=num[i];
		num[i]=temp;
	}
	public static void FindPermutation(List<List<Integer>> result,int num[],int i) {
		
		if(i>=num.length) {
			List<Integer> temp=new ArrayList<Integer>();
			for(int x:num) {
				temp.add(x);
			}
			result.add(temp);
			return;
		}
		
		for(int l=i;l<num.length;++l) {
			swap(l,i,num);
			FindPermutation(result,num,i+1);
			swap(l,i,num);
			
		}
		
	}
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Scanner sc=new Scanner(System.in);
		int n=sc.nextInt();
		int arr[]=new int[n];
		System.out.println("enter the array element");
		for(int i=0;i<n;++i) {
			arr[i]=sc.nextInt();
		}
		List<List<Integer>> result=new ArrayList<List<Integer>>();
		int i=0;
		FindPermutation(result,arr,i);
		System.out.println("All permutations of array is ");
		System.out.print(result);
		
		

	}

}

```

- Output

![image](https://user-images.githubusercontent.com/60498472/188354648-8ddae40f-0017-417b-9b55-76bb4ed20fd5.png)
