# Ex.No:13B
## CONVERSION OF INFIX TO POSTFIX
# AIM
To write a Python program to convert a given Infix expression to Postfix expression by following the precedence and associative rules. The input expression contains only Division, Subtraction, and Bitwise AND operators. A dictionary is used to set the priority for operators, and a set is used to hold the operators used in the given expression.

# ALGORITHM
1.Start the program.

2.Initialize an empty stack and an empty output string.

3.Iterate through each character in the infix expression:
If the character is not an operator, append it directly to the output string.

4.If the character is an open parenthesis '(', push it onto the stack.

5.If the character is a close parenthesis ')', pop from the stack and append to the output until encountering a left parenthesis '('.
If the character is an operator, handle it based on precedence:
While there’s an operator at the top of the stack with higher or equal precedence, pop the stack and append those operators to the output.
Push the current operator onto the stack.

6.Use a priority dictionary to define operator precedence, ensuring higher precedence operators are placed before lower precedence ones.

7.Once the expression is fully processed, continue popping any remaining operators from the stack and append them to the output.

8.Return the final postfix expression.

9.Print the result.

10.End the program.

# PROGRAM
```
# REGNO:-212222020008
# Name:- Harini B
Operators = set(['&', '-', '/','(',')']) # collection of Operators

Priority = {'&':1,'-':2,'/':3} 

 
