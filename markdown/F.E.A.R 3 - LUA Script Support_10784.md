## Post #1
- Username: liDante
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 17, 2013 9:12 pm
- Post datetime: 2013-09-17T22:34:21+00:00
- Post Title: F.E.A.R 3 - LUA Script Support

Hello Xentax community!

I've been looking into ways of making F.E.A.R 3 mod friendly, but I've encountered a few problems on my travels. One of the major ones being the script used within the .LUA files, I'm not sure if I'm allowed to screenshot it here, but I'll post a link - if it's in breach of the rules, I'll remove the link. The screenshot is available at the bottom of this paragraph.

If anyone has any information on what has happened to this LUA, or any way to make it readable would be absolutely amazing. As you can imagine, I'm not too well educated on LUA script, so, any help would be greatly appreciated!

> Game: F.E.A.R 3
>
> Engine: Despair Engine (Modified)
>
> Product Author(s): DAY 1 STUDIOS & Warner Brother Games

Thanks, 

Dante.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-18T00:12:57+00:00
- Post Title: F.E.A.R 3 - LUA Script Support

> Reply from liDante
>
> If anyone has any information on what has happened to this LUA, or any way to make it readableLooks like a compiled lua script. You need a decompiler for getting the lua script in ASCII format means as pure text. Google for LuaDec or Chunkspy.lua for example.
## Post #3
- Username: liDante
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 17, 2013 9:12 pm
- Post datetime: 2013-09-18T11:45:04+00:00
- Post Title: F.E.A.R 3 - LUA Script Support

> Reply from shakotay2
>
> liDante wrote:If anyone has any information on what has happened to this LUA, or any way to make it readableLooks like a compiled lua script. You need a decompiler for getting the lua script in ASCII format means as pure text. Google for LuaDec or Chunkspy.lua for example.

I did give LuaDec a try, but it just wouldn't do what it promised; I was kind of hoping there would be another one I didn't already know about that would hopefully help me with this. I'll try the Chunkspy one though; Thanks for the heads up! 

Edit - Tries Chunkspy but the same result, to no avail. I'd like to upload a copy of the script in conjunction with this thread, again - if it is in breach of the rules, I will remove it as soon as possible.

[http://tinyurl.com/olytd5r](http://tinyurl.com/olytd5r)

If you, or anyone viewing this thread could attempt to make this readable, and post their results that would be fantastic! Thanks!

Dante.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-18T15:46:08+00:00
- Post Title: F.E.A.R 3 - LUA Script Support

There's a compiled AdjustFOV.lua IN the AdjustFOV.lua file at 0x304.
Chunkspy.lua gives you this:

```
------------------------------------------------------------------------
0000                     ** source chunk: adjustfov_.lua
                         ** global header start **
0000  1B4C7561           header signature: "\27Lua"
0004  51                 version (major:minor hex digits)
0005  00                 format (0=official)
0006  01                 endianness (1=little endian)
0007  04                 size of int (bytes)
0008  04                 size of size_t (bytes)
0009  04                 size of Instruction (bytes)
000A  08                 size of number (bytes)
000B  00                 integral (1=integral)
                         * number type: double
                         * x86 standard (32-bit, little endian, doubles)
                         ** global header end **

```
and then bad constant type 97

Don't know why it's stopping. If you have a look at the hex data and compare it to a sample listing
you'll find source name= "/script/game/Camera/AdjustFOV.lua",
maxstack=16 (0x10) and size of code = 68 (0x44).
[](http://www.pic-upload.de/view-20761994/lua.jpg.html)

Just an example for comparison:

```
0010  4073616D706C652E+  "@sample."
0018  6C756100           "lua\0"
                         source name: @sample.lua
001C  00000000           line defined (0)
0020  00000000           last line defined (0)
0024  00                 nups (0)
0025  00                 numparams (0)
0026  02                 is_vararg (2)
0027  07                 maxstacksize (7)
                         * code:
0028  32000000           sizecode (50)
002C  01000000           [01] loadk      0   0        ; 1
0030  41800000           [02] loadk      1   2        ; "the quick brown fox\r\n"

```
## Post #5
- Username: liDante
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 17, 2013 9:12 pm
- Post datetime: 2013-09-19T11:18:14+00:00
- Post Title: F.E.A.R 3 - LUA Script Support

So with the information being stored within that file - does that mean that the code existing there can be modified and re-imported back into a usable state? If so, would I need to change any of the hex values which are in there to prevent differences, or would they automatically update/change when I make modifications?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-19T15:30:52+00:00
- Post Title: F.E.A.R 3 - LUA Script Support

> Reply from liDante
>
> So with the information being stored within that file - does that mean that the code existing there can be modified and re-imported back into a usable state?This would be the 3rd or 4th step.

If you are firm in some kind of "(dis) assembler thinking" you might succeed in changing the hex values. But it's hard.

So first step will be to decompile the script. luadec is decoding a sample.lua which is similar to the (extracted) AdjustFOV.lua. But luadec fails on the latter. 
(I'll do a debugging session on the luadec project trying to fix this issue.)
## Post #7
- Username: liDante
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 17, 2013 9:12 pm
- Post datetime: 2013-09-21T11:04:01+00:00
- Post Title: F.E.A.R 3 - LUA Script Support

> Reply from shakotay2
>
> liDante wrote:So with the information being stored within that file - does that mean that the code existing there can be modified and re-imported back into a usable state?This would be the 3rd or 4th step.

If you are firm in some kind of "(dis) assembler thinking" you might succeed in changing the hex values. But it's hard.

So first step will be to decompile the script. luadec is decoding a sample.lua which is similar to the (extracted) AdjustFOV.lua. But luadec fails on the latter. 
(I'll do a debugging session on the luadec project trying to fix this issue.)

Thank you for that! I appreciate it a lot, and no I'm not firm in any kind of coding other than web development unfortunately, which is a downside. I've not had access to Xentax for the past couple of days which is why I've not been able to respond. But thank you for the debugging, that would be awesome if you could!  

Thankyou!
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-27T21:05:37+00:00
- Post Title: F.E.A.R 3 - LUA Script Support

I don't know the reason atm but the LUA 5.1 parser does a faulty jump of 0x110 (= 0x44*4) bytes:
[](http://www.pic-upload.de/view-20849386/AdjustFOV-error.jpg.html)

I'm not familiar with LUA assembler so I've first have to learn it to modify the parser ([http://code.google.com/p/luadec](http://code.google.com/p/luadec)). But maybe I get some intuitive idea before... 

edit: I changed the value 0x44 (at address 0x003E) to 0x3D and as can be seen the parser at least recognizes the first strings in the strings table:

```
22 0 0 0 
2f 73 63 72 69 70 74 2f 67 61 6d 65 2f 43 61 6d 65 72 61 2f 41 64 6a 75 73 74 46 4f 56 2e 6c 75 61 0 
0 0 0 0 
0 0 0 0 
0 
0 
2 
10 
3d 0 0 0 
5 0 0 0 6 40 40 0 45 0 0 0 46 80 c0 0 85 0 0 0 86 c0 40 1 c5 0 0 0 c6 0 c1 1 5 1 0 0 6 41 41 2 45 1 0 0 46 41 c1 2 46 81 c1 2 86 c1 41 2 c5 1 0 0 c6 1 c2 3 c6 41 c2 3 5 2 0 0 6 2 42 4 6 82 42 4 45 2 0 0 46 2 c2 4 46 c2 c2 4 86 2 43 2 9c 82 80 0 c6 42 43 1 1 83 3 0 41 c3 3 0 dc 82 80 1 6 43 43 1 41 3 4 0 81 43 4 0 1c 83 80 1 43 3 80 6 a4 3 0 0 0 0 80 2 0 0 80 5 0 0 0 3 0 0 0 6 87 83 4 0 a4 43 0 0 0 0 0 5 87 c3 4 0 a4 83 87 3 5 0 a4 c3 43 5 0 a4 3 1 0 5 0 0 80 6 0 0 0 0 87 83 5 0 a4 43 1 0 80 2 0 0 0 0 0 0 80 3 0 0 80 1 0 0 0 4 0 0 80 4 87 c3 5 0 85 c3 5 0 c0 3 0 5 9c 43 0 1 1e 0 
80 0 18 0 
0 
0 
4 
b 0 0 0 
47 61 6d 65 53 63 72 69 70 74 0 // GameScript
4 
a 0 0 0 
43 61 6c 6c 62 61 63 6b 73 0 // Callbacks
4 
6 0 0 0 
44 65 62 75 67 0 // Debug
4 
8 0 0 0 
53 75 70 70 6f 72 55 74 
69 

```

But then 'bad constant in precompiled chunk' (the standard error message when the parser is upset  )

So maybe they just changed the "size of code" to hinder decompilation?
(String length at 0x163 should be 16 instead of 8 so I'm sure they did.)
