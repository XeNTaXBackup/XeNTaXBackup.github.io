## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-25T15:36:16+00:00
- Post Title: [XBox 360] Infernal - *.vfs

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-25T16:29:29+00:00
- Post Title: [XBox 360] Infernal - *.vfs

the script will produce some duplicates because the handling of the folders structure should be performed by using the first table (the table of the folders) anyway the output is ok also using this easier method:

```

idstring VFS2
get BASE_NAME basename

get FOLDERS long
savepos OFFSET
math SIZE = FOLDERS
math SIZE *= 0x14
log MEMORY_FILE2 OFFSET SIZE
math OFFSET += SIZE

goto OFFSET
get FILES long
savepos OFFSET
math SIZE = FILES
math SIZE *= 0x18
log MEMORY_FILE OFFSET SIZE
math OFFSET += SIZE

goto OFFSET
get NAMES_OFF long
savepos BASE_OFF

goto NAMES_OFF
get NAMES long
for i = 0 < NAMES
    get NAMESZ long
    getdstring NAME NAMESZ
    putarray 0 i NAME
next i
get NAMES long
for i = 0 < NAMES
    get NAMESZ long
    getdstring NAME NAMESZ
    putarray 1 i NAME
next i

for i = 0 < FILES
    get CRC long MEMORY_FILE
    get NAME_NUM long MEMORY_FILE
    get DUMMY long MEMORY_FILE
    get FOLDER_NUM long MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get SIZE long MEMORY_FILE

    math OFFSET += BASE_OFF
    getarray NAME 0 NAME_NUM
    getarray FOLDER 1 FOLDER_NUM
    set FULLNAME string BASE_NAME
    string FULLNAME += /
    string FULLNAME += FOLDER
    string FULLNAME += /
    string FULLNAME += NAME
    log FULLNAME OFFSET SIZE
next i
```
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-25T23:57:09+00:00
- Post Title: [XBox 360] Infernal - *.vfs

Wow, that was amazingly quick! 

The folder structure isn't represented correctly, but I was only after the music. 

Thanks a lot!
