## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-04-06T14:53:56+00:00
- Post Title: 5244465A - Natalie Brooks - The Treasures of the Lost Kin

I will appreciate any help or guidance to unpack the "data" archive from Adventures of Natalie Brooks.
The database can be downloaded here: [http://pretorius.za.com/brooks/data.rar](http://pretorius.za.com/brooks/data.rar) ("data" file packed as rar)

Best Regards

Hendrik Pretorius
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-05T14:47:43+00:00
- Post Title: 5244465A - Natalie Brooks - The Treasures of the Lost Kin

not the max of the simplicity but works (-o option suggested because some files have the same names):

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "RDFZ"
get SIZE long
getdstring NAME SIZE
if NAME != "Zlib" # I have tested only this archive
    cleanexit
endif

get ZSIZE long  # block size
math ZSIZE -= 4
get SIZE long
savepos INFO_OFFSET

clog MEMORY_FILE INFO_OFFSET ZSIZE SIZE

goto 0x10 MEMORY_FILE   # quick way
get FOLDERS long MEMORY_FILE
savepos FOLDERS_OFFSET MEMORY_FILE
for i = 0 < FOLDERS
    get NAMESZ long MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
next i
get FILES long MEMORY_FILE
savepos FILES_OFFSET MEMORY_FILE

math INFO_OFFSET += ZSIZE
goto INFO_OFFSET
get FILES long
savepos INFO_OFFSET
for i = 0 < FILES
    goto INFO_OFFSET
    get OFFSET long
    get ZSIZE long
    get FOLDERID long
    get FILEID long
    get ZIP long
    savepos INFO_OFFSET

    set FULLNAME ""
    goto FOLDERS_OFFSET MEMORY_FILE
    for j = 0 <= FOLDERID
        get NAMESZ long MEMORY_FILE
        getdstring NAME NAMESZ MEMORY_FILE
    next j
    string FULLNAME += NAME

    goto FILES_OFFSET MEMORY_FILE
    for j = 0 <= FILEID
        get NAMESZ long MEMORY_FILE
        getdstring NAME NAMESZ MEMORY_FILE
    next j
    string FULLNAME += \
    string FULLNAME += NAME

    if ZIP == 0
        log FULLNAME OFFSET ZSIZE
    else
        goto OFFSET
        get SIZE long
        math OFFSET += 4
        math ZSIZE  -= 4
        clog FULLNAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #3
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2009-12-27T01:05:45+00:00
- Post Title: 5244465A - Natalie Brooks - The Treasures of the Lost Kin

Thx aluigi!
