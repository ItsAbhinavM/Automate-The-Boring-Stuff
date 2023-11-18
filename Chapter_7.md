# PRACTICE QUESTIONS

1. The functio nre.compile creates the regex objects
2. Because they allow you to give more specifactions for the search like putting / ,etc
3. The search method returns the matching setence from the selected phrase .
4. By using the group method
5. It returns the completely matching string .
6. It can be be done by using / or () .
7. If the result have two or more values then it will return a list of tuples .
8. It means 'either or'
9. ? is mainly used for non-greedy mode and in some parts it is meant to “match zero or one of the preceding group” .
10. + is used if there is one or more values , is there could be zero or more values then we could use * .
11. The {3} is used for getting exactly 3 values and {3,5} is used to get anywhee between 3 to 5 values .
12. /d means the integer values between 0-9 , /s means space and /w means word .
13. The /D , /S and /W means to identify all other values apart from an integer a word and space .
14. The .* is a greedy mode and .*? is a non-greedy mode .
15. srch=re.compile([0-9a-z])
16. By usign re.IGNORECASE() function .
17. The . is used to match all other values other than a newline . if re.DOTALL is passed on the re.compile() then it will consider the newline characters too .
18. The sub method is used to return a string with the substitutions applied . So it will return 'X drummers, X pipers, five rings, X hens' .
19. The re.verbose() allows you to use whitespaces and comments in the code which makes it easier to read .
20. rn=re.compile(r'\d{1,3}(,d{3})$')
21. s=r.compiler(r'[A-Z][a-z]*\s')
22. rp=re.comiler(r'(Alice|Bob|Carol)\s(eats|pets|throws)\s(apples|cats|baseball)',re.IGNORECASE)

# PRACTICE PROJECTS

## Date detection
```
import re
date_check=re.compile(r'[1-31]')
month_check=re.compile(r'[1-12]')
year_check=re.compile(r'.{4}')

rx=re.compile(r'(\d\d)-(\d\d)-(\d\d\d\d)')
val=rx.search(input("Enter the date here : "))
date=val.group(1)
month=val.group(2)
year=val.group(3)
def date_validation(date):
    if date_check.search(date)!='':
        return True
    else:
        return False

def month_validation(month):
    if month_check.search(month) is None:
        return False
    else:
        return True
        
def year_validation(year):
    if year_check.search(year) is  None:
        return False
    else:
        return True
count=0
if date_validation(date):
    count+=1
if month_validation(month):
    count+=1
if year_validation(year):
    count+=1
if count==3:
    print("It is a valid date !") 
else:
    print("Improper date !")
```

## Strong Password detector
```
import re
size_check=re.compile(r'.{8,}')
upper_check=re.compile(r'[A-Z]')
lower_check=re.compile(r'[a-z]')
digit_check=re.compile(r'[0-9]')

def pass_checker(passw):
    if size_check.search(passw)!='':
        return False
    elif upper_check.search(passw)!='':
        return None
    elif lower_check.search(passw)!='':
        return None
    elif digit_check.search(passw)!='':
        return None
    else:
        return True
    
password=input("Enter you password here : ")
if pass_checker(password):
    print("Your password is strong")
else:
    print("Your password is weak")
```

## Regex Search
```
import re
def strip(text, remove=''):
    if remove == '':
        space_regex = re.compile(r'^(\s*)(\S*)(\s)*$')
        trimmed = space_regex.search(text)
        return trimmed.group(2)

    # for the second string
    else:
        remove_start = re.compile(r'^([%s]+)' % remove)
        remove_end = re.compile(r'([%s]+)$' % remove)
        start = remove_start.search(text)
        end = remove_end.search(text)
        try:
            return text[len(start.group()):len(text) - len(end.group())]
        except AttributeError:
            error_avoid = remove + text + remove
            return strip(error_avoid, remove)

user_text = input('Enter the text you would like stripped here: ')
user_remove = input('Enter the character you want stripped here'
                    ' (Removes Space as Default): ')

print(strip(user_text, user_remove))
```

