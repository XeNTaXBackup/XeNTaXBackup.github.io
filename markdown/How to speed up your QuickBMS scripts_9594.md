## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-09-04T00:31:11+00:00
- Post Title: How to speed up your QuickBMS scripts

When processing large files or small portions of data in huge loops, scripts can be really slow. Often it's because of faulty code. So here are some general tips for QuickBMS coders to make your scripts faster.  This list may be updated in the future.

1. Avoid double calculation
avoid calculating variables inside a loop when you can do so outside. Example: 

```
set DAT 0x100
for i = 1 <= 10000
    get FSIZE asize      # same operation each loop
    math FSIZE -= HEADER #              "
    set SUB i
    math SUB *= DAT
    math FSIZE -= SUB
next i
```

should be corrected to

```
set DAT 0x100
get TSIZE asize
math TSIZE -= HEADER # one calculation before the loop
for i = 1 <= 10000
    set FSIZE TSIZE # just take the already calculated variable
    set SUB i
    math SUB *= DAT
    math FSIZE -= SUB
next i
```


2. Avoid appending (thanks for this tip, Luigi  )
Instead of

```
math CYCLES /= 8
set OFFSET 0
append
for i = 1 <= CYCLES
    log MEMORY_FILE OFFSET 8
    math OFFSET += 8
next i
append
```

use

```
math CYCLES /= 8
for i = 1 <= CYCLES
    getDstring DATA 8
    putDstring DATA 8 MEMORY_FILE
next i
```


3. Pre-allocate memory
Whenever you have to write something to MEMORY_FILE, set it's size first:

```
log MEMORY_FILE 0 0
```

If you don't know the size of the complete file without running through the data and getting single block sizes (e.g. when demultiplexing certain video formats), it's faster to pre-allocate the memory in one loop and then fill it in a second one:

```
savepos MYOFF
do
    get MSIZE long
    savepos OFFSET
    math PSIZE += MSIZE
    putVarChr MEMORY_FILE PSIZE 0
    log MEMORY_FILE 0 0
while [ending argument]
goto MYOFF
do
    get MSIZE long
    savepos TEMPOFF
    getDstring DATA MSIZE
    putDstring DATA MSIZE MEMORY_FILE
    math TEMPOFF += MSIZE
    goto TEMPOFF
while [ending argument]
```
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-09-04T01:08:28+00:00
- Post Title: How to speed up your QuickBMS scripts

A lot of this stuff is really applicable to programming in general: whenever you have a loop, you want it as "tight" as possible (meaning it does as little as possible), to allow the program to get through it faster. Actually, on that note, I wonder if your second "Pre-allocate memory" example would be even faster if you separated the 2-cycle loop into separate loops, so there's no overhead from the If block:

```
do
    get MSIZE long
    savepos OFFSET
    math PSIZE += MSIZE
while [ending argument]
putVarChr MEMORY_FILE PSIZE 0
log MEMORY_FILE 0 0
do
    get MSIZE long
    savepos OFFSET
    append
    log MEMORY_FILE OFFSET MSIZE
    append
while [ending argument]
```

(also, is there a way to lose the append pair in the second loop? using it goes against your own advice to avoid it, after all  )

> Reply from AlphaTwentyThree
>
> Code: Select all]get CYCLES asize
math CYCLES /= 8
for i = 1 <= CYCLES
    getDstring DATA 8
    putDstring DATA 8 MEMORY_FILE
next i
Is the extra "]" meant to be at the beginning of that?
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-04T03:38:56+00:00
- Post Title: How to speed up your QuickBMS scripts

Is the reason for dropping the append for purely I/O reasons? Or is there something else to it?
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-09-04T12:11:17+00:00
- Post Title: How to speed up your QuickBMS scripts

> Reply from Dinoguy1000
>
> Actually, on that note, I wonder if your second "Pre-allocate memory" example would be even faster if you separated the 2-cycle loop into separate loops, so there's no overhead from the If block
Yeah, you're right.  Changed it. 

> Reply from Dinoguy1000
>
> Also, is there a way to lose the append pair in the second loop? using it goes against your own advice to avoid it, after all
Hm, I haven't tested that. I've changed it BUT it could be slower because the variable (i.e. the data for the memory file) is really big and there's no pre-allocated memory for it I think. If I'm wrong, please correct me Luigi.  If so, it would of course be better to add another if-case to use getDstring for MSIZE < [some value] and the append and log command for data that's bigger than this value. Would be nice to know, so if you see this, Luigi, please post!

> Reply from Dinoguy1000
>
> Is the extra "]" meant to be at the beginning of that?
Nope.  Corrected.

> Reply from finale00
>
> Is the reason for dropping the append for purely I/O reasons? Or is there something else to it?
No, just that the speed gain is immense.
