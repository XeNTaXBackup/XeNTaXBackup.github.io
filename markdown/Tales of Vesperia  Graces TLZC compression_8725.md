## Post #1
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2012-04-08T20:10:28+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

so some guy reverse-engineered the TLZC compression format used in most of the Tales of games.

[http://blog.lse.epita.fr/articles/8-sta ... ormat.html](http://blog.lse.epita.fr/articles/8-static-analysis-of-an-unknown-compression-format.html)

There's a python program at the bottom of the post, I couldn't get it to work though (I would get a 'list index out of range' error on line 37). Any way to convert it to a quickbms script?? Or if someone could get that python program to work, that's be great too!

sample TLZC-compressed files: [http://www.mediafire.com/?6423f9rml64tsmd](http://www.mediafire.com/?6423f9rml64tsmd)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-08T20:37:40+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

What game is this?
I couldn't get it to work either.

```
  File "decompress.py", line 39, in <module>
    decompress_tlzc(buf, open(sys.argv[2], "w"))
  File "decompress.py", line 31, in decompress_tlzc
    decompress_block(lzma_params, block, out, remaining)
  File "decompress.py", line 11, in decompress_block
    out.write(pylzma.decompress(block, size, maxlength=size))
TypeError: Error while decompressing: 6

```


.............
You should send the samples to the author.
## Post #3
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2012-04-08T21:08:25+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

They're from Tales of Vesperia. But hey, you got farther than I did in executing it, at least.

I sent the samples to the author, not expecting to get too much though.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-08T22:12:30+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

I made a quickbms script based on his post enjoy.

```
get name basename
string name + ".FPS4"
comtype MSF
get version long
get tzsize long
get tsize long
goto 0x1D
set blockcount tsize
math blockcount += 0xFFFF
math blockcount /= 0x10000
for i = 0 < blockcount
get zsize short
putarray 0 i zsize
next i
for i = 0 < blockcount
savepos offset
getarray ZSIZE 0 i
if tsize >= 0x10000
append
clog MEMORY_FILE OFFSET ZSIZE 0x10000
append
else
append
if ZSIZE == 0
log MEMORY_FILE OFFSET tsize
else
clog MEMORY_FILE OFFSET ZSIZE tsize
endif
append
endif
math tsize -= 0x10000
math offset + ZSIZE
goto offset
next i
get SIZE asize MEMORY_FILE
log name 0 SIZE MEMORY_FILE

```
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-08T23:03:52+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

Doesn't work for the book_enemy files.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-08T23:10:33+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

those files are null?
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-08T23:13:03+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

oops my bad
change the one line
i left a hard coded number in there from a file i tested.
updated post
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-08T23:21:51+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

Now it works for book_enemy_20, but still fails on the other non-null books_enemy's (eg: 18, 19).

It fails on the very last iteration of the loop.
Maybe you have to deal with the remaining block separately?
## Post #9
- Username: oathkeeper9918
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-08T23:33:46+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

done
## Post #10
- Username: oathkeeper9918
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jul 10, 2011 4:16 am
- Post datetime: 2012-04-08T23:54:51+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

Thanks! The script works perfectly for Vesperia's and Graces' files
## Post #11
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-10T07:50:35+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

> Reply from oathkeeper9918
>
> Thanks! The script works perfectly for Vesperia's and Graces' files

Did I make a mistake..? It doesn't work.



K-85.png (1.65 KiB) Viewed 351 times
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-10T15:35:49+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

> Reply from albert1905
>
> oathkeeper9918 wrote:Thanks! The script works perfectly for Vesperia's and Graces' files

Did I make a mistake..? It doesn't work.
K-85.png

replace

```
math blockcount / 0x10000
```


to

```
math blockcount /= 0x10000
```
## Post #13
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2014-05-11T14:14:53+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

> Reply from Ekey
>
> albert1905 wrote:oathkeeper9918 wrote:Thanks! The script works perfectly for Vesperia's and Graces' files

Did I make a mistake..? It doesn't work.
K-85.png

replace
Code: Select allmath blockcount + 0xFFFF
math blockcount / 0x10000

to
Code: Select allmath blockcount += 0xFFFF
math blockcount /= 0x10000

Thanks a lot.
## Post #14
- Username: jrush
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 25, 2012 6:10 pm
- Post datetime: 2014-05-14T23:29:51+00:00
- Post Title: Tales of Vesperia / Graces TLZC compression

Does this mean you can extract models from Tales of Graces F or Tales of Graces? I have some models from Vesperia Xbox but I want to know if you can get models from Vesperia PS3.
