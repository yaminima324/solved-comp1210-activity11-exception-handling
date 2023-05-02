Download Link: https://assignmentchef.com/product/solved-comp1210-activity11-exception-handling
<br>
By the end of this project you should be able to do the following:

<ul>

 <li>Handle exceptions that can occur in your program using a try-catch statement</li>

 <li>Throw exceptions in your program</li>

</ul>

<strong>Directions: </strong>

Don’t forget to add your Javadoc comments for your classes, constructor, and methods in this activity.

For this assignment, you will be creating two classes: Division and DivisionDriver

<h1>Division: methods</h1>

<ul>

 <li>Division has two public static methods:

  <ul>

   <li>intDivide: takes two <strong>int</strong> parameters (a numerator and denominator), performs integer division, and returns the <strong>int</strong> result of dividing the numerator by the denominator.</li>

   <li>decimalDivide: takes two <strong>int</strong> parameters (a numerator and denominator), performs floating point division (you’ll have to use casting), and returns the result of dividing the numerator by the denominator.</li>

  </ul></li>

</ul>




<ul>

 <li>Test your methods in the Interactions pane:</li>

</ul>




Division.intDivide(10, 3)

3

Division.decimalDivide(10, 3)

3.3333333333333335

<h1>DivisionDriver</h1>

<ul>

 <li>DivisionDriver contains a main method only. The program will get a numerator and denominator from the user and print the integer division and decimal division result.</li>

 <li>Create a <strong>dialog box</strong> that will get the numerator and denominator as a String (you’ll have to import the JOptionPane class in the javax.swing package):</li>

 <li>Convert each to an integer value using the static parseInt method in the Integer class:</li>

 <li>Create a String object to hold the result of the division:</li>

 <li>Print the result in a dialog box:</li>

 <li>Test your method by running the driver program with numerator 19 and denominator 5:</li>

 <li>Now try entering an invalid number in the dialogs (five and ten):</li>

</ul>

Your program should generate a run-time error in the form of a NumberFormatException exception:

—-jGRASP exec: java DivisionDriver

Exception in thread “main” java.lang.NumberFormatException: For input string: “five”    at java.lang.NumberFormatException.forInputString(NumberFormatException.java:65)    at java.lang.Integer.parseInt(Integer.java:580)    at java.lang.Integer.parseInt(Integer.java:615)    at DivisionDriver.main(DivisionDriver.java:9)

—-jGRASP wedge: exit code for process is 1.

—-jGRASP: operation complete.




<ul>

 <li>The exception occurs when the parseInt method tries to convert the String “five” to an integer. The Java API listing for parseInt lists the exception that it might throw.</li>

 <li>Use a try-catch statement to catch the exception and tell the user what went wrong without creating a run-time error:</li>

 <li>Try entering invalid values five and ten once more for numerator and denominator once more. You should now get the following error:</li>

</ul>

<h1>Exception Throwing</h1>

<ul>

 <li>Try the following in the interactions pane:</li>

</ul>

Division.intDivide(10, 0)

java.lang.ArithmeticException: / by zero




<ul>

 <li>Try to run your driver program with the numerator 10 and denominator 0:</li>

</ul>




—-jGRASP exec: java DivisionDriver

Exception in thread “main” java.lang.ArithmeticException: / by zero    at Division.intDivide(Division.java:7)    at DivisionDriver.main(DivisionDriver.java:12)




—-jGRASP wedge: exit code for process is 1.

—-jGRASP: operation complete.




<ul>

 <li>The exception is generated in the intDivide method and not caught/handled, so it is <strong>propagated</strong> to main where it is also not caught/handled. Next we want to catch the exception in the intDivide method so that it will not be propagated to the main method.</li>

 <li>In your intDivide method, add code that will return 0 if an ArithmeticException occurs and the division result otherwise:</li>

</ul>

Run DivisionDriver with inputs 10 and 0. The result should be 0 for integer division:




Suppose that you do not want users to be able to divide by 0 in your decimalDivide method.

Division.decimalDivide(10, 0)

Infinity




The IllegalArgumentException in the Java API can be thrown if a particular argument (parameter) to a method is not allowed:

http://download.oracle.com/javase/6/docs/api/java/lang/IllegalArgumentException.html




<ul>

 <li>In your decimalDivide method, throw an IllegalArgumentException if the denominator is zero:</li>

</ul>

if (denom == 0) {

throw new IllegalArgumentException(“The denominator ”

+ “cannot be zero.”);

}




<ul>

 <li>Test your method again in interactions. You should now see the exception:</li>

</ul>

Division.decimalDivide(10, 0) java.lang.IllegalArgumentException: The denominator cannot be zero.

<ul>

 <li>In your main method, add another catch statement to catch the exception that is thrown by the decimalDivide method. This time, print the exception text itself (stored by variable errorMessage):</li>

 <li>Now try dividing by 0 in your program. You will get the following error message instead of a run-time error:</li>

</ul>




<ul>

 <li>Run Checkstyle on each of your files and make any necessary corrections indicated by audit errors.</li>

</ul>


