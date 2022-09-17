# part3-Practical_1


package part3;

import java.util.Date;
import java.util.Scanner;

	
	abstract class Geometricobject
	{
		public String color;
		public boolean filled;
		public Date datecreated =new Date();
		protected Geometricobject()
		{
		 color="red";
		 filled=true;
		}
		protected Geometricobject(String C,boolean F)
		{
		 color=C;
		 filled=F;
		}
		
		public String getcolor()//for get color from protected
		{
			return color;
		}
		public void setcolor(String C)
		{
		    color=C;
		}
		
		public boolean isfilled()//for get filled from protected
		{
			return filled;
		}
		public void setfilled(boolean F)
		{
			filled=F;
		}
		
		
		public Date getdatecreated()
		{
			return datecreated;
		}
		
		public abstract double getArea();
		public abstract double getPerimeter();
	}
			
class Circle extends Geometricobject{
        public double radius;
        public Circle()
        {
        radius=0;
        }
        public Circle(double R) 
        {
        	radius=R;	
        }
        public Circle(double R,String C,boolean F) 
        {
        	radius=R;
        	color=C;
        	filled=F;
        }
        
		
		public double getArea()
		{
			return 3.14*radius*radius;
		}

	
		public double getPerimeter() 
		{
			return 2*3.14*radius;
		}
		}

	 
	
class Rectangle extends Geometricobject{
		public double width;
		 public double height;
		 
		 public Rectangle()
		 {
			 width=0;
			 height=0;
		 }
		 public Rectangle(double W,double H)
		 {
			 width=W;
			 height=H;
		 }
		 public Rectangle(double W,double H,String C,boolean F)
		 {
			 width=W;
			 height=H;
			 color=C;
			 filled=F;
		 }
		
		 public double getwidth()
		 {
			return width;	 
		 }
		 
		 public void setwidth(double W)
		 {
			 width=W;
		 }
		 
		 public double getheight()
		 {
			return height;	 
		 }
		 
		 public void setheigth(double H)
		 {
			 height=H;
		 }
		 
		 
		public double getArea() {
			return width*height;
		}
	
		public double getPerimeter() {
			return 2*(width+height);
		} 
	 }

class Practical1 {
	public static void main(String[]args) 
	{
	  Geometricobject g1=new Circle(9.5,"red",true);
	  Geometricobject g2=new Rectangle(10,6,"blue",false);
	  System.out.println("For circle:");
	  System.out.println("color:"+g1.getcolor());
	  System.out.println("Perimeter:"+g1.getPerimeter());
	  System.out.println("Area:"+g1.getArea());
	  
	  System.out.println("For rectangle:");
	  System.out.println("color:"+g2.getcolor());
	  System.out.println("Perimeter:"+g2.getPerimeter());
	  System.out.println("Area:"+g2.getArea());
	  
	  if(g1.getArea()==g2.getArea())
	  {
		  System.out.println("Area of circle and rectangle are same."); 
	  }
	  else
	  {
		  System.out.println("Area of circle and rectangle are not same.");
	  }
	}

}
