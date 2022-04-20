# vb.net
# vb.net
********************************************************************************************
1. Write a C# program to print a binary triangle <br>
********************************************************************************************
using System; <br>
namespace Exercises <br>
{ <br>
 class BinaryTriangle<br> 
 { <br>
 static void Main(string[] args)<br> 
 { <br>
 int number,digit=1; <br>
 Console.Write("\nEnter the number of lines: "); <br>
 number = Convert.ToInt32(Console.ReadLine()); <br>
 for(int i=1; i<=number; i++) <br>
 { <br>
 for(int space=number-i; space>0; space--) <br>
 { <br>
 Console.Write(" "); <br>
 } <br>
 for(int j=0; j<i; j++) <br>
 { <br>
 Console.Write(digit + " "); <br>
 digit = (digit==1) ? 0:1; <br>
 }<br> 
 Console.Write("\n"); <br>
 } <br>
 } <br>
 } <br>
} <br>
output:

![image](https://user-images.githubusercontent.com/97940277/154424310-683c4e72-1d56-42de-8157-6305eb621de2.png)<br> 

************************************************************************************************************************
2.Write a C# Program to Check Whether the Entered Number is an Amicable Number  or Not. <br>  
*************************************************************************************************************************
using System; <br>
namespace Exercises <br>
{ <br>
 class AmicableNumber <br>
 { <br>
 static void Main(string[] args) <br>
 { <br>
 int num1, num2, sum1=0, sum2=0; <br>
 Console.WriteLine("\n--------AMICABLE NUMBERS-----------\n");  Console.Write("\nEnter the first number: "); <br>
 num1 = Convert.ToInt32(Console.ReadLine()); <br>
 Console.Write("\nEnter the second number: "); <br>
 num2 = Convert.ToInt32(Console.ReadLine()); <br>
 for(int i=1; i<num1; i++) <br>
 { <br>
 if(num1%i == 0) <br>
 { <br>
 sum1 += i; <br>
 } <br>
 } <br>
 for(int i=1; i<num2; i++) <br>
 { <br>
 if(num2%i == 0) <br>
 { <br>
 sum2 += i; <br>
 } <br>
 } <br>
 if(sum1 == num2 && sum2 == num1) <br>
 { <br>
 Console.WriteLine("\nThe numbers {0} and {1} are amiciable.", num1, num2);  } <br>
 else <br>
 { <br>
 Console.WriteLine("\nThe numbers {0} and {1} are not amiciable.", num1, num2);  } <br>
 } <br>
 } <br>
}<br>

Output:
![image](https://user-images.githubusercontent.com/97940277/154425770-736ffae1-e0b1-47bb-9302-dc3bb7b0f174.png)

****************************************************************************************************************
3.Write a C# Program to Illustrate Multilevel Inheritance with Virtual Methods  (displaying student details). <br>
************************************************************************************************************
using System; <br>
namespace Exercises<br> 
{ <br>
 class PersonalDetails<br> 
 { <br>
 string name; <br>
 int age; <br>
 string gender; <br>
 public PersonalDetails(string name, int age, string gender) <br>
 { <br>
 this.name = name; <br>
 this.age = age; <br>
 this.gender = gender; <br>
 } <br>
 public virtual void Display() <br>
 { <br>
 Console.WriteLine("\n-------- PERSONAL DETAILS --------\n"); <br>
 Console.WriteLine("Name : " + name); <br>
 Console.WriteLine("Age : " + age); <br>
 Console.WriteLine("Gender : " + gender);<br> 
 } <br>
 } <br>
 class CourseDetails : PersonalDetails <br>
 { <br>
 int regNo;<br> 
 string course;<br> 
 int semester; <br>
 public CourseDetails(string name, int age, string gender, int regNo, string course, int semester)  : base(name, age, gender) <br>
 { <br>
 this.regNo = regNo; <br>
 this.course = course; <br>
 this.semester = semester<br>; 
 } <br>
 public override void Display()<br> 
 { <br>
 base.Display(); <br>
 Console.WriteLine("\n-------- COURSE DETAILS --------\n");<br>
 Console.WriteLine("Register Number : " + regNo); <br>
 Console.WriteLine("Course : " + course); <br>
 Console.WriteLine("Semester : " + semester); <br>
 } <br>
 } <br>
 class MarksDetails : CourseDetails<br> 
 { <br>
 int[] marks = new int[5];<br> 
 int total; <br>
 float average;<br> 
 string grade; <br>
 int flagFail; <br>
 public MarksDetails(string name, int age, string gender, int regNo, string course, int semester,  int[] marks) : base(name, age, gender, regNo, course, semester) <br>
 { <br>
 total = 0; <br>
 for(int i=0; i<5; i++) <br>
 { <br>
 this.marks[i] = marks[i]; <br>
 total += marks[i]; <br>
 if(marks[i]<35) <br>
 { <br>
 flagFail = 1; <br>
 } <br>
 } <br>
 Calculate(); <br>
 } <br>
 private void Calculate()<br> 
 { <br>
 average = total/5; <br>
 if(flagFail == 1 || average<40) <br>
 grade = "Fail"; <br>
 else if(average>=70) <br>
 grade = "Distinction"; <br>
 else if(average>=60) <br>
 grade = "First Class"; <br>
 else if(average>=50) <br>
 grade = "Second Class"; <br>
 else <br>
 grade = "Pass Class";<br> 
 } <br>
 public override void Display() <br>
 { <br>
 base.Display(); <br>
 Console.WriteLine("\n-------- MARKS DETAILS --------\n"); <br>
 Console.Write("Marks in 5 subjects: "); <br>
 for(int i=0; i<5; i++) <br>
 Console.Write(marks[i] + " <br>
 Console.Write<br>
 Console.WriteLine("Total : " + total); <br>
 Console.WriteLine("Average : " + average); <br>
 Console.WriteLine("Grade : " + grade); <br>
 } <br>
 } <br>
 class MultiLevel <br>
 { <br>
 public static void Main(string[] args) <br>
 { <br>
 MarksDetails Student1 = new MarksDetails("Rehal Thomas", 22, "Male", 20190001, "MCA", 5,  new int[]{77,80,98,95,90}); <br>
 Student1.Display(); <br>
 } <br>
 } <br>
}<br>
OUTPUT: <br>
![Screenshot (2)](https://user-images.githubusercontent.com/97940277/154626095-6285ac41-c5d1-43f9-b32f-4633d2e02030.png)<br>

****************************************************************************************************************
4. Write a C# Program to Create a Gray Code.<br>
****************************************************************************************************************
using System; <br>
namespace Exercises <br>
{ <br>
 class GrayCode <br>
 { <br>
 static int getGray(int n) <br>
 { <br>
 return n^(n>>1); <br>
 } <br>
 static void Main(string[] args) <br>
 { <br>
 int InputNum, GrayNum; <br>
 Console.Write("\nEnter the decimal number: "); <br>
 InputNum = Convert.ToInt32(Console.ReadLine()); <br>
 Console.WriteLine("\nBinary equivalent of {0}: {1}", InputNum,  Convert.ToString(InputNum, 2)); <br>
 GrayNum = getGray(InputNum); <br>
 Console.WriteLine("\nGray Code equivalent of {0}: {1}", InputNum,  Convert.ToString(GrayNum, 2)); <br>
 } <br>
 } <br>
} <br>

Output:<br>
![Screenshot (4)](https://user-images.githubusercontent.com/97940277/154628717-e1674fe3-eb2f-4265-80ca-84070f18b137.png)<br>

************************************************************************************************************************************************
5.Write a C# program to calculate volume of 2 boxes and find the resultant volume  after addition of 2 boxes by implementing operator overloading.<br> 
************************************************************************************************************************************************
using System;<br>
namespace Exercises<br>
{<br>
    class Box<br>
    {<br>
        float width;<br>
        float height;<br>
        float length;<br>
        public float Volume<br>
        {<br>
            get { return width * height * length; }<br>
        }<br>
        public Box(float width, float height, float length)<br>
        {<br>
            this.width = width;<br>
            this.height = height;<br>
            this.length = height;<br>
        }<br>
        public static float operator +(Box box1, Box box2)<br>
        {<br>
            return box1.Volume + box2.Volume;<br>
        }<br>
        public override String ToString()<br>
        {<br>
            return "box with width " + width + ", height " + height + " and length " + length;<br>
        }<br>
    }<br>
    class OperatorOverloading<br>
    {<br>
        public static void Main()<br>
        {
            Box box1 = new Box(10, 20, 30);<br>
            Box box2 = new Box(25, 32, 15);<br>
            Console.WriteLine("Volume of {0} is: {1}", box1, box1.Volume); Console.WriteLine("Volume of {0} is: {1}", box2, box2.Volume);<br>

        Console.WriteLine("Volume after adding boxes: {0}", box1 + box2);<br>
        }<br>
    }<br>
}<br>

Output:<br>
![Screenshot (6)](https://user-images.githubusercontent.com/97940277/154629462-8db67286-8206-4499-a9f4-332a2a467ab8.png)<br>

********************************************************************************************************************************************
6. Write a C# Program to Implement Principles of Delegates (converting input string to  uppercase first, last and entire string). <br>
********************************************************************************************************************************************
using System; <br>
namespace Exercises <br>
{ <br>
 class Delegates<br><br> 
 { <br>
 delegate string UppercaseDelegate(string input); <br>
 static string UppercaseFirst(string input)<br> 
 { <br>
 char[] buffer = input.ToCharArray(); <br>
 buffer[0] = char.ToUpper(buffer[0]); <br>
 return new string(buffer); <br>
 } <br>
 static string UppercaseLast(string input) <br>
 { <br>
 char[] buffer = input.ToCharArray(); <br>
 buffer[buffer.Length - 1] = char.ToUpper(buffer[buffer.Length - 1]);  return new string(buffer); <br>
 } <br>
 static string UppercaseAll(string input) <br>
 { <br>
 return input.ToUpper(); <br>
 } <br>
 static void WriteOutput(string input, UppercaseDelegate del) <br>
 { <br>
 Console.WriteLine("Input String: {0}", input); <br>
 Console.WriteLine("Output String: {0}", del(input)); <br>
 } <br>
 static void Main() <br>
 { <br>
 WriteOutput("tom ", new UppercaseDelegate(UppercaseFirst)); <br>
 WriteOutput("tom", new UppercaseDelegate(UppercaseLast)); <br>
 WriteOutput("tom", new UppercaseDelegate(UppercaseAll)); <br>
 Console.ReadLine(); <br>
 } <br>
 } <br>
}<br>

Output:<BR>
 ![Screenshot (8)](https://user-images.githubusercontent.com/97940277/154631240-41ca6a79-7405-492b-92fa-a0480c9c1587.png)

 ****************************************************************************************************************************
 7. Write a C# program to Generate Register Number automatically for 100 Students using Static Constructor. <br>
 ****************************************************************************************************************************
 using System; <br>
namespace Register_number <br>
{ <br>
    class Register_number <br>
    { <br>
        int regNo; <br>
        static int startNum; <br>
        static Register_number() <br>
        { <br>
            startNum=202110000; <br>
         } <br>
        Register_number() <br>
        { <br>
            regNo=++startNum; <br>
        } <br>
        public static void Main(string[]args) <br>
        { <br>
            for(int i=0;i<100;i++) <br>
            { <br>
                Register_number Student=new Register_number(); <br>
                Console.WriteLine("Student {0} : {1}",i+1,Student.regNo); <br>
            } <br>
        } <br>
    } <br>
} <br>
OUTPUT: <br>
![image](https://user-images.githubusercontent.com/97940333/154635181-0f940813-32eb-4881-879c-99d15b2591c8.png)<br>
 
 [image](https://user-images.githubusercontent.com/97940333/154635531-cfbb395d-b6c3-4aa0-b400-68bb18972dd2.png)

 ************************************************************************************************************************************************
 8. Write aC# program to find the frequency of the word "is" in a given sentence. <br>
************************************************************************************************************************************************
using System;
namespace Frequency <br>
{ <br>
    class Frequency <br>
    { <br>
        static void Main(string[] args) <br>
        { <br>
            int count = 0; <br>
            string inputString; <br>
            Console.WriteLine("\n_____________Frequency of word 'is'________________"); <br>
            Console.Write("\n Enter the input string:"); <br>
            inputString = Console.ReadLine(); <br>
            char[] separator = { ',',' ','.','!','\n' }; <br>
            string testString = inputString.ToLower(); <br>
            String[] outcomes = testString.Split(separator); <br>
            foreach(String s in outcomes) <br>
            { <br>
                Console.WriteLine(s); <br>
                if (s == "is") <br>
                    count++; <br>
            } <br>
            Console.WriteLine("\n Number of 'is' in " + inputString + "is:" + count); <br>
        } <br>
    } <br>
} <br>
 OUTPUT: <br>
 ![image](https://user-images.githubusercontent.com/97940333/154636503-6710c374-c37a-425f-819e-f2e7cea50b0a.png)

 ********************************************************************************************************************************
9. Write a C# program that benchmarks 2D,jagged array allocation. <br>
**********************************************************************************************************************************
 using System; <br>
 using Benchmark_Allocation <br>
 namespace Benchmark_Allocation <br>
{ <br>
    class Benchmark_Allocation <br>
    { <br>
        const int max= 100000; <br>
        static void Main(string[] args) <br>
        { <br>
            var Arr2D = new int[100, 100]; <br>
            var ArrJagged = new int[100][]; <br>
            for (int i = 0; i < 100; i++) <br>
            { <br>
                ArrJagged[i] = new int[100]; <br>
            } <br>
            var Stopwatch2D = Stopwatch.StartNew(); <br>
            for (int i = 0; i < max; i++) <br>
            { <br>
                for (int j = 0; j < 100; j++) <br>
                { <br>
                    for (int k = 0; k < 100; k++) <br>
                    { <br>
                        Arr2D[j, k] = k; <br>
                    } <br>
                } <br>
            } <br>
            Stopwatch2D.Stop(); <br>
            var StopwatchJagged = Stopwatch.StartNew(); <br>
            for (int i = 0; i < max; i++) <br>
            { <br>
                for (int j = 0; j < 100; j++) <br>
                { <br>
                    for (int k = 0; k < 100; k++) <br>
                    { <br>
                        ArrJagged[j][k] = k; <br>
                    } <br>
                } <br> 
            } <br>
            StopwatchJagged.Stop(); <br>
            Console.WriteLine("\n Time taken for allocation in case of 2D array:"); <br>
             Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + "milliseconds"); <br>
            Console.WriteLine("\n Time taken for allocation in case of Jagged array:"); <br>
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + "milliseconds"); <br>
        } <br>
    } <br>
} <br>
OUTPUT: <br>
 ![image](https://user-images.githubusercontent.com/97940333/154637991-c202802c-3fa3-4028-b687-3cc6bb68fbbe.png)
 
 ************************************************************************************************************************************
 10. Write a c# program to print fibonacci series without using recursion and using recursion. <br>
**************************************************************************************************************************************
 using System; <br>
namespace Fibonacci <br>
{ <br>
 public   class Fibonacci <br>
    { <br>
       public static void Main(string[] args) <br>
        { <br>
            int n1 = 0, n2 = 1, n3, i, number; <br>
            Console.Write("Enter the number of elements:"); <br>
            number = int.Parse(Console.ReadLine()); <br>
            Console.Write(n1 + "" + n2 + ""); <br>
            for(i=2;i<number;++i) <br>
            { <br>
                n3 = n1 + n2; <br>
                Console.Write(n3 + " "); <br>
                n1 = n2; <br>
                n2 = n3; <br>
            } <br>
        } <br>
    } <br>
} <br>
 OUTPUT: <br>
![image](https://user-images.githubusercontent.com/97940333/155659227-f6884f19-6863-412e-b590-4b80b230f5a0.png)

 ************************************************************************************************************************************************
 11. Write a c# program to check prime number. <br>
**************************************************************************************************************************************************
 using System; <br>
public class PrimeNumberExample <br>
{ <br>
    public static void Main(string[] args) <br>
    { <br>
        int n, i, m = 0, flag = 0; <br>
        Console.Write("Enter the Number to check Prime: "); <br>
        n = int.Parse(Console.ReadLine()); <br>
        m = n / 2; <br>
        for (i = 2; i <= m; i++) <br>
        { <br>
            if (n % i == 0) <br>
            { <br>
                Console.Write("Number is not Prime."); <br>
                flag = 1; <br>
                break; <br>
            } <br>
        } <br>
        if (flag == 0) <br>
            Console.Write("Number is Prime."); <br>
    } <br>
} <br>
 OUTPUT: <br>
![image](https://user-images.githubusercontent.com/97940333/155661030-4cb66e8b-ef8d-4470-abd1-063f7a441711.png) <br>
 
 [image](https://user-images.githubusercontent.com/97940333/155661299-e95ab4e9-9a1b-427a-a95e-8c0144b1829d.png)

 ************************************************************************************************************************************************
 12. Write a c# Program to check palindrome number. <br>
**************************************************************************************************************************************************
 using System; <br>
public class PalindromeExample  <br>
{ <br>
    public static void Main(string[] args) <br>
    { <br>
        int n, r, sum = 0, temp; <br>
        Console.Write("Enter the Number: "); <br>
        n = int.Parse(Console.ReadLine()); <br>
        temp = n; <br>
        while (n > 0) <br>
        { <br>
            r = n % 10; <br>
            sum = (sum * 10) + r; <br>
            n = n / 10; <br>
        } <br>
        if (temp == sum) <br>
            Console.Write("Number is Palindrome."); <br>
        else <br>
            Console.Write("Number is not Palindrome"); <br>
    } <br>
} <br>
 OUTPUT: <br>
 ![image](https://user-images.githubusercontent.com/97940333/155662868-b019525d-586b-4cab-81f5-0dc1ebcf3335.png)<br>
 
 ![image](https://user-images.githubusercontent.com/97940333/155662954-ce9e552f-75ee-47ee-8c6b-81eacb2af3c7.png)

 ********************************************************************************************************************************************************
 13. Write a c# program to print factorial of a number. <br>
*********************************************************************************************************************************************************
 using System; <br>
public class FactorialExample <br>
{ <br>
    public static void Main(string[] args) <br>
    { <br>
        int i, fact = 1, number; <br>
        Console.Write("Enter any Number: "); <br>
        number = int.Parse(Console.ReadLine()); <br>
        for (i = 1; i <= number; i++) <br>
        { <br>
            fact = fact * i; <br>
        } <br>
        Console.Write("Factorial of " + number + " is: " + fact); <br>
    } <br>
} <br>
OUTPUT: <br>
 ![image](https://user-images.githubusercontent.com/97940333/155664316-1998f10a-b116-40bf-b0e9-2fbc1724ee52.png)


 ****************************************************************************************************************************************************
 14. Write a c# program to print sum of digits. <br>
 *****************************************************************************************************************************************************
 using System; <br>
public class SumExample <br>
{ <br>
    public static void Main(string[] args) <br>
    { <br>
        int n, sum = 0, m; <br>
        Console.Write("Enter a number: "); <br>
        n = int.Parse(Console.ReadLine()); <br>
        while (n > 0) <br>
        { <br>
            m = n % 10; <br>
            sum = sum + m; <br>
            n = n / 10; <br>
        } <br>
        Console.Write("Sum is= " + sum); <br>
    } <br>
} <br>
 OUTPUT: <br>
 ![image](https://user-images.githubusercontent.com/97940333/155667426-1ec4975c-9713-4e4c-b906-6f1a935f52bd.png)<br>
 
 [image](https://user-images.githubusercontent.com/97940333/155667517-b8601215-7e5e-48d4-b212-1f8ff0e8041d.png)

 ********************************************************************************************************************************************************
15. Write a c# program to reverse given number. <br>
 *********************************************************************************************************************************************************
 using System; <br>
public class ReverseExample  <br>
{  <br>
    public static void Main(string[] args)  <br>
    {  <br>
        int n, reverse = 0, rem;  <br>
        Console.Write("Enter a number: ");  <br>
        n = int.Parse(Console.ReadLine());  <br>
        while (n != 0)  <br>
        {  <br>
            rem = n % 10;  <br>
            reverse = reverse * 10 + rem;  <br>
            n /= 10;  <br>
        }  <br>
        Console.Write("Reversed Number: " + reverse);  <br>
    }  <br>
}  <br>
 OUTPUT:  <br>
 ![image](https://user-images.githubusercontent.com/97940333/155668608-05594aa4-f09d-4934-a046-1b3905335a00.png)

 ************************************************************************************************************************************************************
 16. Write a c# program to swap two numbers without third variable. <br>
 ************************************************************************************************************************************************************
 using System; <br>
public class SwapExample   <br>
{  <br>
    public static void Main(string[] args)  <br>
    {  <br>
        int a = 5, b = 10;  <br>
        Console.WriteLine("Before swap a= " + a + " b= " + b);  <br>
        a = a * b; //a=50 (5*10)   <br>
        b = a / b; //b=5 (50/10)   <br>    
        a = a / b; //a=10 (50/5)   <br>  
        Console.Write("After swap a= " + a + " b= " + b); <br>
    } <br>
} <br>
 OUTPUT: <br>
 ![image](https://user-images.githubusercontent.com/97940333/155669712-2af6101f-2a36-4c5e-95e2-f8fc9b8a701c.png)

********************************************************************************************************************************************
 17. Write a c# program to find the sum of the values on diagonal of the matrix . <br>
 ********************************************************************************************************************************************
 using System; <br>
namespace Sum_Of_Diagonals <br>
{ <br>
    class Sum_Of_Diagonals <br>
    { <br>
        static void Main(string[] args) <br>
        { <br>
            int MaxRow, MaxCol, Sum = 0; <br>
            int[,] Matrix; <br>
            Console.WriteLine("\n______________SUM OF DIAGONAL OF A MATRIX____________\n"); <br>
            Console.Write("\n Enter the number of rows:"); <br>
            MaxRow = Convert.ToInt32(Console.ReadLine()); <br>
            Console.Write("\n Enter the number of columns:"); <br>
            MaxCol = Convert.ToInt32(Console.ReadLine()); <br>
            if(MaxRow!=MaxCol) <br>
            { <br>
                Console.WriteLine("\n The Dimensions entered are not of Square Matrix,"); <br>
                Console.WriteLine("\n Exiting the Program.."); <br>
                return; <br>
            } <br>
            Matrix = new int[MaxRow, MaxCol]; <br>
            for(int i=0;i<MaxRow;i++) <br>
            { <br>
                for(int j=0;j<MaxCol;j++) <br>
                { <br>
                    Console.Write("\n Enter the ({0},{1}) the element of the matrix:", (i + 1), (j + 1)); <br>
                    Matrix[i, j] = Convert.ToInt32(Console.ReadLine()); <br>
                } <br>
            } <br>
            Console.WriteLine("\n The entered Matrix is:"); <br>
            for(int i=0;i<MaxRow;i++) <br>
            { <br>
                for(int j=0;j<MaxCol;j++) <br>
                { <br>
                    Console.Write(" " + Matrix[i, j]); <br>
                    if(i==j) <br>
                    { <br>
                        Sum += Matrix[i, j]; <br>
                    } <br>
                } <br>
                Console.WriteLine(); <br>
            } <br>
            Console.WriteLine("\n The Sum of Diagonal is" + Sum); <br>
        } <br>
    } <br>
} <br>
 OUTPUT: <br>
 ![image](https://user-images.githubusercontent.com/97940333/155672233-f9964754-3e13-4010-85ad-60e8f0358ccd.png)

 ****************************************************************************************************************************************************************
 18. Write a C# program to create a File  check the Existence of a File and Read the contents of the File. <br>
 ****************************************************************************************************************************************************************
 using System; <br>
using System.IO; <br>
namespace File_Read <br>
{ <br>
class File_Read <br>
{ <br>
 public static void Main() <br>
 { <br>
 string fileName; <br>
 while (true) <br>
 { <br>
 Console.WriteLine("\n_______________MENU____________________\n"); <br>
 Console.WriteLine("\n 1.Create a File"); <br>
 Console.WriteLine("\n 2.Existence of the File"); <br>
 Console.WriteLine("\n 3.Read the contents of the File"); <br>
 Console.WriteLine("\n 4.Exit"); <br>
 Console.WriteLine("\n Enter your choice:"); <br>
 int ch = int.Parse(Console.ReadLine()); <br>
  switch (ch) <br>
 { <br>
 case 1: <br>
 Console.Write("\n Enter the file name to create:"); <br>
 fileName = Console.ReadLine(); <br>
 Console.WriteLine("\n Write the contents to the File:\n"); <br>
 string r = Console.ReadLine(); <br>
 using (StreamWriter fileStr = File.CreateText(fileName)) <br>
 { <br>
 fileStr.WriteLine(r); <br>
 } <br>
 Console.WriteLine("File is Created.."); <br>
 break;  <br>

 case 2:  
 Console.Write("\n Enter the file name:");  
 fileName = Console.ReadLine();  
 if (File.Exists(fileName))  
 {  
 Console.WriteLine("File exists..");  
 }  
 else  
{  
Console.WriteLine("File does not exist in the current directory!");  
}  <br>
break;  
 case 3:  
 Console.Write("Enter the file name to read the contents\n");  
 fileName = Console.ReadLine();  
 if (File.Exists(fileName))  
 {  
 using (StreamReader sr = File.OpenText(fileName))  
 {  
 string s = " ";  
 Console.WriteLine("Here is the content of the file:");  
 while ((s = sr.ReadLine()) != null)  
 {  
 Console.WriteLine(s);  
 }  
 Console.WriteLine(" ");  
 }  
  }  
 else  
 {  
 Console.WriteLine("File does not exists");  
 } 
 break;  

 case 4:  
 Console.WriteLine("\n Exiting....");  
 return;  

 default:  
 Console.WriteLine("\n Invalid choice");  
 break;  
 }  
 }  
 }  
 }  
}  
 
 OUTPUT:  <br>
 ![image](https://user-images.githubusercontent.com/97940333/157633093-48707e89-6bfc-49af-93da-f8c9a71e1da6.png)


************************************************************************************************************************************************
 19. Write a c# program to Perform File Comparison. <br>
 ************************************************************************************************************************************************
 using System; <br>
using System.IO; <br>
namespace FileRead <br>
{ <br>
    class FileRead <br>
    { <br>
       public static void Main() <br>
        { <br>
            string file1; <br>
            string file2; <br>
            Console.Write("Enter the first file path:"); <br>
            file1 = Console.ReadLine(); <br>
            Console.Write("Enter the second file path:"); <br>
            file2 = Console.ReadLine(); <br>
            if(!File.Exists(file1)) <br>
            { <br>
                Console.WriteLine("First file does not exist!"); <br>
            } <br>
            else if(! File.Exists(file2)) <br>
            { <br>
                Console.WriteLine("Second file does not exist!"); <br>
            } <br>
            else if(File.ReadAllText(file1)==File.ReadAllText(file2)) <br>
            { <br>
                Console.WriteLine("Both files contain the same cuurent"); <br>
            } <br>
            else <br>
            { <br>
                Console.WriteLine("Contents of files are not same"); <br>
            } <br>
        } <br>
    } <br>
} <br>
 OUTPUT: <br>
 ![image](https://user-images.githubusercontent.com/97940333/156504786-26e0f3ee-957c-41b7-a4e8-9963df5a6ef9.png)
 
<br>![image](https://user-images.githubusercontent.com/97940333/156506239-7375834d-2a54-4562-aeb0-a2bb53084be2.png)
 
<br>![image](https://user-images.githubusercontent.com/97940333/156506318-d818f678-05e4-4312-b9d5-da21c4014286.png)
 
<br>![image](https://user-images.githubusercontent.com/97940333/156506424-e40f99ff-fe87-48da-9902-545f6508af15.png)
 
<br>![image](https://user-images.githubusercontent.com/97940333/156506594-a89f7a08-1289-4825-8374-0a2df14a66fe.png)
 
 ************************************************************************************************************************
 20. Write a c# program to Implement IComparable Interface. <br>
 *************************************************************************************************************************
 using System; <br>
namespace Exercises <br>
{ <br>
    class Fraction :IComparable <br>
    { <br>
        int z, n; <br>
        public Fraction(int z, int n) <br>
        { <br>
            this.z = z; <br>
            this.n = n; <br>
        } <br>
        public static Fraction operator +(Fraction a, Fraction b) <br>
        { <br>
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n); <br>
        } <br>
        public static Fraction operator *(Fraction a, Fraction b) <br>
        { <br>
            return new Fraction(a.z * b.z, a.n * b.n); <br>
        } <br>
        public int CompareTo(object obj) <br>
        { <br>
            Fraction f = (Fraction)obj; <br>
            if ((float)z / n < (float)f.z / f.n) <br>
                return -1; <br>
            else if ((float)z / n > (float)f.z / f.n) <br>
                return 1; <br>
            else <br>
                return 0; <br>
        } <br>
        public override string ToString() <br>
        { <br>
            return z + "/" + n; <br>
        } <br>
    } <br>
    class ICompInterface <br>
    { <br>
        public static void Main() <br>
        { <br>
        Fraction[] a = { <br>
 new Fraction(5,2), <br>
 new Fraction(29,6), <br>
 new Fraction(4,5), <br>
 new Fraction(10,8), <br>
 new Fraction(34,7) <br>
 }; <br>
            Array.Sort(a); <br>
            Console.WriteLine("Implementing the IComparable Interface in " + "Displaying  Fractions : "); <br>
            foreach (Fraction f in a) <br>
            { <br>
                Console.WriteLine(f + " "); <br>
            } <br>
            Console.WriteLine(); <br>
            Console.ReadLine(); <br>
        } <br>
    } <br>
} <br>
 OUTPUT: <br>
![image](https://user-images.githubusercontent.com/97940333/156504541-4742834d-6c69-41b4-9558-7144b585e235.png)

 ************************************************************************************************************************
 21.Write a c# program to create ThreadPool. <br>
 *************************************************************************************************************************
using System; <br>
using System.Threading;  <br>
namespace Exercises  <br>
{  <br>
    class ThreadPoolProg  <br>
    {  <br>
        public void ThreadFun1(object obj)  <br>
        {  <br>
            int loop = 0;  <br>
            for (loop = 0; loop <= 4; loop++)  <br>
            {  <br>
                Console.WriteLine("Thread1 is executing");  <br>
            }  <br>
        }  <br>
        public void ThreadFun2(object obj)  <br>
        {  <br>
            int loop = 0;  <br>
            for (loop = 0; loop <= 4; loop++)  <br>
            {  <br>
                Console.WriteLine("Thread2 is executing");  <br>
            }  <br>
        }  <br>
        public static void Main()  <br>
        {  <br>
            ThreadPoolProg TP = new ThreadPoolProg();  <br>
            for (int i = 0; i < 2; i++)  <br>
            {  <br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1)); ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));  <br>
            }  <br>
            Console.ReadKey();  <br>
        }  <br>
    }  <br>
}  <br>
 OUTPUT:  <br>
 ![image](https://user-images.githubusercontent.com/97940333/156508199-ac5f65a3-6ddb-402a-addd-a261a375c406.png)

 ****************************************************************************************************************************************
22. Write  a program to demonstrate error handling using Try , Ctch and Finally block. <br>
 ****************************************************************************************************************************************
 using System; <br>
namespace ExceptionHandling  <br> 
    class ExceptionHandling  <br>
    {  <br>
        static void Main(string[] args)  <br>
        {  <br>
            Age a = new Age();  <br>
            try  <br>
            {  <br>
                a.displayAge();  <br>
            }  <br>
            catch (AgeIsNegativeException e)  <br>
            {  <br>
                Console.WriteLine("AgeIsNegativeException: {0}", e.Message);  <br>
            }  <br>
            finally  <br>
            {  <br>
                Console.WriteLine("Execution of Finally block is done.");  <br>
            }  <br>
        }  <br>
    }  <br>
}  <br>
public class AgeIsNegativeException : Exception  <br>
{  <br>
    public AgeIsNegativeException(string message) : base(message)  <br>
    {  <br>
    }  <br>
}  <br>
public class Age  <br>
{  <br>
    int age = -5;  <br>
    public void displayAge()  <br>
    {  <br>
        if (age < 0)  <br>
        {  <br>
            throw (new AgeIsNegativeException("Age cannot be negative"));  <br>
        }  <br>
        else  <br>
        {  <br>
            Console.WriteLine("Age is: {0}", age);  <br>
        }  <br>
    }  <br>
}  <br>
 OUTPUT: <br>
 ![image](https://user-images.githubusercontent.com/97940333/156510179-9793d13e-30bf-4e6f-8f63-d157f07103c5.png)

 ************************************************************************************************************************************************
23. C# program to Perform Reversal, Padding and Trimming Operations on string. <br>
************************************************************************************************************************************************
 using System; <br>
using System.Collections.Generic; <br>
using System.ComponentModel; <br>
using System.Data; <br>
using System.Drawing; <br>
using System.Linq; <br>
using System.Text; <br>
using System.Threading.Tasks; <br>
using System.Windows.Forms; <br>

namespace String_Operations <br>
{ <br>
 public partial class Form1 : Form <br>
  { <br>
  public Form1() <br> 
  { <br>
  InitializeComponent(); <br>
 } <br>
private void btnrev_Click(object sender, EventArgs e) <br>
  { <br>
 string inputString, revstr = ""; <br>
 nt Length; <br>
 inputString = txtInput.Text; <br>
  Length = inputString.Length - 1; <br>
   while (Length >= 0) <br>
   { <br>
   Length--; <br>
   } <br>
   MessageBox.Show("Reverse String Is : " + revstr, "Result"); <br>
   } <br>

   private void btntrim_Click(object sender, EventArgs e) <br>
   { <br>
   string inputString; <br>
   inputString = txtInput.Text; <br>
   MessageBox.Show("The String After Trimming : " + inputString.Trim(), "Result"); <br>
   } <br>

   private void btnpad_Click(object sender, EventArgs e) <br>
  { <br>
 string inputString; <br>
 inputString = txtInput.Text; <br>
 inputString = inputString.PadLeft(10, '*'); <br>
 inputString = inputString.PadRight(15, '*'); <br>
 MessageBox.Show("String After Padding : " + inputString, "Result"); <br>
  } <br>
 } <br>
} <br>
 
 OUTPUT: <br>
 ![image](https://user-images.githubusercontent.com/97940333/158742138-e52f6a0d-6c3f-465c-8375-6d692095df59.png)<br>

![image](https://user-images.githubusercontent.com/97940333/157820572-a67eb8c9-7feb-4e3d-a5f9-9495e9c51650.png) <br>
 
 ![image](https://user-images.githubusercontent.com/97940333/157820670-6267d2d0-06ba-4b6d-9684-b646760b7f49.png) <br>
 
 
 ![image](https://user-images.githubusercontent.com/97940333/157820830-7b1b6711-d78b-41ea-bb2a-2f8e772cb753.png)

 ********************************************************************************************************************************
24. C# Program to convert digits to words. <br>
 ********************************************************************************************************************************
 using System; <br>
using System.Collections.Generic; <br>
using System.ComponentModel; <br>
using System.Data; <br>
using System.Drawing; <br>
using System.Linq; <br>
using System.Text; <br>
using System.Threading.Tasks; <br>
using System.Windows.Forms; <br>

namespace Digits <br>
{ <br>
 public partial class Form1 : Form <br>
 { <br>
  public Form1() <br>
  { <br>
   InitializeComponent(); <br>
    } <br>

 private void button1_Click(object sender, EventArgs e) <br>
   { <br>
     lbl_words.Text = NumtoWord(long.Parse(txt_num.Text)); <br>
     } <br>
    public string NumtoWord(long number) <br>
    { <br>
    string word = ""; <br>
   if (number == 0) <br>
   { <br>
    return "Zero"; <br>
   } <br>
   if (number < 0) <br>
   { <br>
   return "Minus" + Math.Abs(number); <br>
  } <br>
  if (number / 10000000 > 0) <br>
  { <br>
    word += NumtoWord(number / 10000000) + "Corer"; number %= 10000000; <br>
   } <br>

   if (number / 100000 > 0) <br>
  { <br>
   word += NumtoWord(number / 100000) + "Lacs"; <br>
  number %= 100000; <br>
  } <br>
  if (number / 1000 > 0) <br>
  { <br>
  word += NumtoWord(number / 1000) + "Thousand"; <br>
  number %= 1000; <br>
  } <br>
  if (number / 100 > 0) <br>
  { <br>
  word += NumtoWord(number / 100) + "Hundred"; <br>
  number %= 100; <br>
 } <br>
 if (number > 0) <br>
 { <br>
 string[] units = new string[] { "Zero", "One", "Two", "Three", "Four", "Five", "Six", "Seven", "Eight", "Nine", "Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen", "Seventeen", "Eighteen", "Nineteen" }; <br>
 string[] Tens = new string[] { "Zero", "Ten", "Twenty", "Thirty", "Fourty", "Fifty", "Sixty", "Seventy", "Eighty", "Ninety" }; <br>
  if (number < 20) <br>
  { <br>
  word += units[number]; <br>
  } <br>
  else <br>
  { <br>
   word += Tens[number / 10]; <br>
  if (number % 10 > 0) <br>
  { <br>
  word += units[number % 10]; <br>
 } <br>
 } <br>
 } <br>
 return word; <br>
 } <br>
 } <br>
} <br>

OUTPUT: <br>
![image](https://user-images.githubusercontent.com/97940333/158741672-b6ffb632-fa7d-45b8-b40e-8c2f1c982545.png) <br>
 
 ![image](https://user-images.githubusercontent.com/97940333/158741923-f4418976-ea16-41ca-b945-a52dba501dfd.png) <br>

****************************************************************************************************************************************
 25. C# Program to create a Progress Bar Control
 ****************************************************************************************************************************************
 using System; <br>
using System.ComponentModel;<br>
using System.Threading; <br>
using System.Windows.Forms; <br>

namespace Progress_Bar <br>
{ <br>
 public partial class Form1 : Form <br>
 { <br>
 public Form1() <br>
 { <br>
  InitializeComponent(); <br>
 } <br>

  private void Form1_Load(object sender, EventArgs e) <br>
   { <br>
  backgroundWorker1.WorkerReportsProgress = true; <br>
  backgroundWorker1.RunWorkerAsync(); <br>
  } <br>

  private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e) <br>
 { <br>
  for (int i = 1; i <= 100; i++) <br>
 { <br>
 Thread.Sleep(50); <br>
 backgroundWorker1.ReportProgress(i); <br>
 } <br>
 } <br>
  private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e) <br>
  { <br>
  progressBar1.Value = e.ProgressPercentage; <br>
  this.Text = "Progress: " + e.ProgressPercentage.ToString() + "%"; <br>
  } <br>
 } <br>
}  <br>

 OUTPUT: <br>
 ![image](https://user-images.githubusercontent.com/97940333/158745251-e7a6d71f-dc9d-4058-8483-621cb96cd82c.png) <br>
 
 ![image](https://user-images.githubusercontent.com/97940333/158745536-4e5cf95b-c063-44a3-b79d-96ea2daeb51c.png)<br>

 ****************************************************************************************************************************************
 26. Develop a winform application to create flat clock. <br>
 ****************************************************************************************************************************************
sing System; <br>sing System; <br>
using System.Collections.Generic; <br>
using System.ComponentModel; <br>
using System.Data; <br>
using System.Drawing; <br>
using System.Linq; <br>
using System.Text; <br>
using System.Threading.Tasks; <br>
using System.Windows.Forms; <br>
namespace Winform <br>
{ <br>
 public partial class Form1 : Form <br>
 { <br>
  public Form1() <br>
  { <br>
  InitializeComponent(); <br>
  timer1.Start(); <br>
  } <br>

 private void Form1_Load(object sender, EventArgs e) <br>
 { <br>
 System.Timers.Timer timer = new System.Timers.Timer(); <br>
 timer.Interval = 1000;//1s  <br>
  timer.Elapsed += Timer_Elapsed; <br>
 timer.Start(); <br>
  } <br>
 private void Timer_Elapsed(object sender, System.Timers.ElapsedEventArgs e) <br>
 { <br>
cularProgressBar1.Invoke((MethodInvoker)delegate <br>
 { <br>
 circularProgressBar1.Text = DateTime.Now.ToString("hh:mm:ss"); circularProgressBar1.SubscriptText = DateTime.Now.ToString("tt");//AM or PM  });  <br>
 }); <br>
 } <br>
 } <br>

} <br>

 OUTPUT: <br>
 ![image](https://user-images.githubusercontent.com/97940333/158944460-57a7afb8-1a58-404e-a5e5-1dc845b96dfe.png) <br>
 
 ![image](https://user-images.githubusercontent.com/97940333/158944634-defed55a-9b9d-443b-95ef-3444ea9fa37d.png) <br>

****************************************************************************************************************************************************
 27.  C# program to perform a number guessing game. <br>
 ****************************************************************************************************************************************************
 using System;<br>
using System.Drawing;<br>
using System.Windows.Forms;<br>

namespace game<br>
{<br>
 public partial class Form1 : Form<br>
 {<br>
 // Intialising component  <br>
 static Random r = new Random();<br>
  int value;<br>
  int guessnum;<br>
  int win = 10;<br>
  int guess = 1;<br>
  Button button1;<br>
  TextBox textBox1;<br>
  RichTextBox richTextBox1;<br>
  RichTextBox richTextBox2;<br>
  Label label4;<br>
 public Form1()<br>
 {<br>
 InitializeComponent();<br>
  {<br>
  value = r.Next(10);<br>
  this.Controls.Clear();<br>
  this.BackColor = Color.SkyBlue;<br>
  this.AutoSize = true;<br>
  this.Padding = new Padding(16);<br>
   Label label = new Label();<br>
  label.Text = "Pick a number between 1 and 100"; label.Bounds = new Rectangle(10, 20, 340, 40); label.Font = new Font("Arial", 16);<br>
 textBox1 = new TextBox();<br>
  textBox1.Bounds = new Rectangle(20, 50, 120, 80); textBox1.Font = new Font("Arial", 24);<br>

  button1 = new Button();<br>
 button1.Text = " Check Your Guess ";<br>
 button1.Bounds = new Rectangle(160, 50, 120, 40);<br>
 button1.BackColor = Color.LightGray;<br>
 button1.Click += new EventHandler(button1_Click);<br>
 Label label2 = new Label();<br>
 label2.Text = "Low Guess";<br>
 label2.Bounds = new Rectangle(20, 150, 160, 40); label2.Font = new Font("Arial", 18);<br>
  richTextBox1 = new RichTextBox();<br>
 richTextBox1.Bounds = new Rectangle(20, 190, 160, 300); richTextBox1.Font = new Font("Arial", 16);<br>
 Label label3 = new Label();<br>
 label3.Text = "High Guess";<br>
 label3.Bounds = new Rectangle(180, 150, 160, 40); label3.Font = new Font("Arial", 18);<br>
 richTextBox2 = new RichTextBox();<br>
 richTextBox2.Bounds = new Rectangle(180, 190, 160, 300); richTextBox2.Font = new Font("Arial", 16);<br>
 label4 = new Label();<br>
 label4.Bounds = new Rectangle(20, 100, 340, 40); label4.Font = new Font("Arial", 16);<br>
 this.Controls.Add(label);<br>
 this.Controls.Add(textBox1);<br>
 this.Controls.Add(button1);<br>
 this.Controls.Add(label4);<br>
 this.Controls.Add(label2);<br>
 this.Controls.Add(label3);<br>
 this.Controls.Add(richTextBox1);<br>
this.Controls.Add(richTextBox2);<br>
 }<br>
 }<br>
 private void button1_Click(object sender, EventArgs e)<br>
 {<br>
 // Coding of game  <br>
 if (textBox1.Text == "")<br>
 {<br>
 return;<br>
 }<br>
 guessnum = Convert.ToInt32(textBox1.Text); textBox1.Text = String.Empty;<br>
 if (win >= 0)<br>
 { <br>
 if (guessnum == value)<br>
  {<br>
  MessageBox.Show("You have guessed the number! \n The number was " + value); InitializeComponent();<br>
  }<br>
  else if (guessnum < value)<br>
  {<br>
  richTextBox1.Text += guessnum + "\n";<br>
  label4.Text = "wrong Guess and number of guesses left are " + (10 - guess);<br>
  }<br>
  else if (guessnum > value)<br>
  {<br>
  richTextBox2.Text += guessnum + "\n";<br>
  label4.Text = "wrong Guess and number of guesses left are " + (10 - guess);<br>
  }<br>
 guess++;<br>
 win--;<br>
 }<br>
 if (guess == 11)<br>
 {<br>
 label4.Text = "You loose,Correct Guess is " + value;<br>
}<br>
}<br>
private void Form1_Load(object sender, EventArgs e)<br>
{<br>
}<br>
}<br>
}<br>
 
 OUTPUT:<br>
 ![image](https://user-images.githubusercontent.com/97940333/161211079-afee86af-1c86-443b-aa8d-5675639ede52.png) <br>
 
 ![image](https://user-images.githubusercontent.com/97940333/161211264-645a6f35-fe4d-49cf-b0db-753daf49bac7.png) <br>
 
 ![image](https://user-images.githubusercontent.com/97940333/161211473-15bd7640-c761-4e5a-8d27-a449999d4a35.png) <br>

************************************************************************************************************************************
 28.Develop an application to create a notepad. <br>
 ************************************************************************************************************************************
 using System; <br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br><br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace Notepad9<br>
{<br>
 public partial class Form1 : Form<br>
 {<br>
 private string fileName;<br>
 private RichTextBox txtContent; <br>
 private ToolBar toolBar; <br>

 private void Form1_Load(object sender, EventArgs e) <br>
 { <br>

 } <br>
 internal Form1() <br>
 { <br>
 fileName = null; <br>
 initializeComponents(); <br>
 } <br>
 void initializeComponents() <br>
 { <br>
 this.Text = "My notepad"; <br>
 this.MinimumSize = new Size(600, 450); <br>
 this.FormClosing += new FormClosingEventHandler(NotepadClosing); this.MaximizeBox = true; <br>
 toolBar = new ToolBar(); <br>
 toolBar.Font = new Font("Arial", 16); <br>
 toolBar.Padding = new Padding(4); <br>
 toolBar.ButtonClick += new ToolBarButtonClickEventHandler(toolBarClicked); <br>
 ToolBarButton toolBarButton1 = new ToolBarButton(); <br>
 ToolBarButton toolBarButton2 = new ToolBarButton(); <br>
 ToolBarButton toolBarButton3 = new ToolBarButton(); <br>
 toolBarButton1.Text = "New"; <br>
 toolBarButton2.Text = "Open"; <br>
 toolBarButton3.Text = "Save"; <br>
 toolBar.Buttons.Add(toolBarButton1); <br>
 toolBar.Buttons.Add(toolBarButton2); <br>
 toolBar.Buttons.Add(toolBarButton3); <br>
 txtContent = new RichTextBox();
 txtContent.Size = this.ClientSize; <br>
 txtContent.Height -= toolBar.Height; <br>
 txtContent.Top = toolBar.Height; <br>
 txtContent.Anchor = AnchorStyles.Left | AnchorStyles.Right | AnchorStyles.Top | AnchorStyles.Bottom; <br>
 txtContent.Font = new Font("Arial", 16); <br>
 txtContent.AcceptsTab = true; <br>
 txtContent.Padding = new Padding(8); <br>
this.Controls.Add(toolBar); <br>
 this.Controls.Add(txtContent); <br>
 } <br>
 private void toolBarClicked(Object sender, ToolBarButtonClickEventArgs e) <br>
 { <br>
saveFile(); <br>
switch (toolBar.Buttons.IndexOf(e.Button)) <br>
{ <br>
case 0: <br>
this.Text += "My notepad"; <br>
txtContent.Text = string.Empty; <br>
fileName = null; <br>
break; <br>
case 1: <br>
 OpenFileDialog openDlg = new OpenFileDialog(); <br>
 if (DialogResult.OK == openDlg.ShowDialog()) <br>
 { <br>
 fileName = openDlg.FileName; txtContent.LoadFile(fileName); this.Text = "My notepad " + fileName; <br>
 } <br>
 break; <br>
 } <br>
 } <br>
 void saveFile() <br>
 { <br>
 if (fileName == null) <br>
 { <br>
 SaveFileDialog saveDlg = new SaveFileDialog(); <br>
 if (DialogResult.OK == saveDlg.ShowDialog()) <br>
 { <br>
  fileName = saveDlg.FileName; <br>
 this.Text += " " + fileName; <br>
 } <br>
 } <br>
 else <br>
 { <br>
 txtContent.SaveFile(fileName, RichTextBoxStreamType.RichText); <br>
 } <br>
 } <br>
 private void NotepadClosing(Object sender, FormClosingEventArgs e) <br>
 { <br>
 saveFile(); <br>
 } <br>
 /*static void Main(String[] args) <br>
 { <br>

 Application.Run(new NotepadForm()); <br>
 }*/<br>
 } <br>
 } <br>
 
OUTPUT:  <br>![image](https://user-images.githubusercontent.com/97940333/160990386-a546180f-8f39-406f-89ee-f470f095b313.png)

 ********************************************************************************************************************************************************
29. C# Program to Perform Reversal, Padding and Trimming Operations on  string. <br>
************************************************************************************************************************************************************
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
using System.Drawing.Drawing2D;<br>

namespace BinaryTree<br>
{<br>
 public partial class Form1 : Form<br>
{<br>
private Node root;<br>
public Form1()<br>
{<br>
InitializeComponent();<br>
this.root = null;<br>
test();<br>
}<br>
void test()<br>
{<br>
textBox1.Text = "5";<br>
btnAdd_Click(btnAdd, null);<br>
textBox1.Text = "3";<br>
btnAdd_Click(btnAdd, null);<br>
textBox1.Text = "2";<br>
btnAdd_Click(btnAdd, null);<br>
textBox1.Text = "1";<br>
btnAdd_Click(btnAdd, null);<br>
textBox1.Text = "4";<br>
btnAdd_Click(btnAdd, null);<br>
textBox1.Text = "7";<br>
btnAdd_Click(btnAdd, null);<br>
textBox1.Text = "6";<br>
btnAdd_Click(btnAdd, null);<br>
textBox1.Text = "8";<br>
btnAdd_Click(btnAdd, null);<br>
}<br>
private void btnCreate_Click(object sender, EventArgs e)<br>
{<br>
root = null;<br>
pictureBox1.Image = null;<br>
}<br>
private void btnAdd_Click(object sender, EventArgs e)<br>
{<br>
int value = int.Parse(textBox1.Text); if (root == null)<br>
root = new Node(value);<br>
else<br>
{<br>
if (root.Add(value) == false)<br>
MessageBox.Show("The value already exists!");<br>
}<br>
drawTree();<br>
}<br>
private void btnRemove_Click(object sender, EventArgs e)<br>
{<br>
int value = int.Parse(textBox1.Text); if (root != null)<br>
{<br>
bool status = root.Remove(value, root, ref root); if (status == false)<br>
{<br>
MessageBox.Show("the value does not exists");<br>
}<br>
}<br>
drawTree();<br>
}<br>
 private void btnSearcch_Click(object sender, EventArgs e)<br>
{<br>
string msg;<br>
int value = int.Parse(textBox1.Text); if (root == null)<br>
{<br>
msg = "Tree is empty";<br>
}<br>
 else<br>
 {<br>
if (root.Exists(value))<br>
{<br>
msg = "Value found";<br>
}<br>
else<br>
{<br>
msg = "Value not found";<br>
}<br>
}<br>
MessageBox.Show(msg);<br>
}<br>
void drawTree()<br>
{<br>
if (root != null)<br>
pictureBox1.Image = root.Draw();<br>
else<br>
pictureBox1.Image = null;<br>
this.Update();<br>
 }<br>
 }<br>
 class Node<br>
 {<br>
 internal Node left { get; set; }<br>
 internal Node right { get; set; }<br>
 internal int value;<br>
 internal int center = 12;<br>
 private static Bitmap nodeBg = new Bitmap(30, 25); private static Font font = new Font("Arial", 14);<br>
 internal Node(int value)<br>
 {<br>
 this.value = value;<br>
 }<br>
 internal bool Add(int value)<br>
{<br>
Node node = new Node(value);<br>
if (value < this.value)<br>
{<br>
 if (this.left == null)<br>
{<br>
this.left = node;<br>
return true;<br>
}<br>
else<br>
return this.left.Add(value);<br>
}<br>
else if (value > this.value)<br>
{<br>
if(this.right == null)<br>
{<br>
this.right = node;<br>
 return true;<br>
 }<br>
 else<br>
 return this.right.Add(value);<br>
 }<br>
 return false;<br>
 }<br>
 internal bool Remove(int value, Node parent, ref Node root)<br>
 {<br>
 if (value < this.value)<br>
 {<br>
 if (left != null)<br>
 {<br>
 return left.Remove(value, this, ref root);<br>
 }<br>
 }<br>
 else if (value > this.value)<br>
  {<br>
 if (right != null)<br>
  {<br>
  return right.Remove(value, this, ref root);<br>
  }<br>
  }<br>
  else if (value == this.value)<br>
 {<br>
 bool isLeft = (this == parent.left);<br>
 if (left == null && right == null)<br>
 {<br>
 if (root == this)<br>
 root = null;<br>
 else<br>
 if (isLeft) parent.left = null; else parent.right = null;<br>
 }<br>
 else if (right == null)<br>
{<br>
 if (isLeft) parent.left = left; else parent.right = left; if (root == this)<br>
 root = left;<br>
 }<br>
 else<br>
 {<br>
 if (right.left == null)<br>
 {<br>
 right.left = left;<br>
 if (isLeft) parent.left = right;<br>
 else<br>
 parent.right = right;<br>
 if (root == this)<br>
 root = right;<br>
 }<br>
 else<br>
 {<br>
 Node node = right;<br>
 while (node.left.left != null)<br>
 node = node.left;<br>
 Console.WriteLine("Node: " + node.value);<br>
 this.value = node.left.value;<br>
 Console.WriteLine("here");<br>
 node.left = null;<br>
 }<br>
 }<br>
   return true;<br>
   }<br>
   return false;<br>
   }<br>
   public Image Draw()<br>
   {<br>
   Size lSize = new Size(nodeBg.Width / 2, 0);<br>
   Size rSize = new Size(nodeBg.Width / 2, 0);<br>
   Image lNodeImg = null;<br>
  Image rNodeImg = null;<br>
  int lCenter = 0, rCenter = 0;<br>

  if (this.left != null)<br>
  {<br>
  lNodeImg = left.Draw();<br>
  lSize = lNodeImg.Size;<br>
  this.center = lSize.Width;<br>
  lCenter = left.center;<br>
  }<br>
  if (this.right != null)<br>
  {<br>
  rNodeImg = right.Draw();<br>
  rSize = rNodeImg.Size;<br>
  rCenter = right.center;<br>
  }<br>
  int maxHeight = (lSize.Height < rSize.Height) ? rSize.Height : lSize.Height; if (maxHeight > 0) maxHeight += 35;<br>

  Size resultSize = new Size(lSize.Width + rSize.Width, nodeBg.Size.Height + maxHeight);<br>
  Bitmap result = new Bitmap(resultSize.Width, resultSize.Height);<br>
  Graphics g = Graphics.FromImage(result);<br>
  g.SmoothingMode = SmoothingMode.HighQuality;<br>
  g.FillRectangle(Brushes.White, new Rectangle(new Point(0, 0), resultSize)); g.DrawImage(nodeBg, lSize.Width - nodeBg.Width / 2, 0);<br>
  string str = "" + value;<br>
  g.DrawString(str, font, Brushes.Black, lSize.Width - nodeBg.Width / 2 + 7, nodeBg.Height / 2f - 12);<br>
  Pen pen = new Pen(Brushes.Black, 1.2f);<br>
  float x1 = center;<br>
  float y1 = nodeBg.Height;<br>
  float y2 = nodeBg.Height + 35;<br>
  float x2 = lCenter;<br>
  var h = Math.Abs(y2 - y1);<br>
  var w = Math.Abs(x2 - x1);<br>
  if (lNodeImg != null)<br>
  {<br>
  g.DrawImage(lNodeImg, 0, nodeBg.Size.Height + 35); var points1 = new List<PointF><br>
 {<br>
 new PointF(x1, y1),<br>
 new PointF(x1 - w/6, y1 + h/3.5f),<br>
 new PointF(x2 + w/6, y2 - h/3.5f),<br>
 new PointF(x2, y2),<br>
 };<br>
 g.DrawCurve(pen, points1.ToArray(), 0.5f);<br>
  }<br>
  if (rNodeImg != null)<br>
 {<br>
 g.DrawImage(rNodeImg, lSize.Width, nodeBg.Size.Height + 35); x2 = rCenter + lSize.Width;<br>
 w = Math.Abs(x2 - x1);<br>
 var points = new List<PointF><br>
 {<br>
 new PointF(x1, y1)<br>,
 new PointF(x1 + w/6, y1 + h/3.5f),<br>
 new PointF(x2 - w/6, y2 - h/3.5f),<br>
 new PointF(x2, y2)<br>
 };<br>
g.DrawCurve(pen, points.ToArray(), 0.5f);<br>
 }<br>
 return result;<br>
 }<br>
 public bool Exists(int value)<br>
 {<br>
 bool res = value == this.value;<br>
 if (!res && left != null)<br>
 res = left.Exists(value);<br>
 if (!res && right != null)<br>
 res = right.Exists(value);<br>
 return res;<br>
}<br>
}<br>
} <br>

 OUTPUT: <br>
![image](https://user-images.githubusercontent.com/97940333/161208591-3fb8f5d3-f9b9-4576-8f85-3b7c3748e62c.png) <br>

 ![image](https://user-images.githubusercontent.com/97940333/161208474-dc0c78d6-0bd7-49a2-a6a4-58135f30fe9e.png) <br>
 
 ![image](https://user-images.githubusercontent.com/97940333/161208735-7d30f937-37f4-4f86-bda9-2713c559ce6e.png) <br>


