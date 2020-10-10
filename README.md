import java.util.Arrays;
import java.util.Scanner;

public class Example1 {

	public static void main(String[] args) 
		Scanner sc=new Scanner(System.in);
		
		 
		System.out.println("Enter the Number of Employees");
		int No_Of_Employees=sc.nextInt();
		System.out.println("Enter the size of the Array");
		int n=sc.nextInt();
		int[] input=new int[n];
		System.out.println("Enter the elements into array");
		for(int i=0;i<n;i++)
		{
			input[i]=sc.nextInt();
		}
		
		int[] sorted_input=new int[input.length];
		Arrays.parallelSort(input);
		int j=0;
		int[] Difference_array=new int[input.length-No_Of_Employees+1];
		for(int i=0;i<input.length;i++)
		{
			if(j<input.length&& i<=input.length-No_Of_Employees)
			{
				j=i+No_Of_Employees-1;
				Difference_array[i]=input[j]-input[i];
			}
			
		}
		for(int i=0;i<Difference_array.length;i++)
		{
			System.out.print(Difference_array[i]+" ");
		}
	int min=Difference_array[0];
	int index=0;
	for(int i=0;i<Difference_array.length;i++)
	{
		if(Difference_array[i]<min)
		{
			min=Difference_array[i];
			index=i;
		}
	}
	System.out.println();
	System.out.println(min);
	System.out.println(index);
	int[] final_array=new int[No_Of_Employees];
	
	for(int i=index;i<index+No_Of_Employees;i++)
	{
		System.out.println(input[i]+" ");
	}
	}	
}
