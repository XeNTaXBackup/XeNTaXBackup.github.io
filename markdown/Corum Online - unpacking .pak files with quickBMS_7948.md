## Post #1
- Username: modelone
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 02, 2011 5:07 pm
- Post datetime: 2011-12-28T15:51:34+00:00
- Post Title: Corum Online - unpacking *.pak files with quickBMS

Hey, i would like to unpack packed files from game files named *.pak . I read some tutorials, but unfortunately cant understand them. Here is my file: [http://speedy.sh/Hkqed/Npc.pak](http://speedy.sh/Hkqed/Npc.pak). Thank you for help
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-31T11:04:18+00:00
- Post Title: Corum Online - unpacking *.pak files with quickBMS

the script for quickbms is ready, write the name of the game and I will post it
## Post #3
- Username: modelone
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 02, 2011 5:07 pm
- Post datetime: 2011-12-31T15:47:20+00:00
- Post Title: Corum Online - unpacking *.pak files with quickBMS

Nice. Thank you   Name of the game is: Corum Online (Client ver. 4.7.5.2)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-31T18:33:14+00:00
- Post Title: Corum Online - unpacking *.pak files with quickBMS

```
# script for QuickBMS http://quickbms.aluigi.org

get PATH basename
string PATH += /
get DUMMY long
get FILES long
goto 0x5c
for i = 0 < FILES
    get XSIZE long
    get SIZE long
    get NAMESZ long
    math NAMESZ += 1
    get XOFFSET long
    getdstring DUMMY 0x10
    getdstring NAME NAMESZ
    savepos OFFSET
    set FNAME string PATH
    string FNAME += NAME
    log FNAME OFFSET SIZE
    math OFFSET += SIZE
    goto OFFSET
next i
```
