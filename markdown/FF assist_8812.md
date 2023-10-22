## Post #1
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-04-22T13:03:34+00:00
- Post Title: FF assist

i'm having a bit of a problem with Noel's texture in xiii-2... his textures won't align properly:



here are my files (i have the trb files included):

[http://www.mediafire.com/?7krvhkb77k9hkms](http://www.mediafire.com/?7krvhkb77k9hkms)

 thnx
## Post #2
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-04-22T19:52:23+00:00
- Post Title: FF assist

i tried re-extracting the char files but same. its his clothes they won't align properly.
## Post #3
- Username: drivethru92
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Apr 23, 2012 3:58 am
- Post datetime: 2012-04-22T20:06:30+00:00
- Post Title: FF assist

> Reply from inspiredgurl
>
> i tried re-extracting the char files but same. its his clothes they won't align properly.

i'm having trouble with some of the textures too. i thought it was just me lol
hopefully you get help, and we both will know
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2012-04-23T16:09:52+00:00
- Post Title: FF assist

> Reply from drivethru92
>
> inspiredgurl wrote:i tried re-extracting the char files but same. its his clothes they won't align properly. 

i'm having trouble with some of the textures too. i thought it was just me lol
hopefully you get help, and we both will know

Have you checked the UV's of the model? Also check to make sure all normals are facing the same direction (otherwise you get those dark areas in your above image).
## Post #5
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-04-23T20:32:41+00:00
- Post Title: FF assist

> Reply from lionheartuk
>
> drivethru92 wrote:inspiredgurl wrote:i tried re-extracting the char files but same. its his clothes they won't align properly. 

i'm having trouble with some of the textures too. i thought it was just me lol
hopefully you get help, and we both will know  

Have you checked the UV's of the model? Also check to make sure all normals are facing the same direction (otherwise you get those dark areas in your above image).

thnx for reply. i checked the normals (modifier) and i try unwrap uvw, nothing. 

so i looked again and i noticed in material editor the textures are named different than the textures i extracted from noesis. hmm...noel's textures were in a 7kb .trb file separate from his model file. noel's model looked weird too in noesis, it was all white with brown patched on his skin... 

> Code: Select allget NAME BASENAME
>
> log MEMORY_FILE 0 0
>
> put NAME string MEMORY_FILE
>
> get size asize MEMORY_FILE
>
> math size - 4
>
> goto size MEMORY_FILE
>
> getdstring EXT2 4 MEMORY_FILE
>
> if EXT2 == "360"
>
> set EXT "x360"
>
> else
>
> set EXT ps3
>
> endif
>
> 
>
> comtype unzip_dynamic
>
> for
>
> findloc START string \x78\xDA
>
> goto START
>
> findloc END string \x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00
>
> set SIZE end
>
> math SIZE - START
>
> goto END
>
> if SIZE > 0x40
>
> clog MEMORY_FILE START SIZE SIZE
>
> getdstring SEDB 8 MEMORY_FILE
>
> if SEDB == "SEDBRES "
>
> goto 0x30 MEMORY_FILE
>
> get COUNT long MEMORY_FILE
>
> math COUNT * 16
>
> math COUNT + 0x40
>
> goto COUNT MEMORY_FILE
>
> getdstring TRB 7 MEMORY_FILE
>
> if TRB == "SEDBtxb"
>
> string START + .
>
> string START + EXT
>
> get SIZE asize MEMORY_FILE
>
> set NAME START
>
> string NAME + .trb
>
> log NAME 0 SIZE MEMORY_FILE
>
> set NAME START
>
> string NAME + .imgb
>
> clog NAME OFFSET ZSIZE2 SIZE2
>
> endif
>
> endif
>
> if SEDB != "SEDBRES "
>
> set OFFSET START
>
> set ZSIZE2 SIZE
>
> get SIZE2 asize MEMORY_FILE
>
> endif
>
> endif
>
> next

could it be the script i use thats causing the texture problem for noel?
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-23T20:40:53+00:00
- Post Title: FF assist

More likely the import script rather than the unpacking script.
## Post #7
- Username: drivethru92
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Apr 23, 2012 3:58 am
- Post datetime: 2012-04-23T21:07:47+00:00
- Post Title: FF assist

> so i looked again and i noticed in material editor the textures are named different than the textures i extracted from noesis. hmm...noel's textures were in a 7kb .trb file separate from his model file. noel's model looked weird too in noesis, it was all white with brown patched on his skin...
ahh i found what you mentioned



and the 7kb texture file



i'm trying to texture chocolina, but having the same problem. textures with different name than material



her textures
## Post #8
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-04-23T23:24:26+00:00
- Post Title: FF assist

@finale: hmm but Snow imported just fine with his textures mapped in 3dsmax material editor... 

@drivethru: thats the noel i have...
## Post #9
- Username: drivethru92
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Apr 23, 2012 3:58 am
- Post datetime: 2012-04-24T20:17:54+00:00
- Post Title: FF assist

> Reply from inspiredgurl
>
> @finale: hmm but Snow imported just fine with his textures mapped in 3dsmax material editor... 

@drivethru: thats the noel i have...

have you had any luck yet? i thought i made a break through last night but i was wrong.
i may try another modeling program.
## Post #10
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-04-25T20:32:07+00:00
- Post Title: FF assist

I was reading around and someone was having the same problem as I was. i posted the forum link.

[viewtopic.php?f=16&t=7862&start=30](http://forum.xentax.com/viewtopic.php?f=16&t=7862&start=30)

so he used the original script to get it to work for him. i pasted it below:

```
log MEMORY_FILE 0 0
put NAME string MEMORY_FILE
get size asize MEMORY_FILE
math size - 4
goto size MEMORY_FILE
getdstring EXT2 4 MEMORY_FILE
if EXT2 == "360"
set EXT "x360"
else
set EXT ps3
endif

comtype unzip_dynamic
for
findloc START string \x78\xDA
goto START
findloc END string 

\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00
set SIZE end
math SIZE - START
goto END
if SIZE > 0x40
clog MEMORY_FILE START SIZE SIZE
getdstring SEDB 8 MEMORY_FILE
if SEDB == "SEDBRES "
goto 0x30 MEMORY_FILE
get COUNT long MEMORY_FILE
math COUNT * 16
math COUNT + 0x40
goto COUNT MEMORY_FILE
getdstring TRB 7 MEMORY_FILE
if TRB == "SEDBtxb"
string START + .
string START + EXT
get SIZE asize MEMORY_FILE
set NAME START
string NAME + .trb
log NAME 0 SIZE MEMORY_FILE
set NAME START
string NAME + .imgb
clog NAME OFFSET ZSIZE2 SIZE2
endif
endif
if SEDB != "SEDBRES "
set OFFSET START
set ZSIZE2 SIZE
get SIZE2 asize MEMORY_FILE
endif
endif
next

```


I use the same script he used (above) and i get this error message...
## Post #11
- Username: drivethru92
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Apr 23, 2012 3:58 am
- Post datetime: 2012-05-01T02:00:27+00:00
- Post Title: FF assist

i'm try different 3d software and i can't get the model to line right.
maybe someone who is good in 3ds max can help you...here?
excuse me, but i notice you files have no such many download
i wonder what is problem?
## Post #12
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-05-30T21:32:57+00:00
- Post Title: FF assist

ye its weird... hopefully some can help us, lol.
