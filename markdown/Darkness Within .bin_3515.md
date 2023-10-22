## Post #1
- Username: shaneno
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Oct 17, 2008 12:15 pm
- Post datetime: 2009-05-29T14:12:29+00:00
- Post Title: Darkness Within *.bin

Any one can make a bms script of  Darkness Within *.bin files ?
The demo version can be find here.
[http://www.zoetropeint.com/ln/data/Dark ... n_Demo.exe](http://www.zoetropeint.com/ln/data/Darkness_Within_Demo.exe)
## Post #2
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-05-29T17:18:45+00:00
- Post Title: Darkness Within *.bin

this is the simpliest ever format dercipting this game files! And if someone who knows writing BMS scripts will not do this then the idea is clear! - shut this forum down.
## Post #3
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2009-05-30T09:34:58+00:00
- Post Title: Darkness Within *.bin

> Reply from Gocha
>
> this is the simpliest ever format dercipting this game files! And if someone who knows writing BMS scripts will not do this then the idea is clear! - shut this forum down.

what?   

anyway, the files looks like are not compressed or crypted but the header is, so like filenames (if there are some..). Months ago I found a file reinserter in the russian translation so if you just want to translate the game it could be easily done by manually extracting the texts and then using that program to reinsert everything. You can find russian translation here: [http://www.zoneofgames.ru/](http://www.zoneofgames.ru/) (you need to sign-up)
## Post #4
- Username: shaneno
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Oct 17, 2008 12:15 pm
- Post datetime: 2009-05-30T13:14:17+00:00
- Post Title: Darkness Within *.bin

> Reply from Vash
>
> Gocha wrote:this is the simpliest ever format dercipting this game files! And if someone who knows writing BMS scripts will not do this then the idea is clear! - shut this forum down.

what?   

anyway, the files looks like are not compressed or crypted but the header is, so like filenames (if there are some..). Months ago I found a file reinserter in the russian translation so if you just want to translate the game it could be easily done by manually extracting the texts and then using that program to reinsert everything. You can find russian translation here: http://www.zoneofgames.ru/ (you need to sign-up)

Very thank you for your information.
But i don't know russian,and i found 7 pages about Darkness Within there.
Can you post the thread's url or just post the tool here?
Thanks!
## Post #5
- Username: shaneno
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-30T17:47:00+00:00
- Post Title: Darkness Within *.bin

This will extract the files but no names I will see if I can figure the names out.

```
get UNK short
for i = 0 < FILES
math NAME += 1
get UNK1 long
get OFFSET long
get SIZE long
get UNK2 long
Math OFFSET += 0x3A04
log NAME OFFSET SIZE
next i
```
## Post #6
- Username: shaneno
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Oct 17, 2008 12:15 pm
- Post datetime: 2009-05-31T11:58:11+00:00
- Post Title: Darkness Within *.bin

> Reply from chrrox
>
> This will extract the files but no names I will see if I can figure the names out.
Code: Select allget FILES short
get UNK short
for i = 0 < FILES
math NAME += 1
get UNK1 long
get OFFSET long
get SIZE long
get UNK2 long
Math OFFSET += 0x3A04
log NAME OFFSET SIZE
next i

Very thanks!
## Post #7
- Username: shaneno
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Oct 17, 2008 12:15 pm
- Post datetime: 2009-05-31T12:04:11+00:00
- Post Title: Darkness Within *.bin

But the scripts.bin can't be extracted.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-31T12:12:49+00:00
- Post Title: Darkness Within *.bin

scripts.bin is very random. it contains the file names and different files.
