PRACTICE QUESTIONS

1. The escape characters in python are : /' , /" , // , /n , /t
2. The /n is used to print the next characters in the next line and the /t is used to print the characters after a tab space .
3. By putting double backslashes (//) in the string .
4. It is because the whole sentence is being enclosed by double quotes and not single quotes due to which the single quote present inside the strind does not affect the whole sentence .
5. By using ''' or """ 
6. The answers are :
   H
   Hello
   Hello
   lo, world
7. The answers are : 
   HELLO
   True
   hello
8. ['Remember,', 'remember,', 'the', 'fifth', 'of', 'November.']
9. rjust(),ljust() and centre()
10. Using the rstrip()  for trimming the whitespace in the right side and lstrip() for stripping the left side of the string .

# PRACTICE PROJECTS

## Table Printer

```
tableData = [['apples', 'oranges', 'cherries', 'banana'],
             ['Alice', 'Bob', 'Carol', 'David'],
             ['dogs', 'cats', 'moose', 'goose']]
def printTables(tableData):
    for i in range(len(tableData)):
        for j in range(len(tableData)):
            print(tableData[j][i],end=' ')
        print(' ')
printTables(tableData)
```


