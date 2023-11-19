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
## Deleting unneeded files
```
import os, sys
from pathlib import Path

if(len(sys.argv) == 3):
    searchedDir = Path(sys.argv[1])

    try:
        minSize = int(sys.argv[2]) 
    except ValueError:
        print(f'{minSize} is not an Integer.')
    else:
        # save each filename and size in a tuple under the key 'entries' in a dict
        fileTable = {} 
        fileTable['entries'] = []
        fileTable.setdefault('pathlength', 0)

        for dirname, dirnames , filenames in os.walk(searchedDir):
            for filename in filenames:
                fileSize = os.path.getsize(os.path.join(dirname, filename))

                # check if the current file is bigger than the size given in the second argument
                if(fileSize > minSize):
                    abspath = os.path.abspath(filename) 
                    fileTable['entries'].append((abspath, fileSize))
                    pathlength = len(abspath)
                    if pathlength > fileTable['pathlength']:   # Check for the longest pathlength in dir 
                        fileTable['pathlength'] = pathlength

        # pretty print the filenames and sizes     
        for filePath, size in fileTable['entries']:
            print(filePath.ljust(fileTable['pathlength']+1) + str(size))

else:
    print('Usage: python deletingUnneededFiles.py path size')
```
## Filling Gaps
```
import shutil
from pathlib import Path

def close_and_insert_gaps(folder_path, file_prefix, index_to_insert=None):
    folder_path = Path(folder_path)
    file_count = len(list(folder_path.glob(f"{file_prefix}*")))
    padding_length = len(str(file_count))
    pattern = f'{file_prefix}{{:0{padding_length}}}.txt'

    file_list = sorted(folder_path.glob(f'{file_prefix}*.txt'))

    for index, file_path in enumerate(file_list, start=1):
        expected_name = pattern.format(index)

        if index_to_insert and index == index_to_insert:
            new_path = folder_path / f'{file_prefix}{index_to_insert:0{padding_length}}.txt'
            shutil.move(file_path, new_path)
            print(f'Inserted {new_path.name}')

        elif file_path.stem != expected_name:
            new_path = folder_path / f'{file_prefix}{index:0{padding_length}}.txt'
            shutil.move(file_path, new_path)
            print(f'Renamed {file_path.name} to {new_path.name}')

folder_path = input("Enter folder path: ")
file_prefix = input("Enter file prefix: ")
index_to_insert = int(input("Enter index to insert (1-based, enter 0 to skip insertion): "))

close_and_insert_gaps(folder_path, file_prefix, index_to_insert)
```
