## Post #1
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-06-21T14:22:21+00:00
- Post Title: Doctor Who - The Adventure Games .Epc Files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-21T17:12:23+00:00
- Post Title: Doctor Who - The Adventure Games .Epc Files

the format of the file is horrible so the following is the only 5-minutes thing I got out (and for sure I will not spend other time on this):

```
do
    savepos OFFSET
    get DUMMY long
    get DUMMY long
    getdstring SIGN 4
    get SIZE long
    math NEXT_OFF = OFFSET
    math NEXT_OFF += SIZE
    if SIGN == "EMTR"
        math OFFSET += 0x7c
        goto OFFSET
        get SIZE long
        math OFFSET += 0x14
        math TMP = OFFSET
        math TMP += SIZE
        goto TMP
        get NAME string
    else
        set NAME string ""
    endif
    log NAME OFFSET SIZE
    goto NEXT_OFF
while NEXT_OFF < FULLSIZE
```
## Post #3
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-06-21T17:31:09+00:00
- Post Title: Doctor Who - The Adventure Games .Epc Files

lol, well, that is quite awesome for 5 minutes 
i get a folder of textures, though they are unusable...it says the format is damaged or something like that...
and i get .neo files, which i asume are either models, or textures according to this [http://www.fileinfo.com/extension/neo](http://www.fileinfo.com/extension/neo)
but it isn't very reliable info concerning games...thanks anyway...
## Post #4
- Username: SimpleText
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 20, 2011 3:12 am
- Post datetime: 2011-11-19T19:22:49+00:00
- Post Title: Doctor Who - The Adventure Games .Epc Files

has anyone tried to use OpenGLExtractor (OGLE) with GLIntercept to rip the textures and models from this game? I'm going to set it up and see what I can get.. I will post my results when I get it going. I found this thread looking for .eps file format; I was intending to rip the character models to use for a GTA IV mod 

This utility when configured correctly can probably rip the files out of this game, not sure of how it will work but I have used it in the past on similar adventure-style games ... I also used to use it to rip models and textures from Second Life and it worked great. 

[http://www.gamevixenzone.com/gvz/viewto ... f=47&t=458](http://www.gamevixenzone.com/gvz/viewtopic.php?f=47&t=458)

edit: the link to OGLE is dead there but thanks to this forum I found another way to download it courtesy of the Internet Archive's WayBack Machine  Thanks, revelation!

Here are both links if anyone is interested in setting it up on your system:

[http://code.google.com/p/glintercept/downloads/list](http://code.google.com/p/glintercept/downloads/list)

[http://web.archive.org/web/200902021503 ... g/download](http://web.archive.org/web/20090202150340/http://ogle.eyebeamresearch.org/download)
## Post #5
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-11-19T19:28:21+00:00
- Post Title: Doctor Who - The Adventure Games .Epc Files

well, thats actually the same as using 3d Ripper DX, isn't it? i think its just a different library.
It might get you the models as they are in that specific state, but it wont get you any rigging pose, and the rotations will probably be off...
## Post #6
- Username: SimpleText
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 20, 2011 3:12 am
- Post datetime: 2011-11-19T19:37:27+00:00
- Post Title: Doctor Who - The Adventure Games .Epc Files

true, but it is a good start to have something to work with for my purposes anyway  ... have never heard of 3d Ripper DX I will check it out maybe it is updated more frequently
## Post #7
- Username: SimpleText
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 20, 2011 3:12 am
- Post datetime: 2011-11-19T19:43:30+00:00
- Post Title: Doctor Who - The Adventure Games .Epc Files

from the website: 3D Ripper DX supports only DirectX 6.x, 8.x and 9.x applications. OpenGL, older versions of DirectX and software renderers are not supported.

aha, so now need to find out what renderer these games utilize
## Post #8
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-11-19T19:50:42+00:00
- Post Title: Doctor Who - The Adventure Games .Epc Files

it works almost on every game, but as i said, the mesh rotations are a bit off, UV mappings sometimes dont exist or are damaged, and the textures aren't named
you're still welcome to try, do tell of the results
