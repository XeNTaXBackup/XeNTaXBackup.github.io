## Post #1
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2010-10-19T21:37:57+00:00
- Post Title: Black Mirror 2

Hello ... 
I can not write the script for Black Mirror 2 speech.dat to file .... But my knowledge is insufficient for this 
file is too big to my upload so I add photo

```
http://img257.imageshack.us/img257/2229/bm2speech.jpg
```

and my script I wrote

```
get FILES long
for i < FILES
     getdstring NAME 0x33 # one file is hex 0x33 , two file is hex 0x2E
     get ZSIZE long
     get SIZE long 
     get OFFSET long
     clog NAME OFFSET ZSIZE SIZE
next i

```

Thank you for your help
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-10-20T05:52:21+00:00
- Post Title: Black Mirror 2

```
get FILES long
for i = 0 < FILES
  get NameSize long
  getdstring File_Name NameSize
  get Start_Pos long
  get File_Size long
  log File_Name Start_Pos File_Size
next i
```
## Post #3
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2010-10-20T12:26:20+00:00
- Post Title: Black Mirror 2

> Reply from bacter
>
> Code: Select all# Black Mirror II - "sounds.dat" file extractor script for QuickBMS
get FILES long
for i = 0 < FILES
  get NameSize long
  getdstring File_Name NameSize
  get Start_Pos long
  get File_Size long
  log File_Name Start_Pos File_Size
next i
Thank you ... 
and we could please explain what each command? Learn that only a few days so I would like to know what and how
