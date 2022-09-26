class FileHandling :
    n = 4
   // @staticmethod
    import sys
 def create() : 
  try:
     file = open ( "filethatdoesnotexist.txt", 'r' )
   except IOError, e:
     print e
print sys.exc_type
something()
   
        br =  java.io.BufferedReader( java.io.InputStreamReader(java.io.BufferedInputStream@33e5ccce))
        fw =  java.io.FileWriter("Stud.dat")
        bw =  java.io.BufferedWriter(fw)
        pw =  java.io.PrintWriter(bw)
        print("Enter Record :")
        i = 1
        while (i <= FileHandling.n) :
            print("Name ", end ="")
            name = br.readLine()
            print("Roll ", end ="")
            roll = int(br.readLine())
            print("Marks ", end ="")
            marks = int(br.readLine())
            name = name + " " + str(roll) + " " + str(marks)
            pw.println(name)
            i += 1
             pw.close()
            create()
       
   // @staticmethod
    def read() :  
         try:
     file = open ( "filethatdoesnotexist.txt", 'r' )
   except IOError, br:
        fw =  java.io.FileReader("Stud.dat")
        br =  java.io.BufferedReader(fw)
        mat = " "
        print("name\troll\tmarks")
        while ((
        mat = br.readLine()) != None) :
            str =  java.util.StringTokenizer(mat)
            name = str.nextToken()
            roll = int(str.nextToken())
            mark = int(str.nextToken())
            print(name + "\t" + str(roll) + "\t" + str(mark))
        br.close()
    //@staticmethod
    def sort() :  
         try:
     file = open ( "filethatdoesnotexist.txt", 'r' )
   except IOError, br:
        temp = 0
        t = ""
        fr =  java.io.FileReader("Stud.dat")
        br =  java.io.BufferedReader(fr)
        mat = " "
        a = [0] * (FileHandling.n)
        b = [0] * (FileHandling.n)
        i = 0
        c = [None] * (FileHandling.n)
        while ((
        mat = br.readLine()) != None) :
            str =  java.util.StringTokenizer(mat)
            name = str.nextToken()
            roll = int(str.nextToken())
            mark = int(str.nextToken())
            b[i] = roll
            a[i] = mark
            c[i += 1] = name
        br.close()
        # sort array
        i = 0
        while (i < FileHandling.n - 1) :
            j = 0
            while (j < FileHandling.n - i - 1) :
                if (a[j] > a[j + 1]) :
                    temp = a[j]
                    a[j] = a[j + 1]
                    a[j + 1] = temp
                    temp = b[j]
                    b[j] = b[j + 1]
                    b[j + 1] = temp
                    t = c[j]
                    c[j] = c[j + 1]
                    c[j + 1] = t
                j += 1
            i += 1
        fw =  java.io.FileWriter("Stud.dat")
        bw =  java.io.BufferedWriter(fw)
        pw =  java.io.PrintWriter(bw)
        i = 0
        while (i < FileHandling.n) :
            name = c[i] + " " + str(b[i]) + " " + str(a[i])
            pw.println(name)
            i += 1
        pw.close()
