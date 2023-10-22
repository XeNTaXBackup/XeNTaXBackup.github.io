## Post #1
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2012-07-20T11:49:22+00:00
- Post Title: quickbms ( PutCT command )

hello Dear Sir Luigi Auriemma

although this a banal subject but my scrupulosity don't let to skip it ...

i just managed to write a simple bms script that extract null terminated strings from a file and write them to a text file , so that they separated by a custom character like space, enter , comma ... 
but in all case of using PutCT command for this subject , raised an exception !
please check what is wrong here :

the content of file :

```
00 64 65 6C 74 61 00 65 70 73 69 6C 6F 6E 00 7A
65 74 61 00 65 74 61 00 74 68 65 74 61 00 69 6F
74 61 00 6B 61 70 70 61 00 6C 61 6D 62 64 61 00
6D 75 00 6E 75 00 78 69 00 6F 6D 69 63 72 6F 6E
00 70 69 00 72 68 6F 00 73 69 67 6D 61 00 74 61
75 00 75 70 73 69 6C 6F 6E 00 70 68 69 00 63 68
69 00 70 73 69 00 6F 6D 65 67 61 00

```

the bms script i wrote :
although we can coding it in an alternative way just by adding another  Put "0x20" BYTE after putct
but i don't know why the PutCT VAR TYPE CHAR [FILENUM] don't work properly even by -w switch according to the following documents of quickbms ?

```

for i = 0 < 20

get greek string
putct greek string -1 MEMORY_FILE
#putct greek string "0x20" MEMORY_FILE
Put "0x20" BYTE MEMORY_FILE

next i

log text.txt 0 64 MEMORY_FILE

```


> PutCT VAR TYPE CHAR [FILENUM]
>
> ...
>
>     these are EXACTLY like the Get* functions except for the fact that
>
>     they perform write operations.
>
>     for using these commands on a phisical file (so MEMORY_FILEs
>
>     excluded) MUST be used the -w option at runtime needed for both
>
>     technical and security reasons.
>
>     if you want to write a string without the NULL delimiter use:
>
>     putct "your_string" string -1

> GetCT VAR TYPE CHAR [FILENUM]
>
>     reads a string till the reaching of the CHAR delimiter.
>
> 
>
>     arguments
>
>       VAR       output variable
>
>       TYPE      ignored because doesn't exist a type in this operation
>
>       CHAR      the delimiter character as 8bit number
>
>       FILENUM   number of the file associated to the archive (0)
>
> 
>
>     examples:
>
>       GetCT NAME string 0x0a
>
>       GetCT NAME string 0x3b
>
>       set DELIMITER_BYTE long 0x0a
>
>       GetCT NAME string DELIMITER_BYTE
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-20T17:26:44+00:00
- Post Title: quickbms ( PutCT command )

thanx for the feedback.

well, the crash obviously a problem in any case and so I will fix it.

but for the rest the putct command acted correctly.
in short putct with char 0x20 (the space) on a string like "test test" will store "test "

in your file you have the first string equal to "alpha" so there is no 0x20 char in that string, in this case putct can do nothing because it continue to store the string char by char till it finds a 0x20 char that doesn't exist.
so when it arrives at the end of the variable quickbms crashes because is out of the memory assigned to the "alpha" string.

so it's all ok, no problem (except the crash obviously eh eh eh)
## Post #3
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2012-07-21T18:16:06+00:00
- Post Title: quickbms ( PutCT command )

thanks for your comment and UPDATE !
