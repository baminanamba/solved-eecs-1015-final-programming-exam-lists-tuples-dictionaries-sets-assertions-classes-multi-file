Download Link: https://assignmentchef.com/product/solved-eecs-1015-final-programming-exam-lists-tuples-dictionaries-sets-assertions-classes-multi-file
<br>



<strong> </strong>

<strong>TASK 1 – Word frequency in a song lyric</strong>

<em>Topics covered</em><strong>: </strong>variables, expressions, control structures, string processing, functions, and lists.

In the utilities.py file, there is a variable named lyrics that is bound to a long string that has some of the words to the song “Happy.”  Note that the string includes newline characters, commas, and periods.

In the main() function, you should pass the lyrics variable as an argument to the function task1().   Your task is to extract the words from the lyrics string and count the number of times each word appears in the string.    Follow the procedure below.  You are welcome to introduce additional functions.  If you write additional functions, write them in the final.py file (not in utilities.py).

<strong>Perform the following steps: </strong>

<em>String pre-processing</em>

<ul>

 <li>Convert the string passed to your task1() function to lower case</li>

 <li>Remove all commas and periods from the string. <em>Counting the words and printing out the information</em> (3) Split the string to find all the words.</li>

 <li>For each word, determine the number of times it appears.</li>

 <li>Print out each word, its count, and a string of * representing the count.</li>

</ul>

For example, if the string “the” appears three (3) times and the string “you” appears four (4) times, print:

the [3] ***        you [4] ****

<em>Hint</em>: When printing out the word from the lyrics, you can use “%10s” in the string formatting.  This notation will result in the string always taking ten (10) characters.

Here is a <em><u>partial</u></em> output from Task 1—see also the accompanying video.

— Task 1 —       what  [3] ***       along  [4] ****         i’m  [6] ******       she’s  [1] *         the  [3] ***        take  [1] *        roof  [1] *  ….

you  [7] *******<strong>  </strong>

<strong> </strong>

<em>Note</em>: There are many ways to perform this task.  You may find using the “set” data type discussed in lecture 10 useful.  Set can be used to find the unique items in a list.  For example:   x = set([10,20,10,20,30]) -&gt;  x = {10,20,30}.

Also, remember that you can always convert a set to a list as follows:

x = list({10,20,30}) -&gt; x = [10,20,30]

<strong> </strong>

<strong>Task 2 – “Invert” a dictionary’s keys and values </strong>

<em>Topics covered</em><strong>: </strong>variables, expressions, control structures, functions, lists and dictionaries.

In the utilities.py file, there is a variable named nameDict that is bound to a dictionary object.  The dictionary object’s keys are strings (representing a person’s name), and the value associated with each key is the person’s age (e.g., “Abdullah”:18, “Su”:21, …, “Priya”:18).

In the main() function, you should pass the nameDict variable as an argument to the function Task2().  Task2 function should create a new dictionary that “inverts” the keys and values in nameDict.   In particular, your new dictionary will have keys that are the ages; the associated value for each key will be a list of names.

Once you have “inverted” the dictionary, you should do the following.

<ul>

 <li>Print out the new dictionary variable (this way, we can see you constructed it correctly)</li>

 <li>For each key in the new dictionary, print out the age and then each person’s name in the list as shown below.</li>

</ul>

You are welcome to introduce additional functions.  If you write additional functions, write them in the final.py file (not in utilities.py).

Here is a <em><u>partial</u></em> output from Task 2—see also the accompanying video.

{17: [‘Dirk’, ‘Sarah’, ‘Bosko’, ‘Cameron’], 18: [‘Mahesh’, ‘Abdullah’, ‘Franck’, ‘Xavier’, ‘Maxim’, ‘Priya’], 19: [‘Kai’, ‘Bailey’, ‘Ollie’, ‘Parsa’, ‘Ming’, ‘Javier’], 20: [‘Jol’, ‘Seonjoo’, ‘Beatrice’], 21: [‘Su’, ‘Abbo’, ‘Olivia’], 22:

[‘Pravel’, ‘Urzula’], 23: [‘Katja’], 24: [‘Svetlana’]}

Age 17

Dirk

Sarah

Bosko

Cameron

Age 18

Mahesh

Abdullah

Franck

Xavier

Maxim

Priya

…

Age 24

Svetlana<strong>                                                 </strong>

<strong>Task 3 – Poor person’s graphics — draw a circle in a 20×20 raster (2D lists)</strong>

<em>Topics covered:</em>variables, expressions, control structures, functions, and lists of lists, testing (assert)

In the utilities.py file, there is a variable named raster that is bound to a list of lists.   The raster variable has 20 lists, each list with 20 empty strings.   This “list of lists” is effectively a 2D list that logically makes up a 20×20 grid. In computer graphics, such grids are called a raster.  Our simple drawing program will place either a “*” or a ” ” (space) in each location of the 20×20 grid.  This can be done by access the element as follows:  raster[5][10] = “*” would place a “*” at the 6<sup>th</sup> row and 11<sup>th</sup> column of the raster; raster[3][3] = ” ”  would place a ” ” at the 4<sup>th</sup> row and 4<sup>th</sup> column of the raster.   Task 3 goal is to draw a circle in the 20×20 raster based on a user-supplied circle radius between 1 and 9.   <strong> </strong>

In the main() function, you should pass the raster variable as an argument to the function Task3().   Your function should work as follows:

<ul>

 <li>Ask the user for a radius from [1 to 9]. If the user inputs a value that is not 1-9, then raise an <strong>assertion error</strong> with the following statement: “Radius must be between 1-9”.</li>

 <li>Loop through the 20×20 raster to draw the circle using the algorithm sketched out below:</li>

</ul>

loop through i -&gt; 0 to 19 loop through j -&gt; 0 to 19  at raster location i,j

# convert i,j to an x,y coordinate by

# subtracting 10 from the i,j

#  (subtracting 10, centers the circle at 10,10)   x = i – 10   y = j – 10

if sqrt(x<sup>2 </sup>+ y<sup>2</sup>) &lt;= radius

place a ‘*’ in the i,j location on the raster   otherwise

place a ‘ ‘ in the i,j location on the raster







The sqrt() function from the math module has been imported for you in the final.py file.

<strong>For example:  </strong>

Consider the yellow raster location (i=4 and j=6) with in the figure above.  The radius of the circle to draw is 8.

Let’s determine if the raster location i=4 and j=6 should be a ” ” or a “*”? Follow the formula above:

x = 4-10 = -6 y = 6-10 = -4 sqrt(-6*-6 + -4*-4) = 7.22

7.22 is less than or equal to 8, so raster[4][6]=”*”

(3) After you draw the circle, ask the user if they would like to do it again?




<strong>See sample output on the next page. </strong>

<strong>             </strong>

<em>Example output for Task 3 (also see accompanying video) </em>




— Task 3 —

Radius [1 to 9]: 5
















*

*******

*********

*********

*********

***********

*********

*********

*********

*******

*













Try again: Y/N? y

Radius [1 to 9]: 9




*

*********

***********

*************

***************

*****************

*****************

*****************

*****************

*******************

*****************

*****************

*****************

*****************

***************

*************

***********

*********

*

Try again: Y/N? <strong>                                                </strong>

<strong>Task 4 – Robust statistics for a corrupted list (Class/Objects)</strong>

<em>Topics covered:</em>variables, expressions, control structures, functions, lists, classes/objects

In the utilities.py file, there is a variable named numList that is bound to a list of numbers.   For Task4, you will write code for a class named listStats that is used to compute the mean (also called the average), trimmed mean, and median of a list.     The trimmed mean and median are known as “robust statistics” because they can give good answers even when some of the data in the list has been “corrupted”.  Task4 will examine how the mean, trimmed mean, and median perform on corrupted input.

Your listStat class should have the following methods that provide the described functionality:

__init__( parameters: numList, corruption_level )

This method is the object’s constructor or initializer.  The constructor is passed a numList and a        “corruption level”.  The corruption level is a value between 0 and 100.     Create an instance variable that stores a <em>copy</em> of the numList.

Next “corrupt” the numList as follows:

For each item in the numList, generate a random number between 1 and 100.

If the random number is &lt;= the corruption_level parameter, then corrupt the item as follows:

Generate another random number between 1 and 100.

If the number is &gt; 50, set the item in the list to -1; otherwise set the item to 100.




computeMean()

This method computes the mean (i.e., standard average) of the corrupted list.    The mean is the sum of all items in the list divided by the number of items.

Print out the result as “Standard Mean  XXX” where XXX is formatted to have 2 decimal places.




computeTrimmedMean()

A “trimmed mean”  is computed as follows.

<ul>

 <li>sort the list</li>

 <li>Remove the first 10 items and last 10 items from the list</li>

</ul>

The removal of these items is where the term “trim” comes from, which means to “cut” or “remove.”      (3) Now, compute the average of the <em>new</em> list.

– Note: sum only the items in the trimmed list and divide by the number of items in the trimmed list.

Print out the result as “Trimmed Mean   XXX” where XXX is formatted to have 2 decimal places.




computeMedian()

The median is computed by sorting the list and taking the middle value.

The middle value is the length of the list divided by 2 using integer division (//).

Take care to make sure this method sorts the full corrupted list and not the trimmed list.

Print out the result as “Median        XXX”.  Note that the median will be an integer.

printStatistics()

This method prints out the corruption level and the corrupted list (see output example on next page).

This method then calls the computeMean(), computeTrimmedMean(), and computeMedian() methods.     Recall that you call a method within another method using the self keyword (see Lecture 9       slides 46-47 for an example in the “putting it all together” example).    The mean/trimmed mean/median      methods will print out their results as described above.

<strong> </strong>

<strong>Class code and task4() code </strong>

<u>IMPORTANT: write your class in the </u><u>utilities.py</u><u> file.</u>    In task4() in the main file (final.py), declare three listStats objects with the following corruption levels (0, 15, and 30).  For each of these three objects, call the printStatistics() method as follows:

obj1 = listStats(numList, 0)  # no corruption obj2 = listStats(numList, 15) # 15% chance of corruption obj3 = listStats(numList,30)  # 30% chance of corruption

obj1.printStatistics()        # print stats obj2.printStatistics()        # print stats obj3.printStatistics()        # print stats

<em>Example output for Task 4 (also see accompanying video) </em>

— Task 4 —

Corruption level 0%

[21, 20, 29, 16, 16, 19, 26, 19, 26, 23, 19, 25, 16, 18, 18, 18, 21, 15, 18, 14, 22, 17,

32, 30, 22, 28, 26, 17, 19, 16, 17, 17, 19, 21, 20, 17, 18, 34, 23, 18, 23, 22, 17, 22,

16, 11, 21, 26, 20, 27]

Standard Mean  20.70

Trimmed Mean   19.90 Median         20

Corruption level 15%

[21, 20, 29, 100, 16, 19, 26, 19, 26, 23, -1, 25, 16, 18, 18, 18, 100, 15, 18, 14, 22,

17, 32, 30, 22, 28, 100, -1, 19, 16, 17, -1, 19, 21, 20, 17, 18, 34, 23, 18, 23, -1, 100,

-1, -1, 11, -1, 26, 20, 27]

Standard Mean  24.28

Trimmed Mean   20.03

Median         19

Corruption level 30%

[100, 20, 29, 16, -1, 19, 26, 19, 100, 23, 19, 100, 16, 18, 18, 100, 21, 15, 18, 14, 22,

100, 32, 100, 22, -1, 26, 17, -1, 16, 17, 17, -1, 21, 100, -1, 18, 34, 23, 18, 23, 100,

17, 22, 16, 11, 21, -1, 20, 27]

Standard Mean  30.50

Trimmed Mean   20.30

Median         20

Notice how the trimmed mean and median give similar results even when the list is corrupted.










<strong> </strong>

<strong> </strong>



















<strong> </strong>














