import java.util.*;
import java.io.*;
 class FileHandling
{ static int n=4;
    static void create()throws IOException
    {BufferedReader br= new BufferedReader(new InputStreamReader(System.in));
     FileWriter fw= new FileWriter("Stud.dat");
     BufferedWriter bw= new BufferedWriter(fw);
     PrintWriter pw= new PrintWriter(bw);
     System.out.println("Enter Record :");
     for(int i=1;i<=n;i++)
     {System.out.print("Name ");
      String name= br.readLine();
      System.out.print("Roll ");
      int roll= Integer.parseInt(br.readLine());
      System.out.print("Marks ");
      int marks= Integer.parseInt(br.readLine());
      name=name+" "+roll+" "+marks;
      pw.println(name);
    }
    pw.close();
    }
  static void read()throws IOException
  {FileReader fw= new FileReader("Stud.dat"); 
   BufferedReader br= new BufferedReader(fw);
   String mat=" ";
   System.out.println("name\troll\tmarks");
   while((mat=br.readLine())!=null)
   {StringTokenizer str=new StringTokenizer(mat);
    String name= str.nextToken();
    int roll= Integer.parseInt(str.nextToken());
    int mark= Integer.parseInt(str.nextToken());
    System.out.println(name +"\t"+roll+"\t"+ mark);
   }
   br.close();
  }
  static void sort()throws IOException
  {int temp=0;String t="";
   FileReader fr= new FileReader("Stud.dat");
   BufferedReader br= new BufferedReader(fr);
   String mat=" ";
   int a[]=new int[n], b[]=new int[n],i=0; String c[]=new String[n];
   while((mat=br.readLine())!=null)
   {StringTokenizer str=new StringTokenizer(mat);
    String name= str.nextToken();
    int roll= Integer.parseInt(str.nextToken());
    int mark= Integer.parseInt(str.nextToken());
    b[i]=roll;a[i]=mark;c[i++]=name;
   }
   br.close();
   //sort array
   for(i=0;i<n-1;i++)
   for(int j=0;j<n-i-1;j++)
   if(a[j]>a[j+1])
   {temp=a[j];a[j]=a[j+1];a[j+1]=temp;
    temp=b[j];b[j]=b[j+1];b[j+1]=temp;
    t=c[j];c[j]=c[j+1];c[j+1]=t;
   }
   FileWriter fw= new FileWriter("Stud.dat");
   BufferedWriter bw= new BufferedWriter(fw);
   PrintWriter pw= new PrintWriter(bw);
   for(i=0;i<n;i++)
   {String name=c[i]+ " " +b[i]+ " " +a[i];
    pw.println(name);
   }
   pw.close();
}
}
