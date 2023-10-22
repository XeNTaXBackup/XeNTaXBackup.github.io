## Post #1
- Username: Resiliaxia
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-12T22:20:50+00:00
- Post Title: (X360) Naruto the broken bond.

Here is a script to extract but not decompress the files in the bf file.
The textures in the other files are plain dds files.

```
get files long
get unk01 long
get unk02 long
for i = 0 < files
get unk03 long
get offset long
get unk04 long
get size long
math size + 4
get unk05 long
get unk06 long
get unk07 long
get unk08 long
getdstring name 0x40
getdstring null 0x29
log name offset size
next i
```


And here is the .bin extractor for the files the first script outputs.

```
#quickbms script
#By chrrox
get name FILENAME
string name + ".dec"
get TotalUncompSize long
comtype LZO1X
Do
get size long
get zsize long
savepos offset
append
clog MEMORY_FILE offset zsize size
append
math offset + zsize
goto offset
While OFFSET < TotalUncompSize
get tsize asize MEMORY_FILE
log NAME 0 tsize MEMORY_FILE
```

[sasuke2.png](https://xentaxbackup.github.io/file/4483_sasuke2.png)
## Post #2
- Username: PiqMonKey
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 26, 2010 5:05 pm
- Post datetime: 2011-07-14T23:02:55+00:00
- Post Title: (X360) Naruto the broken bond.

Thank you for these scripts.

But I am missing something, once I get the .dec file what is the next step to get the model in 3D software?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-14T23:13:24+00:00
- Post Title: (X360) Naruto the broken bond.

someone needs to make a model converter i just manually converted sasuke to show it was possible now.
## Post #4
- Username: Siegfre
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 25, 2012 10:58 am
- Post datetime: 2014-09-12T08:28:39+00:00
- Post Title: (X360) Naruto the broken bond.

> Reply from chrrox
>
> someone needs to make a model converter i just manually converted sasuke to show it was possible now.
Could you please post the format specifications you used?

I tried using this one here, but the Naruto bin format seemed to be a bit different: [viewtopic.php?p=43246#p43246](http://forum.xentax.com/viewtopic.php?p=43246#p43246)
## Post #5
- Username: Detexki99
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 30, 2016 11:08 pm
- Post datetime: 2020-05-29T12:15:17+00:00
- Post Title: (X360) Naruto the broken bond.

I was thinking if this program "3d Object Converter" does not work for me :/ 
You said where the .bin.dec file went from?
