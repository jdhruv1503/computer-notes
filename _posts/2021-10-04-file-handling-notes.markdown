---
title:  "File Handling - Notes"
date:   2021-10-04 11:40:42 +0530
categories: notes
permalink: /:title
---

## Opening and closing files

Files can be opened using `fileObj = open(filename, mode)` (default mode is "r"). The `filename` can be provided as `"c:\\temp\\data.txt"` or as `r"c:\temp\data.txt"` (`r` means raw string).

Files can be closed using `fileObj.close()`. The variable `fileObj` is called a file object or file handle.

### File access modes

|Filemode|Binary filemode|Description|
|`"r"`|`"rb"`|Read|
|`"w"`|`"wb"`|Write|
|`"a"`|`"ab"`|Append|
|`"r+"`|`"rb+"`|Read, write|
|`"w+"`|`"wb+"`|Write, read|
|`"a+"`|`"ab+"`|Append, read|

Note
: For `read` file pointer starts at start of file, while for `append` file pointer starts at the end of file.

## Text files

Text files can be read using these commands:

|Function|Description|
|`fileObj.read(n)`|Reads `n` bytes. If `n` is not provided whole file is read.|
|`fileObj.readline(n)`|Reads `n` bytes. If `n` is not provided one line is read.|
|`fileObj.readlines()`|Reads all lines and returns a list of the lines.|

Text files can be written using these commands:

|Function|Description|
|`fileObj.write(str1)`|Writes `str1` to file.|
|`fileObj.writelines(list1)`|Writes all lines from `list1`.|

Note
: `file.flush()` can be used to flush buffer without having to `close()` the file.

### Processing input

`stringName.rstrip(char)` can be used to remove all `char`s from the right side of a string. `lstrip()` is similar.

## Binary files

A Python binary file can store Python object(s). This Python object can be written to the binary file as `picke.dump(objectToBeWrittenName, fileObject)`

A Python binary file can be read using `variableName = pickle.load(fileObject)`

### `with` statement

In order to avoid running into end of file errors, syntax `with open(myFile, accessType) as fileObject:` must be used. This codeblock will also automatically close the file.

### Iterating through a binary file (example)

```
try:
    while True:
        dict = pickle.load(file)
        sum += dict('Amount')
except EOFError:
    file.close()
```

## Pointer functions

`fileObj.tell()` function returns index of pointer.

`fileObj.seek(offset, mode)` function shifts the pointer by `offset` bytes. Modes are: `0` for offsetting from start of file (default if `mode` not given), `1` for offsetting from current position, `2` for offsetting from end of file.

## CSV files

While importing make sure that EOL character is set correctly using `fileObj - open("file.csv", "r", newline='')`

|Function|Description|
|`writerObj = csv.writer(fileObject, delimiter = '|')`|Makes a writer object `writerObj`.|
|`writerObj.writerow(sequence)`|Writes sequence `sequence` as a row.|
|`writerObj.writerows(list)`|Writes sequences in the list of sequences `list` as rows.|
|`readerObj = csv.reader(fileObj)`|Makes a reader object, which can be iterated through.|