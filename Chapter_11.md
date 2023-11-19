# PRACTICE QUESTIONS

1.
```
n=int(input("Enter here : "))
assert n>=10
```
2. 
```

s1=input()
s2=input()
assert s1.lower()==s2.lower()
```
3. By using `assert(False,"There is an error")`
4. 
```
import logging
logging.basicConfig(level=logging.DEBUG, format='%(asctime)s -  %(levelname)s
```
5. We can add the file name in the login.basicconfig() function .
```
import logging
logging.basicconfig(level=logging.DEBUG, format=' %(asctime)s -%(levelname)s -  %(message)s')
```
6. Debug, Info,error,warning and critical .
7. if you want to disable logging entirely, just add logging.disable(logging.CRITICAL) to your program.
8. In logging messages we have the option to diable the message that to without deleting/commenting it . The logging messages creates a timestamp .
9. In the` step Over` button when we execute one step and the next step is a function then the button will run over the function with full speed till there is a return function . In `Step In` button it will execute the first code and the next line is a function then it will run over the first line of the function  and then stops . In the `step-out` button it will execute all lines of code until it goes out of the current function .
10. After clicking the debugger will stop when it reaches the last line with a breakpoint .
11. A breakpoint can be set on a specific line of code and forces the debugger to pause whenever the program execution reaches that line.
12. For setting a breakpoint in Mu , click the line number to make the red dot appear near to it .

# PRACTICE PROJECTS
```
import random
guess = ''
guess2=''

sides=['heads','tails']
while guess not in ('heads', 'tails'):
    print('Guess the coin toss! Enter heads or tails:')
    guess = input()
toss = random.randint(0, 1) # 0 is tails, 1 is heads
if sides[toss] == guess:
    print('You got it!')
else:
    print('Nope! Guess again!')
    while guess2 not in sides:
        guess2=input("Enter your choice , heads or tails :")
    if sides[toss] == guess2:
        print('You got it!')
    else:
        print('Nope. You are really bad at this game.')
```


