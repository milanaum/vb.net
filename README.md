# vb.net
# vb.net
1.Write C# program to print a binary triangle <br>
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

![image](https://user-images.githubusercontent.com/97940277/154424310-683c4e72-1d56-42de-8157-6305eb621de2.png)<br> <

<br>
2. C# Program to Check Whether the Entered Number is an Amicable Number  or Not. 
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

3. C# Program to Illustrate Multilevel Inheritance with Virtual Methods  (displaying student details). <br>
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
 MarksDetails Student1 = new MarksDetails("Abhijith", 22, "Male", 20190001, "MCA", 5,  new int[]{77,80,98,95,90}); <br>
 Student1.Display(); <br>
 } <br>
 } <br>
}<br>
output:
![Screenshot (2)](https://user-images.githubusercontent.com/97940277/154626095-6285ac41-c5d1-43f9-b32f-4633d2e02030.png)<br>

4. C# Program to Create a Gray Code.<br>
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

5. C# program to calculate volume of 2 boxes and find the resultant volume  after addition of 2 boxes by implementing operator overloading.<br> 
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

6. C# Program to Implement Principles of Delegates (converting input string to  uppercase first, last and entire string). <br>
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

 7.C# program to Generate Register Number automatically for 100 Students using Static Constructor. <br>
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
![image](https://user-images.githubusercontent.com/97940333/154635181-0f940813-32eb-4881-879c-99d15b2591c8.png)![image](https://user-images.githubusercontent.com/97940333/154635531-cfbb395d-b6c3-4aa0-b400-68bb18972dd2.png)

 8.C# program to find the frequency of the word "is" in a given sentence. <br>
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

9.C# program that benchmarks 2D,jagged array allocation. <br>
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
 
 10.Write a c# program to print fibonacci series without using recurd=sion and using recursion. <br>
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

 11.Write a c# program to check prime number. <br>
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

