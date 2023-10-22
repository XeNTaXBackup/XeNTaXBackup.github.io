## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-29T22:05:40+00:00
- Post Title: Making memory file as "file 0"

```
# do stuff with the file and put it in memory file
filexor "stuff"
get size asize
log MEMORY_FILE 0 size
filexor ""

# now we actually read it

get ... MEMORY_FILE
get ... MEMORY_FILE

goto .... MEMORY_FILE

...

```


It gets kind of redundant, especially when I'm loading everything into memory first. Is there a way to make it so that I can treat file number 0 as MEMORY_FILE?
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-01T07:49:43+00:00
- Post Title: Making memory file as "file 0"

and why you use a memory_file?

filexor "stuff"
get DUMMY long
getdstring DUMMY 0x10
...

you don't need a memory_file
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-01T19:23:23+00:00
- Post Title: Making memory file as "file 0"

Oh.

LOL now that I think about it the memory file is kind of pointless.
