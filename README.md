Download Link: https://assignmentchef.com/product/solved-csci2270-homework-c-fundamentals
<br>
OBJECTIVES

<ol>

 <li><strong> Read-in command line arguments 2. Read a file 3. Loop through an array 4. Create an array of struct types 5. Read and Write to a file</strong></li>

</ol>

Write code to complete the problem below. To receive credit for your code, you will need to paste your solution into <strong>Moodle’s autograder (CodeRunner)</strong>. Your code needs to compile and pass the given test cases in order to receive points. Note that the autograder submissions are divided into separate parts, so that you will be required to test the individual functions prior to testing the entire program. You must also zip your code and attach it to this week’s Dropbox via Moodle.

<h2>P roblem</h2>

<strong>Overview: </strong>In this question, you will write a program that:

<ol>

 <li>Reads a <strong>“.csv” </strong>file with up to 10 lines and 5 columns containing information on student grades.</li>

 <li>Stores the information in an array of structs.</li>

 <li>Writes the lines into the <strong>output .csv </strong>file where the overall student grade is an A.</li>

 <li>Prints the content of the entire array.</li>

</ol>

<strong>Specifics: </strong>

Create an array that holds the <strong>studentData struct objects</strong>. Use the following struct declaration:

<strong>struct studentData { string </strong>studentName; <strong>int </strong>homework; <strong>int </strong>recitation; <strong>int </strong>quiz; <strong>int </strong>exam; <strong>double </strong>average;

};

<strong>2A</strong>. Write a function named <strong>addStudent: </strong>

<ol>

 <li>The <strong>addStudentData </strong>function has the following declaration:</li>

</ol>

<strong>// length: Number of items currently stored in the array </strong><strong>void addStudentData(studentData </strong><strong>students[]</strong><strong>, string </strong><strong>studentName</strong><strong>, int </strong><strong>homework</strong><strong>, int </strong><strong>recitation</strong><strong>, int </strong><strong>quiz, </strong><strong>int </strong><strong>exam,</strong><strong> int </strong><strong>length</strong><strong>);</strong>

<ol>

 <li>Instantiate a struct and store the <strong>studentName, homework</strong>, <strong>recitation</strong>, <strong>quiz</strong>, and <strong>exam </strong>values in it.</li>

</ol>

<ul>

 <li>Assume equal weights amongst everything that needs to be graded. Take the average of the homework, recitation, quiz, and exam for each respective student and store it in the struct.</li>

</ul>

<ol>

 <li>student.average = (homework + recitation + quiz + exam) / 4;</li>

 <li>Add the struct to the <strong>students </strong></li>

</ol>




<strong>2B</strong>. Write a function named <strong>calcLetter: </strong>

<ol>

 <li>The <strong>calcLetter </strong>function has the following declaration:</li>

</ol>

<h3>char calcLetter(double avg);</h3>

<ol>

 <li>Write IF-ELSE conditions to assign letter grades based on the following a. &gt;90 = A

  <ol start="89">

   <li>80-89.9 = B</li>

   <li>70-79.9 = C</li>

   <li>60-69.9 = D</li>

   <li>&lt;60 = F</li>

  </ol></li>

</ol>

<ul>

 <li>Return the letter grade.</li>

</ul>

<strong>2C</strong>. Write a function named <strong>printList: </strong>

<ol>

 <li>The <strong>printList </strong>function has the following signature:</li>

</ol>

<strong>// length: Number of items in the array </strong>

<h3>void printList(const studentData students[], int length);</h3>

<ol>

 <li>Loop through the <strong>students </strong></li>

</ol>

<ul>

 <li>Print out each element of the <strong>student </strong>array in the following format.</li>

</ul>

&lt;student_name&gt; earned &lt;student_average&gt; which is a(n) &lt;letter_grade&gt; <em>cout &lt;&lt; students.studentName &lt;&lt; ” earned ” &lt;&lt; students.average &lt;&lt; ” which is a(n): ” &lt;&lt; calcLetter(students[index].average) &lt;&lt; endl; </em><strong>Example: </strong>

“John Doe earned 95 which is an A”




<strong>2D</strong>. <u>Write a <strong>complete program </strong>which includes the following<strong>:</strong></u> I.        The <strong>stru<u>c</u>t </strong>and<strong> functions </strong>listed above<strong>.</strong>

<ol>

 <li>A <strong>main() </strong>function defined as below:</li>

 <li>Your <strong>main() </strong>should handle <strong>four command line arguments </strong>

  <ol>

   <li>the name of the <strong>input “.csv”</strong> file</li>

   <li>the name of the <strong>output “.csv”</strong> file</li>

   <li>a low bound letter grade</li>

   <li>an upper bound letter grade</li>

  </ol></li>

 <li>Input and output files need to be stored in the same directory as your program.</li>

 <li>Read from the input file, “<strong><em>csv</em></strong>”:

  <ol>

   <li>Each line of the file can be read using <strong>getline </strong></li>

   <li>Parse each line using <strong>stringstream </strong>and convert each entry into its appropriate data type. <strong>Keep in mind that you must use the exact data types that are specified in the struct.</strong> <em>(Hint: If needed, use <strong>stoi, stof </strong>functions to convert from strings to numbers) </em></li>

   <li>Call <strong>addStudentData </strong>function to update the <strong>students </strong></li>

  </ol></li>

 <li>Call the <strong>printList </strong>function after the array has been filled with data.</li>

 <li>Writing out to external files in C++ can be done very similarly as reading in. Instead of using an object of the <em>ifstream </em>class, as is done with input streams, use an object of the <em>ofstream </em> A “csv” stands for comma separated values. Write into <strong>output “.csv” </strong>file:

  <ol>

   <li>Write the &lt;student_name&gt;, &lt;student_average&gt;, &lt;letter_grade&gt; of the students whose &lt;letter_grade&gt; is &gt;= <strong>lower_bound </strong>and &lt;letter_grade&gt; &lt;= <strong>upper_bound </strong>(read from command line) into the <strong>output “.csv” </strong></li>

   <li><strong>You should not sort them while writing to output file. </strong>The relative order will be same as input file. Only those students with overall letter grade within the bounds should be written to the output file.</li>

  </ol></li>

 <li>Make sure your program closes the output file when it is finished writing.</li>

</ol>







<strong>Check next page for sample input and output. </strong>

<strong> </strong>

<strong>Sample Input and Output: </strong>

<strong>Test case 1: </strong>

<strong>File Contents: students.csv </strong>

Tim Thomas, 90, 92, 95, 100

Bob Brown, 80, 90, 88, 81

Jenny Jackson, 69, 79, 90, 73

Samantha Smith, 65, 57, 72, 59

Ralph Rogers, 55, 59, 62, 48




<strong>Your print Output: </strong>

Tim Thomas earned 94.25 which is an A

Bob Brown earned 84.75 which is an B

Jenny Jackson earned 77.75 which is an C

Samantha Smith earned 63.25 which is an D

Ralph Rogers earned 56 which is an F


