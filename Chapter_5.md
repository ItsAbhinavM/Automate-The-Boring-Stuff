# PRACTICE PROBLEMS

1. An empty dictionary will look like :  {}
2. {'foo':42}
3. Unlike list dictionary can be unordered , a list can store single data whereas a dictionary can store it only in a key-value format .
4. We will get a KeyError since there is no key known as 'foo' in the dictionary .
5. Both are same since cat in spam checks for the cat key present in the dictionary whereas the spam.keys checks specifically  for the key .
6. In cat in spam it checks for the cat key in the dictionary and in cat in spam.values it checks for the cat value in the dictionary .
7. spam.setdefault('color','black') 
8. The pprint() module.

# PRACTICE PROJECTS

## Chess dictionary validator

```
chessdict={'1h': 'bking', '6c': 'wqueen', '2g': 'bbishop', '5h': 'bqueen', '3e': 'wking'}

def isValidChessBoard(chessdict):
    for i in chessdict.keys():
        for p in range(1,9):
            if str(p) in i:
                return True
        if i in "a,b,c,d,e,f,g,h":
            return True
        else:
            return False
    for j in chessdict.values():
        if "W" in i:
            return True
        elif "b" in i:
            return True
        else:
            return False
print(isValidChessBoard(chessdict))
```

## Fantasy Game Inventory

```
stuff = {'rope': 1, 'torch': 6, 'gold coin': 42, 'dagger': 1, 'arrow': 12}

def displayInventory(inventory):
    print("Inventory:")
    item_total = 0
    for k, v in inventory.items():
        print(k,v)
        item_total+=v
    print("Total number of items: " + str(item_total))

displayInventory(stuff)
```

# List to Dictionary Function for Fantasy Game Inventory

```

dragonLoot = ['gold coin', 'dagger', 'gold coin', 'gold coin', 'ruby']

def addToInventory(inventory, addedItems):
    # your code goes here
    count=0
    for i in dragonLoot:
        if i not in inventory:
            count+=1
            inventory.update({i:count})
        elif i in inventory:
            inventory[i]+=count
        else:
            continue 
    return inventory

def displayInventory(inventory):
    print("Inventory:")
    item_total = 0
    for k, v in inventory.items():
        print(k,v)
        item_total+=v
    print("Total number of items: " + str(item_total))


inv = {'gold coin': 42, 'rope': 1}
dragonLoot = ['gold coin', 'dagger', 'gold coin', 'gold coin', 'ruby']
inv = addToInventory(inv, dragonLoot)
print(inv)
displayInventory(inv)
```

