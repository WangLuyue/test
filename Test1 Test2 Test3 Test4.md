#Test1
public class Test1{
   public static void main(String[] args){
	System.out.println("Hello World!");
   }
}


#Test2
import java.util.Scanner;
import java.io.*;

public class Test2{
    public static void main(String[] args){
	int[]a = null;
	Scanner input = new Scanner(System.in);
	int len=0;
	System.out.print("请输入数组的长度：");
	try{
	    len = Integer.parseInt(input.nextLine());
	}catch(Exception e){
	
	}
	
	a = new int[len];
	System.out.println("a.length ="+a.length);
	
	for(int i=0;i<a.length;i++){
	    System.out.print("请输入数值：");
	    a[i] = input.nextInt();
	}
	
	System.out.println();
	System.out.print("该数组为：");
	for(int i=0;i<a.length;i++){
	    
	    System.out.print(a[i] + " ");
	}
	
	
	int sum = 0,max = 0;
	for(int i=0;i<a.length;i++){
	    sum = 0;
	    for(int j=i;j<a.length;++j){
		sum += a[j];
		if(sum>max)
		    max = sum;
	    }
	}
	
	System.out.println();
	System.out.println("该数组之和的最大值为 "+max);

    }
    
    
}



#Test3
import java.util.Scanner;

public class Test3{
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("请输入英文：");
	String str = input.nextLine();
        String[] strArr = str.split("\\s+|[,]");
        StringBuffer result = new StringBuffer();
        for(int i = strArr.length -1;i >=0; i--){
            result.append(strArr[i] + " ");
        }
        result.setCharAt(str.length() -10, ' ');
        System.out.println("颠倒顺序后的结果为："+result.toString());
}}


#Test4
