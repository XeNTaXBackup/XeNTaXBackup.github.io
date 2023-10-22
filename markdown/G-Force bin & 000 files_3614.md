## Post #1
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-07-28T07:34:34+00:00
- Post Title: G-Force "bin" & "000" files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-28T21:32:07+00:00
- Post Title: G-Force "bin" & "000" files

Will take a look
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-14T17:11:25+00:00
- Post Title: G-Force "bin" & "000" files

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

open FDDE "bin" 0
set EXT string ""
string EXT += 0 # work-around because quickbms consider it a number
string EXT += 0
string EXT += 0
open FDDE EXT 1

get DUMMY long
get BINSZ long
get FILES long
get DUMMY long
get DUMMY_OFF long

math NAME_OFF = FILES
math NAME_OFF *= 4
math NAME_OFF += 16
math NAME_OFF += DUMMY_OFF
math NAME_SIZE = BINSZ
math NAME_SIZE -= NAME_OFF
log MEMORY_FILE NAME_OFF NAME_SIZE
set INIT_ROT long 0xea

for i = 0 < FILES
    get SIZE long
    getdstring DUMMY 16
    get OFFSET long
    get DUMMY long

    savepos NAME_OFF MEMORY_FILE
    set j long INIT_ROT
    do
        getvarchr CHR MEMORY_FILE NAME_OFF
        math CHR -= j
        math CHR &= 0xff
        putvarchr MEMORY_FILE NAME_OFF CHR
        math NAME_OFF += 1
        math j += 1
    while CHR != 0
    math INIT_ROT += 1
    get NAME string MEMORY_FILE

    log NAME OFFSET SIZE 1
next i
```
note that only filelist.bin contains the names of the files (absolute paths like "x:\gforce\binary\_bin_pc\int_demo.edb", most like comments than names) so the files of the other archives will be nameless.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-14T19:19:03+00:00
- Post Title: G-Force "bin" & "000" files

Nice work. I didn't take that look.
