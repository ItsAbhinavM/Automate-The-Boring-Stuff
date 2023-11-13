# PRACTISE QUESTIONS

1. The [] is used for representing a list in python . Any sequence enclosed within [] is considered as list .
2. spam[2]='hello'
3. It will give 'd' as the output
4. showing the last element of the list , in this case the answer will be 'd'
5. It will show all the elements in the list with a step of 2 
6. It will show the index of that specific element from the sequence
7. It will add the value 99 in the last of the list
8. The value cat will be removed from the list .
9. + is used for list concatenation and * is used for list replication .
10. The append() function adds the value to the end of the list whereas in the insert() function we can add the value to the desired index .
11. del() and remove()
12. Both string and list have length , both of them have index , a string is a sequence of characters and a list is sequence of values stored within [ ] .
13. List is a mutable datatype whereas tuple is immutable .
14. For example : bacon=(42,)
15. by using the tuple() function and the list() function .
    bacon=tuple(list_name)
    spam=list(tuple_name)
16. They contain references to the list values .
17. The copy.copy() function copies the values stored in a list and transfers it to other list and if any changes is made in the first list then the second list will also be updated accordingly . The copy.deepcopy() copies the values stored in the first list and transfers it to the second one and if any changes is made in the first list it will not affect the second list .


# PRACTICE PROJECTS

## Comma code

```
def listsep(lst):
    global s
    if s!='':
        s=s+", "+str(lst)
    else:
        s=str(lst)
s=''
lst=['apples','bananas','tofu','cats']
length=len(lst)
count=0
for i in lst:
    listsep(i)
print(s)
```


## Coin flip streaks

```
import random
numberOfStreaks = 0
for experimentNumber in range(10000):
    # Code that creates a list of 100 'heads' or 'tails' values.
    lst=[]
    for i in range(100):
        lst.append(random.choice(['HEAD','TAIL']))
    #print(lst)
    # Code that checks if there is a streak of 6 heads or tails in a row.
    count=0
    for j in range(len(lst)-1):
        if lst[j]==lst[j+1]:
            count+=1
        else:
            continue
    if count%6==0:
        numberOfStreaks+=1
    print(count)
print('Chance of streak: %s%%'%(numberOfStreaks / 100))
```


## CHARACTER PICTURE GRID

```
# CHARACTER PICTURE GRID
grid = [['.', '.', '.', '.', '.', '.'],
        ['.', 'O', 'O', '.', '.', '.'],
        ['O', 'O', 'O', 'O', '.', '.'],
        ['O', 'O', 'O', 'O', 'O', '.'],
        ['.', 'O', 'O', 'O', 'O', 'O'],
        ['O', 'O', 'O', 'O', 'O', '.'],
        ['O', 'O', 'O', 'O', '.', '.'],
        ['.', 'O', 'O', '.', '.', '.'],
        ['.', '.', '.', '.', '.', '.']]

for i in range(len(grid)):
    for j in range(len(grid[i])):
        print(grid[i][j],end='')
    print('')
```

