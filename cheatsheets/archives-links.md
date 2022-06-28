## Archives and Links

- Create a tape archive without compression:

    ```tar cf [archivename.tar] [target]```
- Add `v` option for verbose 
- Create a tape archive with gzip compression: 

    ```tar cfz [archivename.tgz] [target]```
- Create a tape archive with bzip2 compression:

    ```tar cjf [archivename.bz2] [target]```
- Create a tape archive with compression matching the file extension:

    ```tar caf [archivename] [target]```
- Unpack a tape archive without compression:

    ```tar xf [archive]```
- Unpack a tape archive to a directory other than the working directory: 

    ```tar xf [archive] -C [exdir]```
- Unpack a gzip compressed tape archive:

    ```tar xfz [archive]```
- Unpack a bzip2 compressed tape archive: 

    ```tar xjf [archive]```
- Append a file to an uncompressed tape archive:

    ```tar -rf [archive] [file]```
- Remove a file from an uncompressed tape archive:

    ```tar --delete --file=[archive] [file]```
- List contents of a tape archive:

    ```tar tf [archive]```
- Create a zip archive: 

    ```zip -r [archivename.zip] [target]```
- Create an encrypted zip archive with a password: 

    ```zip -re [archivename.zip] [target]```
- Unzip a zip archive:

    ```unzip [archive]```
- Unzip a zip archive to a directory other than the working directory: 

    ```unzip [archive] -d [exdir]```

-----

## Links

- Create a symbolic link: 

    ```ln -s [source file] [link name]```