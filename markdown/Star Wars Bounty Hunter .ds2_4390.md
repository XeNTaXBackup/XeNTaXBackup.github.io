## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-04-26T09:08:14+00:00
- Post Title: Star Wars: Bounty Hunter *.ds2

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-04-26T09:35:21+00:00
- Post Title: Star Wars: Bounty Hunter *.ds2

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-04-26T14:36:49+00:00
- Post Title: Star Wars: Bounty Hunter *.ds2

Here's the script I've written so far, but there are files inside the header list that actually aren't available. How can I test if a file is there and if not, continue to the next i?

```
reverselong FILES
set CURR 0x20
goto CURR 0

for i = 0 < FILES
   get NAME string 0
   math CURR += 0x100
   log MEMORY_FILE CURR 0x60 0
   math CURR += 0x60
   open FDSE NAME 1
   get SIZE asize 1
   math SIZE -= 0x80
   append
   log MEMORY_FILE 0x80 SIZE 1
   append
   string NAME -= 3
   string NAME += "dsp"
   get MSIZE asize MEMORY_FILE
   log NAME 0 MSIZE MEMORY_FILE
   goto CURR
next i
```

Edit: Only six files are missing - of course it's possible to create fake files but would be nice to have a "skip file" option. 
These files are missing:
ce_normal_01.ds2
ce_normal_03.ds2
ge_normal_07.ds2
ge_normal_10.ds2
ge_normal_11.ds2
ge_normal_12.ds2
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-26T14:53:22+00:00
- Post Title: Star Wars: Bounty Hunter *.ds2

uhmmm the bms language doesn't implement this possibility, although would cost me nothing to implement a solution in quickbms (maybe the same I adopted for findloc).
so a 0.4.2a version? :)
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-26T16:03:44+00:00
- Post Title: Star Wars: Bounty Hunter *.ds2

well this customization was enough good so I have just implemented it in version 0.4.2a just released.
example:

```
    get FNAME line   # file with the names of the files to open one-per-line
    open FDSE FNAME 1 EXIST
    if EXIST == 0
        print "the file %FNAME% doesn't exist"
    else
        print "the file %FNAME% exists"
    endif
next
```
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-04-26T16:10:14+00:00
- Post Title: Star Wars: Bounty Hunter *.ds2

YOU'RE MY HERO LUIGI!!! 
Thanks a lot for this really useful option!
