# PRACTICE QUESTIONS

1. The relative path is relative to the current working directory .
2. The absolute path starts with / or C:\ .
3. It evalutes to the windowspath of that specific address in windows .
4. It will produce an error since we can't just use the strng address with / .
5. The os.getcwd() function is used to get the address of the current workign directory and the os.chdir() function is used to change the current working directory to a specific path .
6. The dot(.) it is the shorthand for that specific directory and the two-periods(..) means the parent folder .
7. Here the base name is spam.txt and the dir name is C:\bacon\eggs .
8. r for read mode , a for append mode and w for write mode .
9. It will overwrite the thing which is already written in that specific file .
10. The read() function gives all the text written in the file in a single strig and the readlines() function gives a list of strings from a each line .
11. The shelve function stores data which resembles the function of dictionary and lists . When called with a specific key the function returns a list .

# PRACTICE PROJECTS 

## Regex Search
```
import pathlib as p
import time 

user_input=input("Enter the text that you need to search : ")
status=True
time.sleep(1)
print("Searching through my databases .....")
if status:
    open_=open('hi.txt','r')
    read_=open_.read().split()
    if user_input in read_:
        print(user_input,"found in the file hi.txt")
        status=False
    else:
        print("The word",user_input,"not found in file 1")
        print("Alalysing databases....")
        time.sleep(2)
if status:
    open_2=open('hello.txt','r')
    read_2=open_2.read().split()
    if user_input in read_2:
        print(user_input,"finally found in file hello.txt")
        status=False
    else:
        print("sorry the word ",user_input,"is not there in the database .")
```
## Mad Lib
```
import pyinputplus as pyip
import re
import sys

keywords = ['ADJECTIVE', 'NOUN', 'ADVERB', 'VERB']

if(len(sys.argv) == 2):
    with open(sys.argv[1]) as txtfile:
        txt = txtfile.read()

    for keyword in keywords:
        while(keyword in txt):
            print(f'Found {keyword}')
            replacement = pyip.inputStr(f'Enter an {keyword.lower()}: ')
            txt = txt.replace(keyword, replacement, 1)

    print(txt)

    with open('hello.txt', 'w') as newTxtfile:
        newTxtfile.write(txt)
```

## Extending mulit clipboard
```
import shelve, pyperclip, sys
mcbShelf = shelve.open('mcb')

if len(sys.argv) == 3 and sys.argv[1].lower() == 'save':
    mcbShelf[sys.argv[2]] = pyperclip.paste()

elif len(sys.argv) == 3 and sys.argv[1].lower() == 'delete':
    if(sys.argv[2] in mcbShelf):
        del(mcbShelf[sys.argv[2]])
elif len(sys.argv) == 2:
    
    # List keywords and load content.
    if sys.argv[1].lower() == 'list':
        pyperclip.copy(str(list(mcbShelf.keys())))
    elif sys.argv[1].lower() == 'deleteall':
        mcbShelf.clear()
    elif sys.argv[1] in mcbShelf:
        pyperclip.copy(mcbShelf[sys.argv[1]])

mcbShelf.close()
```
