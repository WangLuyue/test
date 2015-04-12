#test1

public class Test1{
   public static void main(String[] args){
	System.out.println("Hello World!");
   }
}


#test2

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

#test3

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

#test4

package github;

import java.awt.Color;
import java.awt.Graphics;
import java.awt.event.MouseEvent;
import java.awt.event.MouseMotionListener;

import javax.swing.JFrame;
import javax.swing.JPanel;


public class MoveHelloWorld extends JFrame implements MouseMotionListener{
	//窗口的宽度和高度
	final int WINDOW_WIDTH = 500;
	final int WINDOW_HEIGHT = 500;
	MyJPanel myPanel;
	//鼠标任意时刻的坐标值，默认值为屏幕中心
	int nowX=WINDOW_WIDTH/2,nowY=WINDOW_WIDTH/2;
	
	//初始化窗口中的组件
	public MoveHelloWorld() {
		myPanel = new MyJPanel();
		this.add(myPanel);
		
		this.addMouseMotionListener(this);
		this.setSize(WINDOW_WIDTH, WINDOW_HEIGHT);
		this.setVisible(true);
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		this.setLocationRelativeTo(null);
	}
	
	@Override
	public void mouseDragged(MouseEvent arg0) {
		nowX = arg0.getX();
		nowY = arg0.getY();
		repaint();
	}

	@Override
	public void mouseMoved(MouseEvent arg0) {
		// TODO Auto-generated method stub
		
	}
	
	class MyJPanel extends JPanel{
		@Override
		public void paint(Graphics arg0) {
			arg0.setColor(Color.WHITE);
			arg0.fillRect(0, 0, WINDOW_WIDTH, WINDOW_HEIGHT);
			arg0.setColor(Color.BLACK);
			arg0.drawString("Hello World", nowX, nowY);
		}
	}
	
	public static void main(String[] args) {
		MoveHelloWorld moveString = new MoveHelloWorld();
	}
}
