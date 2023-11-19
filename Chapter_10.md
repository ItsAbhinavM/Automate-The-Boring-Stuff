# PRACTICE QUESTIONS

1. The shutil.copy() function is used to copy a single file in a directory and the shutil.copytree() function will copy the whole folder includinf the file/folder that the folder may contain .
2. The shutil.move() function can also be used to rename a file .
3. The function send2trash deletes the specific file and stores it in the bin whereas the delete function in the shutil directly deletes it which is not safe .
4. zipfile.ZipFile() function.

# PRACTICE PROJECTS

## Selective copy
```
import shutil, sys, os
from pathlib import Path

if(len(sys.argv) == 4):
    oldPath = Path(sys.argv[2])
    newPath = Path(sys.argv[3])
    for dirname in oldPath.glob(f'**/*.{sys.argv[1]}'): # **/.* find recursively all files
        if(os.path.exists(newPath) == False): # If the new dir doesn't exist, create it
            newPath.mkdir()
        print(f'Copying {dirname} to {newPath}')
        shutil.copy(dirname, newPath)
else: 
    print('Usage: python selectiveCopy.py filetype oldDir newDir')
```

