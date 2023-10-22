## Post #1
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2013-12-30T23:07:58+00:00
- Post Title: K-On! Houkago Live!! .bin

Here's a quickbms script for the bin files in K-On! Houkago Live!!
If anyone can help with the .uno and .uvr files that would be much appreciated.

```
get UNK1 long
get FILES long
goto 0x50
get NULL3 long
for i = 0 < FILES
getdstring NAME 0x80
get OFFSET long
get SIZE long
get NULL4 long
get NULL5 long
log NAME OFFSET SIZE
next i
```
