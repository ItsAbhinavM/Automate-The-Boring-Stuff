# PRACTICE QUESTIONS

1. No the PyInputPlus library does not come with the standard directories that python has , we need to specifiaclly import it in the code inorder to use it .
2. It can be used since the name PyInputPlus is very lenghty to type .
3. The function inputInt() allows the user to type only integer and the function inputfloat allows the user to type only float dataype values .
4. By using the min and max functions of the pyinput library in the code it is possible to perform such task.

   pyip.inputint(min=0,max=99)
5. The values that we need to either allow or deny from the input can be given in the allow and block regexes of pyinputplus
6. It will raise an RetryLimitException error in the code .
7. It will return hello .

# PRACTICE PROJECTS

## Sandwich maker
```
import pyinputplus as pip
count=0
dough_decider=pip.inputMenu(["wheat"," white","sourdough"])
if dough_decider=="Wheat":
    count+=1
elif dough_decider=="White":
    count+=1
elif dough_decider=="sourdough":
    count+=1
else:
    pass
meat_decider=pip.inputMenu(["chicken","turkey","ham","tofu"])
if meat_decider=="Chicken":
    count+=1
elif meat_decider=="turkey":
    count+=1
elif meat_decider=="ham":
    count+=1
elif meat_decider=="tofu":
    count+=1
else:
    pass
prompt="Do you want cheese ?"
cheese_decider=pip.inputYesNo(prompt)
if cheese_decider.lower()=="yes":
    type_cheese_decider=pip.inputMenu(["cheddar","Swiss","mozzarella"])
    if type_cheese_decider=="Cheddar":
        count+=1
    elif type_cheese_decider=="Swiss":
        count+=1
    elif type_cheese_decider=="mozzarella":
        count+=1
    else:
        count+=1
smthng_decider=pip.inputYesNo("Do you want mayo, mustard, lettuce, or tomato ?")
if smthng_decider.lower()=='yes':
    count+=1
number=pip.inputInt("how many sandwiches you want ? ")
print("The total cost is : ",number*count)
```

## Multiplication Quiz
``` 
import pyinputplus as pip
import random, time

numberOfQuestions = 10
correctAnswers = 0
count=0
for questionNumber in range(numberOfQuestions):
    num1 = random.randint(0, 9)
    num2 = random.randint(0, 9)
    try:
        inp=pip.inputStr(f'What is the product of {num1}x{num2} : ',allowRegexes=['^%s$' % (num1*num2)],blockRegexes=[('.*', 'Incorrect!')],timeout=8, limit=3)
        if inp==str((num1*num2)):
            print("Correct !")
            count+=1
    except pip.TimeoutException:
        print('Out of time!')
    except pip.RetryLimitException:
        print('Out of tries!')
    time.sleep(1) 
print(f'Your Score is : {count}')
```
