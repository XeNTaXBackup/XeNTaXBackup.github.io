## Post #1
- Username: Maspayno
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-21T22:24:23+00:00
- Post Title: QUICKBMS GUIDE 3 IF ELSE

Ok sorry it took me a little longer for this tutorial but I wanted to make sure I had a good example to show for this.
Step 1
The game we will be looking at is Beach Fun Summer Challenge for the WII.
Step 2

> Open the file pc_only.dat in your favorite hex editor
>
> I will be using HxD

Step 3

> Looking at this file I notice 2 Files in this archive right away
>
> dvdpc\pc\misc\fonts\debug.timg and dvdpc\common\misc\fonts\debug.fnt
>
> So this tells us we have 2 files and the directory path is included in the name.
>
> Make sure you just take note of that and we will move on to the next step.
Step 4

> The file starts with the words BeachFun
>
> so this will be our idstring
>
> so in bms we will write.

```
idstring "BeachFun"
```

Step 5

> Next we have 0x18 bytes of 0's so we could write
>
> getdstring NULL1 0x18
>
> but there is a better command called goto
>
> so lets use this great command in bms like this
>
> goto 0x20
>
> this will take us to offset 0x20 in the archive
so now we have

```
goto 0x20

```

and we end up here

Step 6

> Now we are working with console archives so we need to change our endian
>
> to get the right values and we do that with the command
>
> endian BIG
>
> this tells us to read the value as it appears in the archive so the number would be
>
> 00 00 00 02 and it will not get reversed to 02 00 00 00
>
> so 00 00 00 02 is equal to 2 and hey that is the number of files in this archive 
>
> so lets write what we have so far in bms.

```
goto 0x20
endian BIG
get FILES long

```

Step 7

> the next 0x1C bytes are the same in all archives from this game and so not seem to
>
> mean anything so we will skip over them with out new command goto
>
> so lets write it as this
>
> goto 0x40
so far we have

```
goto 0x20
endian BIG
get FILES long
goto 0x40

```

Step 8

> Now we are at the start of the file name.
>
> lets see how long it goes on before we reach something besides a 0
>
> remember always try to work in groups of 2 or 4 bytes as that is the
>
> most common way variables will be stored.
>
> so highlight the next 0x68 bytes and you will see it is the same length
>
> between the archive name and the next long variable for both of the files.
>
> so we will write in bms
>
> getdstring NAME 0x68

```
goto 0x20
endian BIG
get FILES long
goto 0x40
getdstring NAME 0x68

```


Step 9

> ok now we have the next 4 bytes 00 00 01 40
>
> and if we look at your archive that seems to be where the data begins
>
> so we have our offset value lets store that
>
> get OFFSET long
> 

```
goto 0x20
endian BIG
get FILES long
goto 0x40
getdstring NAME 0x68
get OFFSET long

```

Step 10
so now we have 0x14 bytes remaining before the next name begins
so lets break those down into long variables for now so we can visualize it better
get UNK1 long
get UNK2 long
get NULL1 long
get UNK3 long
get NULL2 long
so this completes our pattern for writing our extractor so lets clean up our code.

```
goto 0x20
endian big
get FILES long
goto 0x40
for i = 0 < FILES
getdstring NAME 0x68
get OFFSET long
get UNK1 long
get UNK2 long
get NULL long
get UNK3 long
get NULL2 long
clog NAME OFFSET ZSIZE SIZE
next i

```


> This code starts the loop with the command 
>
> for i = 0 < FILES
>
> and it starts right at the begging of the file name.
>
> I wrote clog NAME OFFSET ZSIZE SIZE
>
> because there is nothing human readable and no 00's in
>
> the archive where the data begins indicating it is compressed.
>
> I saved the variables as UNK if they have a value other than 0
>
> and as NULL if their value was 0
Step 11

> Now we just need to figure out ZSIZE and SIZE to extract these files.
>
> lets look at our variables
>
> UNK1 = 00 00 64 D0
>
> UNK2 = 00 00 00 01
>
> UNK3 = 00 02 AB 20
>
> There are a few ways to figure out what values go where
>
> method 1.
>
> subtract the offset of file 1 from the offset of file 2
>
> that will give us the zipped size of the file so
>
> 00 00 66 20 - 00 00 01 40 = 00 00 64 E0
>
> this tells us 00 00 64 D0 must be the zip size
>
> and there must be some padding in between the files.
>
> Method 2 is just look at the values and use common sense
>
> it is not a size of 1 do UNK2 is crossed out
>
> and now what one is bigger UNK1 or UNK3
>
> UNK3 is bigger so therefore it must be the uncompressed size.
>
> so we have our variables
>
> UNK1 = zipped size
>
> UNK2 = one
>
> unk3 = SIZE
>
> so lets write that in bms

```
goto 0x20
endian big
get FILES long
goto 0x40
for i = 0 < FILES
getdstring NAME 0x68
get OFFSET long
get ZSIZE long
get ONE long
get NULL long
get SIZE long
get NULL2 long
clog NAME OFFSET ZSIZE SIZE
next i

```

Step 11

```
yay it worked we got 2 files
but now lets try it on Characters.dat
hey wait we got a few files and then it got an error.
```


Step 12
If we do a ctrl + f and go to that location in the archive we see it listed there and it looks the same
but if we look closer the value of ONE is set to 00 00 00 00
this means it must indicate weather the file is compressed or not
1 gives a value of compressed 0 says the file is un compressed.
so lets write that in bms

```
goto 0x20
endian big
get FILES long
goto 0x40
for i = 0 < files
getdstring NAME 0x68
get OFFSET long
get ZSIZE long
get ZIP long
get NULL long
get SIZE long
get NULL2 long
if ZIP == 1
clog NAME OFFSET ZSIZE SIZE
else
log NAME OFFSET ZSIZE
endif
next i

```

This says that when the value of ZIP "what we called ONE earlier"
is equal to 1 run the command 
clog NAME OFFSET ZSIZE SIZE
but if it is not equal to 1 run the command
log NAME OFFSET ZSIZE
then we end it with the endif statement.
Now when we run our extraction it works without errors 

As a bonus you can view these models and animations in granny viewer.
[http://www.radgametools.com/granny/download.html](http://www.radgametools.com/granny/download.html)
let me know what you think of the new format.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-22T14:12:59+00:00
- Post Title: QUICKBMS GUIDE 3 IF ELSE

about the if/else statement it's also good to specify that from one of the recent versions of QuickBMS I have added the useful "elif"/"else if" which allows to specify multiple "if"... and it's very very useful in some cases.
example:

```
if MYVAR < 0
    math MYVAR = 0
elif MYVAR == 0
    math MYVAR += 1
else if MYVAR == 2
    math MYVAR -= 2
elif MYVAR > 1000
    math MYVAR *= -1
else
    math MYVAR += 1000
endif
print "%MYVAR%"
```
## Post #3
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-06-24T08:45:59+00:00
- Post Title: QUICKBMS GUIDE 3 IF ELSE

Thanks guys! It's the great way you do!
## Post #4
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-06-24T14:09:27+00:00
- Post Title: QUICKBMS GUIDE 3 IF ELSE

thx chrrox
## Post #5
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-06-27T07:02:16+00:00
- Post Title: QUICKBMS GUIDE 3 IF ELSE

I Wish You Success in Whatever you want $
## Post #6
- Username: Maspayno
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-28T05:34:48+00:00
- Post Title: QUICKBMS GUIDE 3 IF ELSE

I noticed I had not enabled the option to thank a user in this Tutorial forum yet. I have done so now
## Post #7
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-12-23T15:19:17+00:00
- Post Title: QUICKBMS GUIDE 3 IF ELSE

thanks if someone show us how can we decompress Granny Viewer .gr2 file formats ?
samples attached !
[characters.rar](https://xentaxbackup.github.io/file/2654_characters.rar)
## Post #8
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-12-28T12:02:48+00:00
- Post Title: QUICKBMS GUIDE 3 IF ELSE

this problem solved thousands years ago !!!  

> Reply from shekofte
>
> thanks if someone show us how can we decompress Granny Viewer .gr2 file formats ?
samples attached !
[viewtopic.php?f=16&t=1805&start=30&st=0&sk=t&sd=a](http://forum.xentax.com/viewtopic.php?f=16&t=1805&start=30&st=0&sk=t&sd=a)
## Post #9
- Username: Ranker
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 05, 2011 5:03 am
- Post datetime: 2011-01-08T05:12:05+00:00
- Post Title: QUICKBMS GUIDE 3 IF ELSE

I wish this tutorial was more pattern-based and not so "do this" and "do that".  I really want to start extracting files, but I'm just not understanding the rational for any of the steps or how QUICKBMS intrinsically works - so I'm finding it very difficult to apply it to my project and construct my own strategies.

Thanks for the tutorial though.
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-01-08T11:43:25+00:00
- Post Title: QUICKBMS GUIDE 3 IF ELSE

post a sample in the research area to get some help.
