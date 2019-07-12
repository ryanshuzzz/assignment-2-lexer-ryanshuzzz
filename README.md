# assignment-2-lexer-ryanshuzzz
assignment-2-lexer-ryanshuzzz created by GitHub Classroom<br />
Ryan Shu (916850524)<br />
GitHub Repo(https://github.com/sfsu-csc-413-spring-2019/assignment-2-lexer-ryanshuzzz)<br />
CSC 413-05<br />
### Overview
-<br />
### Project Introduction
This repository contains certain aspects of the x language compiler. The goal of this program is to
extend the Lexer component of the x language compiler. The compiler needed to be able to handle
additional tokens to help the compiler understand the code. For example, one of the tokens that I have
added was the GreaterThan (>) token. Initially given is the TokenSetup class, which, when ran, would
allow anyone adding to the compiler to add tokens for which the compiler would recognize. I used this
class to create the following tokens<br />
1. Greater : ><br />
2. GreaterEqual : >=<br />
3. Void: void<br />
4. Char: char<br />
5. CHARacter: <char><br />
6. Scientific: scientific<br />
7. ScientificLit: <scientific> expressed by d.dd[Ee][+-]d+<br />
<br />

### Summary of Technical Work
After using TokenSetup to create the tokens mentioned above, I can run Lexer to first test if the sample
files found in /sample_files/ ran and outputted the information properly. I then formatted the string to
make it readable. The most of the tokens worked, the only ones I had to manually implement was the
CHARacter, and the ScientificLit<br />

### Execution and Development Environment Described
I developed from this code base using IntelliJ IDEA Community v. 2018.3.4. This Java application was
compiled using Java JDK version 11.0.2 which is the most up to date version of the JDK.

### Scope of Work Described

•Create additional tokens specified in Project Introduction
  ◦ Enter tokens into file /lexer/setup/tokens
  ◦ Compile and Run /lexer/setup/TokenSetup.java to autogenerate new tokens
•Reformat the print statement in the while loop in the main function of /lexer/Lexer.java
  ◦ Use printf to ensure proper formatting
•Create public Token newCharToken(String, startPosition, endPosition)
  ◦ Allows the proper get methods to work when a new Char is created
•Create public Token newScientificToken(String, startPosition, endPosition)
  ◦ Allows the proper get methods to work when a new Scientific is created
•Implement functionality for CHARacter in /lexer/Lexer.java
  ◦ Create function to check for single quote(‘) and second single quote(‘) and check if a
•character is contained within single quotes(i.e. ‘c’)
  ◦ The function returns illegal character: ‘ if no character is contained
•Implement functionality for ScientificLit in /lexer/Lexer.java
  ◦ Create method String isScientific(String)
    ▪ checks if proceeding tokens are of type ScientificLit(d.dd[Ee][+-]d+)
    ▪ returns the proceeding numbers if true
    ▪ returns checked numbers, and ends program if false
•Create printError(String) in /lexer/Lexer.java
  ◦ Prints the (“******illegal character: “ + <given character>) statement with the inputted char
  ◦ Ends the program
•Create StringBuffer in in /lexer/SourceReader.java
  ◦ Contains all of the previous lines outputted
  ◦ Outputs entire Stringbuffer when SourceReader.close() is called

### Instructions to Compile and Execute
Dependencies:<br />
Java JDK 11.0.2<br />
Java JRE 18.9 or Newer<br />
<br />
1. Clone this repository<br />
2. Navigate into the repository folder(assignment-2-lexer-ryanshuzzz)<br />
3. Compile using <br />
```
javac lexer/Lexer.java
```
4. Run using <br />
```
java lexer.Lexer.java [test file location]
```
◦ given test files are in /sample_files/

### Assumptions Made
No assumptions were made for this project

### Implementation Discussion
-<br />
### Implementation Decisions
There were many decisions made during the implementation of this program. These decisions were
made to make the code readable, and as efficient as I could. One decision I made was to use printf to
format the outputted string to make the spacing, and outputted variables look as readable as possible.Next I decided to print the entire test file when close() was called in order to make sure the entire part
of the file that was read outputted onto the console.
A decision I made to help make the code clean was to create the isScientific(String) method, which
iterates through the program to check if the given input was a Scientific Literal type. This method
helped me separate the huge chunk of code that it took to actually check if the given input was the
correct format. Similarly, I moved the error message into a new method called printError(String) which
allows me to call this when checking the tokens, and when an invalid token is given, it will end the
program and output the error.
### Code Organization
As previously stated in Implementation, I created two methods to better organize the code that I was
given.
### Results/Conclusion
The Lexer works as described, and has been tested to check for the given Tokens shown in the Project
Introduction.

### Class Diagram
See assignment-2-lexer-ryanshuzzz-class-diagram.png for class diagram.
