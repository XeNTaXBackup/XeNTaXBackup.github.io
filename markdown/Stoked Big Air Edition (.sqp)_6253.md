## Post #1
- Username: DarkAngel
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jan 23, 2011 12:12 pm
- Post datetime: 2011-03-20T06:47:34+00:00
- Post Title: Stoked: Big Air Edition (.sqp)

Please, help me with unpacking .sqp

File:

[http://www.multiupload.com/WFAGTF0PH9](http://www.multiupload.com/WFAGTF0PH9)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-20T09:45:47+00:00
- Post Title: Stoked: Big Air Edition (.sqp)

interesting file format, the following is the script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get HEADER line
get SIZE line
get FILES line
for i = 0 < FILES
    get NAME line
    set SIZE string NAME
    string NAME >= "|"
    string SIZE &= "|"
    string SIZE <= 1
    putarray 0 i NAME
    putarray 1 i SIZE
next i
savepos OFFSET
for i = 0 < FILES
    getarray NAME 0 i
    getarray SIZE 1 i
    log NAME OFFSET SIZE
    math OFFSET += SIZE
next i
```
## Post #3
- Username: DarkAngel
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jan 23, 2011 12:12 pm
- Post datetime: 2011-03-20T18:37:07+00:00
- Post Title: Stoked: Big Air Edition (.sqp)

aluigi.

Thanks for the script, everything is ok unpacked.
