## Post #1
- Username: titanic
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Nov 30, 2006 4:58 am
- Post datetime: 2007-10-12T19:42:31+00:00
- Post Title: Call of Duty 4 demo archive research.

First it is Awesome game. I like it!

I found its 2 type of Archive in cod4.
one is .iwd  like like cod2 that all quake engine pk3. can open use winzip. but only  img and snd files in there.

another is in zone\english .ff file.  it contains model, effect and level files.

remove 12 byte head. rest is zlib compressed.

after uncompressed you can get a block file.

I just  realize one thing:
int   file size (exclude file head 0x2c size )

but no idea for extract file from  block file at this time.
[code_post_gfx.rar](https://xentaxbackup.github.io/file/1354_code_post_gfx.rar)
## Post #2
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T11:28:16+00:00
- Post Title: Call of Duty 4 demo archive research.

I just took a look at it with a HEX editor. A lot of help texts are in there aswell, strings that might be outputted as subtitles or on-screen text in the game.

There was also something like a internal settings file (just look for ASCII 'origin') I have also seen some bits that looked like javascript/C#/C++ sourcecode??? // comment tags, {} brackets, etc.

The header of this file might be dynamic, since 'end ' (65 6E 64 00) looks like an indication the header is finished (not sure). The header itself is padded with FF's. Been looking around at the first few bytes, but other then that offset 0xFC + the first byte (data=0xF3) precisely covers till ASCII 'end tag', I am not sure what to do. 

I did found 0x4176 -> 0x111D2 contains some sort of constants, if you extract this range and split data by 0x00, you'd be able to make some sense of it. Not realy helpfull, but it's something 


Good luck and curious to see what comes out of it.

Sincerely,


Nick Kusters.
## Post #3
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2007-10-21T06:30:13+00:00
- Post Title: Call of Duty 4 demo archive research.

plz one or two snd file's COD4 , upload for  me . thanks...
