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
```

# Ex.No:13A
# IMPLEMENTATION OF STACK
# AIM
To write a Python program to implement a stack using a list and its built-in methods (append(), pop()).

# ALGORITHM
1.Start the program.

2.Define a class st with the following methods:
push(self, num): Adds the number num to the stack.

3.pop(self): Removes and returns the top element from the stack.

4.Create a stack object s using the class st.

5.Input the stack size: Take an integer input size to define the size of the stack.

6.Loop through numbers from 1 to size: Add only the odd numbers to the stack using the push() method.

7.Display the elements in the stack after the loop completes.

8.Call pop() to remove the top element from the stack and display the popped element.

9.Display the stack again to show the remaining elements.

10.End the program.

# PROGRAM
```
# REGNO:-212222020008
# name:- Harini B
stack = []
for i in range(5):
    s=input()
    stack.append(s)
print("Stack before elements are popped")
print(stack)
stack.pop()
stack.pop()
print("\nStack after elements are popped:")
print(stack)
```

# OUTPUT
<img width="1226" height="557" alt="image" src="https://github.com/user-attachments/assets/4cee64e8-b817-4824-85a0-2f15a7db7845" />


# RESULT
Thus a Python program to implement a stack using a list and its built-in methods (append(), pop()) has been executed succesfully


# Ex.No: 13C
## POSTFIX EVALUATION
# AIM
To write a Python program to evaluate a user-given Postfix expression that contains Multiplication and Addition operators using the stack concept.

# ALGORITHM
1.Start the program.

2.Define a set named OPERATORS containing all the valid operators: *, +, **, -, /, %.

3.Define a function evaluate_postfix(exp) to evaluate the postfix expression:
4.Inside the function, create an empty list called stack to store operands and intermediate results.

5.Loop through each item in the given postfix expression:
6.If the current item is not in OPERATORS, it is an operand, so append it to the stack.

7.If the current item is an operator:
8.Pop the top two elements from the stack (first pop is a, second pop is b).

9.Perform the operation b <operator> a depending on the current operator.

10.Store the result in a variable called result.

11.Append the result back to the stack.

12.After the loop ends, return the first element of the stack as the final evaluation result.

13.Take a postfix expression as input from the user.

14.Print the postfix expression.

15.Call the function evaluate_postfix() with the input and print the result.

16.End the program.

# PROGRAM
```
# REGNO:-212222020008
# Name:- Harini B
OPERATORS=set(['*','+']) 
def evaluate_postfix(expression):
    stack=[]
    for i in expression:
        if i not in OPERATORS:
            stack.append(i)
        else:
            a=stack.pop()
            b=stack.pop()
            if i=='+':
                res=int(b)+int(a)
            elif i=="*":
                res=int(b)*int(a)
            stack.append(res)
    return stack[0]
expression=input()
print("postfix expression: ",expression)
print("Evaluation result: ",evaluate_postfix(expression))
```

# OUTPUT
<img width="760" height="207" alt="image" src="https://github.com/user-attachments/assets/a2eac34a-4b55-4f73-8830-2c6fcdc38623" />


### RESULT 
Thus a Python program to evaluate a user-given Postfix expression that contains Multiplication and Addition operators using the stack concept has been executed successfully.


# Ex.No:13D
## PREFIX EVALUATION

---

### AIM  
To write a Python program to evaluate a user-given Prefix expression using a stack. The expression must contain operators such as Multiplication, Addition, and Subtraction.

---

### ALGORITHM

1. **Start the program.**
2. Define a set of valid operators: `*, -, +, %, /, **`.
3. Initialize an empty stack.
4. Traverse the prefix expression from **right to left**:
   - If the character is a **digit**, convert it to an integer and push it onto the stack.
   - If the character is an **operator**, pop two elements from the stack.
     - Apply the operator on the two popped operands.
     - Push the result back onto the stack.
   - If an invalid character is encountered, raise an error.
5. After traversal, the stack should contain only **one element**.
6. Return the **single element** as the evaluation result.
7. **End the program.**

---

### PROGRAM

```
# REGNO:-212222020008
# Name:- Harini B

OPERATORS = set(['*', '-', '+', '%', '/', '**'])

def evaluate(expression):
    stack = []
    for i in reversed(expression):
        if i not in OPERATORS:
            stack.append(i)
        else:
            a = stack.pop()
            b = stack.pop()
            if i == '+':
                res = int(a) + int(b)
            elif i == '*':
                res = int(a) * int(b)
            elif i == '-':
                res = int(a) - int(b)
            elif i == '/':
                res = int(a) // int(b)
            elif i == '%':
                res = int(a) % int(b)
            elif i == '**':
                res = int(a) ** int(b)
            stack.append(res)
    return stack[0]

test_expression = input()
print("Prefix Expression :", test_expression)
print("Evaluation result :", evaluate(test_expression))

```


### OUTPUT
<img width="818" height="198" alt="image" src="https://github.com/user-attachments/assets/be345853-b49c-455d-804a-0582d6fafaf9" />

### RESULT
Thus a Python program to evaluate a user-given Prefix expression using a stack has been executed successfully.

# Ex.No:13E 
## TOWER OF HANOI

---

### AIM  
To write a Python program to implement **Tower of Hanoi** and display all the moves of the disks using a recursive function.  
Consider the names of the tower pegs as A, B, C. Get the number of disks value from the user.

---

### ALGORITHM  

1. **Start the program.**
2. **Input** the number of disks `n`.
3. **Print** the number of disks.
4. Define a **recursive function** `TowerOfHanoi(n, source, destination, auxiliary)`:
   - If `n == 1`:
     - Print: "Move disk from source to destination".
   - Else:
     - Call `TowerOfHanoi(n - 1, source, auxiliary, destination)`  
       → Move `n-1` disks from source to auxiliary using destination as helper.
     - Print: "Move disk from source to destination"  
       → Move the largest disk to the destination.
     - Call `TowerOfHanoi(n - 1, auxiliary, destination, source)`  
       → Move `n-1` disks from auxiliary to destination using source as helper.
5. Call `TowerOfHanoi(n, 'A', 'C', 'B')` to start the process.
6. **End the program.**

---

### PROGRAM  

```
#REGNO:-212222020008
#Name:- Harini B
def TowerOfHanoi(n , source, destination, auxiliary):
	
	if(n>0):
	    TowerOfHanoi(n-1, source, auxiliary,destination)
	    print("Move disk from",source,"to",destination)
	    TowerOfHanoi(n-1, auxiliary,destination,source)
	    

n=int(input())		
print("No. of disks =",n)


```

### OUTPUT
<img width="981" height="391" alt="image" src="https://github.com/user-attachments/assets/38fc873f-840e-43f8-8e87-be994591a3ed" />



### RESULT
Thus a Python program to implement **Tower of Hanoi** and display all the moves of the disks using a recursive function has been executed successfully.

 
