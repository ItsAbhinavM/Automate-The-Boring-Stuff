# PRACTICE QUESTIONS

1. Functions are very useful in large programs we can perform a specific task just by calling its name and doing it rather than just rewriting the whole code again and again .

2. The code in the function will only be executed when the function is called .

3. The def statement creates function

4. A function is a block of code which executes a specific task and a function call is an expression that invokes a function and executes the code in the function .

5. There is only one global and local scope in a code

6. The local variables will be destroyed after the return function

7. When an expression is used with a return statement, the return value is what this expression evaluates to.

8. The return value of that will be None of Nonetype .

9. By adding the keyword global along with it.

10. The datatype None is a value from Nonetype in which the variable or a stack is empty or does not have any values. 

11. import areallyourpetsnamederic will import all the codes/datas based on the directory/code areallyourpetsnamederic to the program in which it has been called .

12. spam.bacon() 

13. We can use the try and except method to avoid unwanted errors in the output .

14. In the try clause all the statements are executed and when it encounters any error it wll go to the except clause .



# PRACTICE PROJECTS

## The collatz sequence


```
def collatz(number):
    a=number
    if number%2==0:
        a=number//2
    else:
        a=number*3 +1
    return a
num=int(input())
while num!=1:
    n=collatz(num)
    print(n)
    num=n
```
