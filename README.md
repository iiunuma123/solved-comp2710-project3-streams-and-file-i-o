Download Link: https://assignmentchef.com/product/solved-comp2710-project3-streams-and-file-i-o
<br>
<ul>

 <li>To learn streams and file I/O</li>

 <li>To learn how to use tools for stream I/O</li>

 <li>To use arrays to group data elements</li>

 <li>To design and implement functions (Note: This topic was covered in Project 2)</li>

 <li>To perform unit testing</li>

 <li>To design a simple algorithm</li>

</ul>

Write a program that merges the numbers in two files and writes all the numbers into a third file. Your program takes input from two different files and writes its output to a

third file. Each input file contains a list of numbers of type int in sorted order from the smallest to the largest. After the program is run, the output file will contain all the numbers in the two input files in one longer list in sorted order from smallest to largest.

You must provide the following user interface. The user input is depicted as <strong>Bold</strong>, but you do not need to display user input in bold. Please replace “Li” with your name. Your program loads two input files and merges the numbers in the two files.




*** Welcome to <strong>Li</strong>‘s sorting program *** Enter the first input file name: <strong>input1.txt </strong>The list of 6 numbers in file input1.txt is:

4

13

14

17

23

89




Enter the second input file name: <strong>input2.txt </strong>The list of 5 numbers in file input2.txt is:

3

7

9

14

15




1

<table width="591">

 <tbody>

  <tr>

   <td width="591">The sorted list of 11 numbers is: 3 4 7 9 13 14 14 15 17 23 89Enter the output file name: <strong>output.txt </strong>*** Please check the new file – output.txt *** *** Goodbye. ***</td>

  </tr>

 </tbody>

</table>

<strong><em> </em></strong>

Your program must follow the above user interface.

<strong><em><u>Design Issues:</u> </em></strong>

Please do NOT intend to implement this project using a single main() function.

You need <strong>at least three functions</strong> to implement this project. The suggested functions are:

<ol>

 <li>array_size &lt;- readfile(inputArray[], instream)</li>

 <li>outputArray_size &lt;- sort(inputArray1[], inputArray1_size, inputArray2[], inputArray2_size, outputArray[])</li>

 <li>void &lt;- writefile(outputArray[], outputArray_size)</li>

</ol>




<strong><em><u>Integration Testing:</u> </em></strong>

Integration testing (a.k.a., Integration and Testing) is the phase in software testing in which individual software modules are combined and tested as a group. You may use the attached two input files to test the correctness of your program as an entire system.

<strong><em> </em></strong>

<strong><em><u>Requirements:</u> </em></strong>

<ol>

 <li>(5 points) Use comments to provide a heading at the top of your code containing your name, Auburn UserID, filename, and how to compile your code. Also describe any help or sources that you used (as per the syllabus).</li>

 <li>(5 points) Your source code file should be named as</li>

</ol>

“<strong>project3_LastName_UserID.cpp</strong>”. (e.g., project3_Liu_tzl0031.cpp) <strong>Note</strong>: You will not lose any point if Canvas automatically changes your file name (e.g., project3_LastName_UserID-2.cpp) due to resubmissions.

<ol start="3">

 <li>(5 points) Your program must test if files have been <strong>correctly opened</strong>.</li>

 <li>(5 points) You must <strong>close files</strong> after using them.</li>

 <li>(10 points) Your program should <strong>read and display numbers</strong> stored in the two input files.</li>

 <li>(20 points) Your program should <strong>correctly sort and display the numbers</strong>. You should also construct your own lists including <strong>negative numbers and zeros for testing</strong>.</li>

 <li>(15 points) Your program should <strong>correctly write the sorted list </strong>to the third file.</li>

 <li>(10 points) You must define <strong>at least three functions</strong>.</li>

 <li>(5 points) You must reduce the number of <strong>global variables</strong> to <strong>less than 3</strong>. 10. (10 points) Usability of your program (e.g., user interface)</li>

 <li>(10 points) Readability of your source code.</li>

</ol>




<strong>Note:</strong> You will lose <strong>at least 40 points</strong> if there are compilation errors or warning messages when the TA compiles your source code. You will lose points if you: do not use the specific program file name, or do not have a comment on each function in your program you hand in.

2

<strong><em><u>Programming Environment:</u> </em></strong>

Write a program in C++. Compile and run it using AU server (no matter what kind of text editor you use, please make sure your code could run on AU server, the only test bed we accept is AU server).

<strong><em> </em></strong>

<strong><em><u>Sample Code 1:</u> </em></strong>

The following code shows you how to use arrays and their sizes as input parameters of functions.

<table width="576">

 <tbody>

  <tr>

   <td colspan="2" width="576">//Sample code for Project 3 #include &lt;fstream&gt; #include  &lt;iostream&gt; using  namespace std; const int MAX_SIZE = 100; </td>

   <td width="2"> </td>

  </tr>

  <tr>

   <td width="2"> </td>

   <td colspan="2" width="576">//Input: (1) Array storing data retrieved from the file (i.e., instream)<sup>      </sup>//       (2) input file stream object//Output: Size of array. Note: you need to use this parameter to  control the array size. int readfile(int inputArray[], ifstream&amp; instream); int main( ){ifstream inStream1; int iArray1[MAX_SIZE];     int iArray1_size;     int iArray2[MAX_SIZE];     int iArray2_size;  inStream1.open(“input1.txt”); iArray1_size = readfile(inputAry, inStreamFirst); inStreamFirst.close( ); return 0;} int readfile(int inputArray[], ifstream&amp; inStream){     int index; inStream &gt;&gt; inputArray[index];     while (! inStream.eof()) {cout &lt;&lt; inputArray[index] &lt;&lt; endl;         index++;inStream &gt;&gt; inputArray[index];} return index; }3</td>

  </tr>

  <tr>

   <td width="2"></td>

   <td width="573"></td>

   <td width="2"></td>

  </tr>

 </tbody>

</table>

<strong><em><u>Sample Code 2:</u> </em></strong>




The following code shows you (1) how to retrieve a file name from your keyboard, (2) how to open a file, and (3) how to read data from the file.

<strong><em> </em></strong>

#include &lt;fstream&gt;

<strong><em><sup> </sup></em></strong>#include &lt;iostream&gt;

<strong><em> </em></strong>#include &lt;cstdlib&gt;  //for exit() using namespace std;

<strong><em> </em></strong>




<strong><em> </em></strong>

<table width="576">

 <tbody>

  <tr>

   <td width="576">int main(){ifstream inStream;     int data; cout &lt;&lt; “file name:”;     cin &gt;&gt; filename;cout &lt;&lt; “entered filename is:” &lt;&lt; filename &lt;&lt; endl;// Pass the file name as an array of chars to open()// inStream.open(filename);inStream.open((char*)filename.c_str()); if (inStream.fail()) {cout &lt;&lt; “Input file opening failed.” &lt;&lt; endl;          exit(1);} inStream &gt;&gt; data;      while (!inStream.eof()) {         cout &lt;&lt; data &lt;&lt; endl;        inStream &gt;&gt; data;}inStream.close(); return 0;}</td>

  </tr>

 </tbody>

</table>

<strong><em> </em></strong>