## Files and Directories 

- Change into a directory: 

    ```cd [/path/to/dir]```
- Move up one level in the filesystem: 

    ```cd ..```
- Change to home directory: 

    ```cd```
- Change to home directory: 

    ```cd ~```
- Get information on a file: 

    ```file [file]```
- View directory contents (from inside): 

    ```ls```
- View directory contents (from outside):

    ```ls [dir]```
- List directories without listing contents: 

    ```ls -d [dir]```
- List contents including hidden files: 

    ```ls -a```
- List contents including hidden files, excluding current & parent dirs: 

    ```ls -A```
- Long listing of directory contents: 

    ```ls -l```
- Long listing of directory contents human-readable: 

    ```ls -lh```
- Long list with file authors: 

    ```ls -l --author```
- Long list sorted by modification time, newest first: 

    ```ls -lt```
- List directory contents sorted by file size, largest first: 

    ```ls -S```
- Reverse the order while sorting: 

    ```ls -Sr```
- List directory contents recursively: 

    ```ls -R [dir]```
- Long listing of a directory: 

    ```ll [dir]```
- Create an empty file: 

    ```touch [filename]```
- Update an existing file's timestamp:

    ```touch [file]```
- Move a file 

    ```mv [file] [/path/to/target]```
- Rename a file 

    ```mv [file] [new name]```
- Move a file without overwriting any files in target dir: 

    ```mv -n [file] [/path/to/target]```
- Copy a file: 

    ```cp [file] [destination]```
- Copy a file without overwriting any files in target: 

    ```cp -n [file] [destination]```
- Recursively copy a directory: 

    ```cp -r [dir] [destination]```
- Delete a file: 

    ```rm [file]```
- Delete a directory (empty):

    ```rmdir [dir]```
- Delete a directory (non-empty):

    ```rm -r [dir]```