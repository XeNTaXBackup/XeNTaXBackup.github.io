## Post #1
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T05:15:18+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

A file compression inside the models and maps, this suffix called I want to know how to extract models and textures, this file is large, I can not upload
[55.jpg](https://xentaxbackup.github.io/file/5149_55.jpg)
## Post #2
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-06T05:23:20+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from zhanzhongyi
>
>  A file compression inside the models and maps, this suffix called I want to know how to extract models and textures, this file is large, I can not upload
[viewtopic.php?p=51186#p51186](http://forum.xentax.com/viewtopic.php?p=51186#p51186)
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-06T07:39:31+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

Don't forget there are also G1TG0050 files as well. Models are forthcoming... they added a bunch of new vertex formats though.
## Post #4
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T08:40:20+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> zhanzhongyi wrote: A file compression inside the models and maps, this suffix called I want to know how to extract models and textures, this file is large, I can not upload
Here's a quickbms script
G1M extracter
Code: Select allendian big
for i
findloc start string "G1M_0034"
goto start
print "%start%"
savepos offset
getdstring null 0x8
get size long
set name i
string name + ".g1m"
log name offset size

next i
G1T extracter
Code: Select allendian big
for i
findloc start string "G1TG0060"
goto start
print "%start%"
savepos offset
getdstring null 0x8
get size long
set name i
string name + ".g1t"
log name offset size

next i
I have altered chrrox's Dynasty Warriors 7 quickbms script.
viewtopic.php?p=51186#p51186
 I am very grateful to you for me to solve the problem of compressed, but I want to know how to extract the OBJ and texture from G1T file
## Post #5
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-06T08:59:40+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from zhanzhongyi
>
> 
 I am very grateful to you for me to solve the problem of compressed, but I want to know how to extract the OBJ and texture from G1T file
I don't have a clue how to do it, to be perfectly honest.
## Post #6
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T09:09:49+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> zhanzhongyi wrote:
 I am very grateful to you for me to solve the problem of compressed, but I want to know how to extract the OBJ and texture from G1T file
I don't have a clue how to do it, to be perfectly honest.
 Oh, it is really a pity that
## Post #7
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-06T09:20:43+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

[viewtopic.php?p=51186#p51186](http://forum.xentax.com/viewtopic.php?p=51186#p51186)
Compare this with Dynasty Warriors 7.
They're about the same in format.
## Post #8
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T09:30:30+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> viewtopic.php?p=51186#p51186
Compare this with Dynasty Warriors 7.
They're about the same in format.
 Their conversation, I totally can not read, do not know how to do
## Post #9
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-06T10:23:17+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

```
.......0..Ђp..Ђ ..Ђp......Ђp..ЃЂ..Ђp.*.р..Ђp....
```

add this section to G1M_0034, at the front
exports with Noesis tool.

test shot
## Post #10
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-03-06T10:45:27+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

Awesome
all-purpose code?
## Post #11
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T10:47:31+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> Code: Select all.......0..Ђp..Ђ ..Ђp......Ђp..ЃЂ..Ђp.*.р..Ђp....
add this section to G1M_0034, at the front
exports with Noesis tool.

test shot
Exported should be named files, can not read Noesis
## Post #12
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-06T10:52:00+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from zhanzhongyi
>
> Exported should be named files, can not read Noesis
only exports.
## Post #13
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T11:02:03+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> zhanzhongyi wrote:Exported should be named files, can not read Noesis
only exports.
So how, some characters can not copy the error
[55.jpg](https://xentaxbackup.github.io/file/5152_55.jpg)
## Post #14
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-06T11:14:21+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from zhanzhongyi
>
> So how, some characters can not copy the error
Look at this picture. 
show clear distinction
## Post #15
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T11:34:53+00:00
- Post Title: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> zhanzhongyi wrote:So how, some characters can not copy the error
Look at this picture. 
show clear distinction

Here is a front code
The attachment front code.7z is no longer available
Save the file, I use the Noesis still can not read the file
[55.jpg](https://xentaxbackup.github.io/file/5154_55.jpg)
## Post #16
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-06T11:38:57+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from zhanzhongyi
>
> 
Save the file, I use the Noesis still can not read the file
upload a changing file.
## Post #17
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T11:45:15+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> zhanzhongyi wrote:
Save the file, I use the Noesis still can not read the file
upload a changing file.
This is after I add the code files
[lf.zip](https://xentaxbackup.github.io/file/5155_lf.zip)
## Post #18
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-06T11:50:30+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

Export, there's no problem with that.

Please update your Noesis with this latest version
[http://oasis.xentax.com/files/noesisv383.zip](http://oasis.xentax.com/files/noesisv383.zip)
## Post #19
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T12:04:20+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> Export, there's no problem with that.
The attachment out.7z is no longer available
Please update your Noesis with this latest version
http://oasis.xentax.com/files/noesisv383.zip
With latest Noesisv can not view the file
[55.jpg](https://xentaxbackup.github.io/file/5157_55.jpg)
## Post #20
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-06T12:09:30+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

Let's try this
## Post #21
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T12:15:30+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> Let's try this
Still not work, there is no file in the list display
## Post #22
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-06T12:18:59+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

Now I think I get the picture.
## Post #23
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T12:21:52+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> Now I think I get the picture.
 Thank you, help me to solve the problem of the model, but the maps need to how to export
## Post #24
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-06T12:32:53+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from zhanzhongyi
>
> 
 Thank you, help me to solve the problem of the model, but the maps need to how to export
Here is a chrrox's G1T2DDS quickbms script.
Chrrox's G1T2DDS quickbms script requires slight modification.
But, i don't know the details.

```
idstring G1TG0060
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\x80\x00\x00\x00\x80\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"


get dataSize long
get dataOffset long
get texCount long
get ukn1 long
get ukn2 long
for i = 0 < texCount
get ukn3 long
next i
goto dataOffset
savepos OFFTABLE

set NUM 1
for i = 0 < texCount
endian BIG
math NUM + 1
get NAME BASENAME
string NAME + "_"
string NAME += NUM
string NAME + ".dds"
goto OFFTABLE

print %OFFTABLE%
set JUMP 0
get JUMP long
print %JUMP%

savepos OFFTABLE
math JUMP + dataOffset
goto JUMP
get ukn4 byte
get texC byte
get texD byte
get NULL byte
get NULL long
get NULL long
get NULL long
get NULL long
set set1 texD
set set2 texD
savepos OFFSET
endian LITTLE
math set1 & 0xF0
math set1 / 16
math set2 & 0x0F
set texH 2
set texW 2
Math texW p set1
Math texH p set2
putVarChr MEMORY_FILE 0x0C texH short
putVarChr MEMORY_FILE 0x10 texW short
if texC == 0x01
print "{0x01} ARGB32 Found!"
set bbp 32
math MAGIC = texW
math MAGIC * texH
math MAGIC / 0x4
math MAGIC * 0x10
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x41 long
putVarChr MEMORY_FILE 0x54 0x00 byte
putVarChr MEMORY_FILE 0x55 0x00 byte
putVarChr MEMORY_FILE 0x56 0x00 byte
putVarChr MEMORY_FILE 0x57 0x00 byte
putVarChr MEMORY_FILE 0x58 0x20 long
putVarChr MEMORY_FILE 0x5E 0xFF Short
putVarChr MEMORY_FILE 0x61 0xFF Short
putVarChr MEMORY_FILE 0x64 0xFF Short
putVarChr MEMORY_FILE 0x6B 0xFF Short
endif
if texC == 0x06
print "{0x06} DXT1 Found!"
set bbp 4
math MAGIC = texW
math MAGIC * texH
math MAGIC / 0x2
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x41 long
putVarChr MEMORY_FILE 0x54 0x44 byte
putVarChr MEMORY_FILE 0x55 0x58 byte
putVarChr MEMORY_FILE 0x56 0x54 byte
putVarChr MEMORY_FILE 0x57 0x31 byte
putVarChr MEMORY_FILE 0x58 0x00 long
putVarChr MEMORY_FILE 0x5E 0x00 Short
putVarChr MEMORY_FILE 0x61 0x00 Short
putVarChr MEMORY_FILE 0x64 0x00 Short
putVarChr MEMORY_FILE 0x6B 0x00 Short
endif
if texC == 0x08
print "{0x08} DXT5 Found!"
set bbp 8
math MAGIC = texW
math MAGIC * texH
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x04 long
putVarChr MEMORY_FILE 0x54 0x44 byte
putVarChr MEMORY_FILE 0x55 0x58 byte
putVarChr MEMORY_FILE 0x56 0x54 byte
putVarChr MEMORY_FILE 0x57 0x35 byte
putVarChr MEMORY_FILE 0x58 0x00 long
putVarChr MEMORY_FILE 0x5E 0x00 Short
putVarChr MEMORY_FILE 0x61 0x00 Short
putVarChr MEMORY_FILE 0x64 0x00 Short
putVarChr MEMORY_FILE 0x6B 0x00 Short
endif
set SIZE texH
math SIZE * texW
math bbp / 8
math SIZE * bbp
log NAME 0 0x80 MEMORY_FILE
append
log NAME OFFSET SIZE
append
next i

```
## Post #25
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T12:41:06+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> zhanzhongyi wrote:
 Thank you, help me to solve the problem of the model, but the maps need to how to export
Here is a chrrox's G1T2DDS quickbms script.
Chrrox's G1T2DDS quickbms script requires slight modification.
But, i don't know the details.
Code: Select allendian BIG
idstring G1TG0060
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\x80\x00\x00\x00\x80\x00\x00\x00\x00\x20\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"


get dataSize long
get dataOffset long
get texCount long
get ukn1 long
get ukn2 long
for i = 0 < texCount
get ukn3 long
next i
goto dataOffset
savepos OFFTABLE

set NUM 1
for i = 0 < texCount
endian BIG
math NUM + 1
get NAME BASENAME
string NAME + "_"
string NAME += NUM
string NAME + ".dds"
goto OFFTABLE

print %OFFTABLE%
set JUMP 0
get JUMP long
print %JUMP%

savepos OFFTABLE
math JUMP + dataOffset
goto JUMP
get ukn4 byte
get texC byte
get texD byte
get NULL byte
get NULL long
get NULL long
get NULL long
get NULL long
set set1 texD
set set2 texD
savepos OFFSET
endian LITTLE
math set1 & 0xF0
math set1 / 16
math set2 & 0x0F
set texH 2
set texW 2
Math texW p set1
Math texH p set2
putVarChr MEMORY_FILE 0x0C texH short
putVarChr MEMORY_FILE 0x10 texW short
if texC == 0x01
print "{0x01} ARGB32 Found!"
set bbp 32
math MAGIC = texW
math MAGIC * texH
math MAGIC / 0x4
math MAGIC * 0x10
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x41 long
putVarChr MEMORY_FILE 0x54 0x00 byte
putVarChr MEMORY_FILE 0x55 0x00 byte
putVarChr MEMORY_FILE 0x56 0x00 byte
putVarChr MEMORY_FILE 0x57 0x00 byte
putVarChr MEMORY_FILE 0x58 0x20 long
putVarChr MEMORY_FILE 0x5E 0xFF Short
putVarChr MEMORY_FILE 0x61 0xFF Short
putVarChr MEMORY_FILE 0x64 0xFF Short
putVarChr MEMORY_FILE 0x6B 0xFF Short
endif
if texC == 0x06
print "{0x06} DXT1 Found!"
set bbp 4
math MAGIC = texW
math MAGIC * texH
math MAGIC / 0x2
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x41 long
putVarChr MEMORY_FILE 0x54 0x44 byte
putVarChr MEMORY_FILE 0x55 0x58 byte
putVarChr MEMORY_FILE 0x56 0x54 byte
putVarChr MEMORY_FILE 0x57 0x31 byte
putVarChr MEMORY_FILE 0x58 0x00 long
putVarChr MEMORY_FILE 0x5E 0x00 Short
putVarChr MEMORY_FILE 0x61 0x00 Short
putVarChr MEMORY_FILE 0x64 0x00 Short
putVarChr MEMORY_FILE 0x6B 0x00 Short
endif
if texC == 0x08
print "{0x08} DXT5 Found!"
set bbp 8
math MAGIC = texW
math MAGIC * texH
putVarChr MEMORY_FILE 0x14 MAGIC long
putVarChr MEMORY_FILE 0x50 0x04 long
putVarChr MEMORY_FILE 0x54 0x44 byte
putVarChr MEMORY_FILE 0x55 0x58 byte
putVarChr MEMORY_FILE 0x56 0x54 byte
putVarChr MEMORY_FILE 0x57 0x35 byte
putVarChr MEMORY_FILE 0x58 0x00 long
putVarChr MEMORY_FILE 0x5E 0x00 Short
putVarChr MEMORY_FILE 0x61 0x00 Short
putVarChr MEMORY_FILE 0x64 0x00 Short
putVarChr MEMORY_FILE 0x6B 0x00 Short
endif
set SIZE texH
math SIZE * texW
math bbp / 8
math SIZE * bbp
log NAME 0 0x80 MEMORY_FILE
append
log NAME OFFSET SIZE
append
next i
 I can view a map, try to use this tool only open G1T file debug
[TextureFinder.v21.zip](https://xentaxbackup.github.io/file/5158_TextureFinder.v21.zip)
## Post #26
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T12:42:27+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

This is the view out of the map
[55.jpg](https://xentaxbackup.github.io/file/5159_55.jpg)
## Post #27
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-06T13:07:28+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from zhanzhongyi
>
>  This is the view out of the map
I know, but that is an imperfect.
## Post #28
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-06T13:11:01+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> zhanzhongyi wrote: This is the view out of the map
I know, but that is an imperfect.
 Well, but now only the case
## Post #29
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-07T02:41:11+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

Some DDS files converting success
## Post #30
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-07T10:56:57+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> Some DDS files converting success

f_1_DXT5.7z
Why do I import the model into UV coordinates 3DMAX and Maya  In this case I will not be able to map this DDS extracted
## Post #31
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-07T14:29:54+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

I have no idea about that.
## Post #32
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-07T15:25:33+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from dj082502
>
> I have no idea about that.
Only the model into 3DMAX UV coordinates
## Post #33
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-07T15:44:12+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

Do you mean, you want to import the model, or do you mean the model is not imported correctly and the UV coords are wrong?
## Post #34
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-07T16:00:10+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from finale00
>
> Do you mean, you want to import the model, or do you mean the model is not imported correctly and the UV coords are wrong?
yes
## Post #35
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-07T16:27:12+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

Which one.
## Post #36
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-07T17:21:21+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from finale00
>
> Which one.
All
## Post #37
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-07T21:03:56+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

What's the existing import script?
## Post #38
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-03-07T21:24:03+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

Use the DW7 script finale00. The previous script for DW7 doesn't always work because they added a few more vertex formats. There is also a new texture format (id = 9). I am currently modifying my DWG3 ripper to support this game but there are lots of changes. But if anyone can add the vertex formats (of size 0x28 through 0x38) to chrrox's script in the meantime... knock yourselves out.
## Post #39
- Username: zhanzhongyi
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 16, 2011 1:37 pm
- Post datetime: 2012-03-08T02:48:30+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

> Reply from finale00
>
> What's the existing import script?
What does it mean?
## Post #40
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2012-04-17T23:07:42+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

Hey, I have a question, is this file only with textures/models? I believe there should be audio inside of it, not sure what format though, my reasons are because there's only .pam (at3 audio / video file) (which contained the movies and their own short streamed audio)  - the BGM (.at3 + some kind of .atsl3 format) neither of these contain the sound effects, and there are 3 large files as stated in this topic in folder LINKDATA_PS3 - ( LINKDATA.A  - LINKDATA.B  - LINKDATA.C ) this is rather offtopic, sorry about that.
## Post #41
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-17T23:50:33+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

I don't have the files in front of me right now but there are a bunch of wave files in the link data files. I typically skip over them since I am not interested in the audio usually. My ripper rips the audio as well but I haven't finished the models. I don't know what codec they use, but it's something not native to windows.
## Post #42
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2012-04-18T02:25:05+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

Well, I was able to extract from "LINKDATA.A" 13 thousand .WAV audio files using audiorip, but all of them were vocals, none were actual sound effects, I tried on the other two " LINKDATA.B / .C" this time there was no .WAVs... , it did detect .mp1 files, but they were broken, some were 1-2 mbs above, still had a hiss sound without actual data, perhaps the audio effects ARE .mp1 /mpeg format, but I'm not sure how to extract them properly and if they aren't, they MUST be in the other two archives .B/.C
## Post #43
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-18T02:33:01+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

Then what I would do is if the effects are stored in a different chunk, is use ur audio finder to find the offset of one of those mpeg sections. Then look up and find the chunktype. You can also find nearest offset in the offset table at the top. Save the whole chunk and pass it to one of the guys in the audio section. It's going to get overlooked here in the graphics section. It will be another week before I have access to the files again so I can't check.
## Post #44
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-04-20T15:08:04+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

FinalBlast, do you have a link to that audio rip application? Google returns too many results for audio rip (if it's not free just provide a link to the developer's page). I have the files in front of me now and want to test that app on all the WBD files listed in LINKDATA.A. B and C contain models and textures and effects and other junk. I have a feeling audio rip is not ripping all the data in the WBD files. There are only a few hundred WBH/WBD file pairs, but each WBD file contains multiple audio samples.
## Post #45
- Username: yiwang
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Apr 28, 2012 9:30 am
- Post datetime: 2012-04-28T02:22:54+00:00
- Post Title: Re: 【PS3】One Piece Warriors Suffix the file named A,

UV displays an error
