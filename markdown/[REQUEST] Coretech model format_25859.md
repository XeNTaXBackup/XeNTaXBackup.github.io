## Post #1
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2022-09-29T16:28:13+00:00
- Post Title: [REQUEST] Coretech model format

Hi guys,

I found these model format looking in King's Arthur 2 files. Each file is stored in C2AR archive  that could be extracted via quickbms with chrrox's script in this post [viewtopic.php?t=10351](https://forum.xentax.com/viewtopic.php?t=10351).

> Reply from chrrox ↑Sun Apr 21, 2013 11:15 pm at Sun Apr 21, 2013 11:15 pm
>
> 
Code: Select all#King Arthur 2 N2M quickbms script
#by chrrox
idstring "C2AR"
append
getdstring null 10
get TSIZE long
do
get ZSIZE long
savepos OFFSET
if TSIZE >= 0x800000
set SIZE 0x800000
else
set SIZE TSIZE
endif
clog MEMORY_FILE OFFSET ZSIZE SIZE
math TSIZE -= SIZE
math OFFSET + ZSIZE
goto OFFSET
while TSIZE != 0
append
get NAME basename
string NAME + ".ext"
get SIZE asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE

List of file ( all of them have a c2ar header and need to be unpacked via script) 

- .n2m archive containing model ? , output file header seems to have textures information : 
- .npt , seems to be a .dds file ( need to remove extra byte before dds header)
- .dds , textures ( remove extra bytes before dds header)

Is there any tool that could handle the model format?  I would like to get skinned models if possible.

Here some sample , wish someone could take a look : [https://www.mediafire.com/file/bf2yqftf ... e.rar/file](https://www.mediafire.com/file/bf2yqftf9t7hxg0/sample.rar/file)

Thanks in advance,

Drawing
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-09-29T20:30:04+00:00
- Post Title: [REQUEST] Coretech model format

> Reply from Drawing ↑Fri Sep 30, 2022 12:28 am at Fri Sep 30, 2022 12:28 am
>
> 
Here some sample
Infested_legion.ext: (1 submesh)

```
vert num = 5218
stride 72:
	-vert (float) ofs = 0
	-normal (float) ofs = 28
	-uvs (float) ofs = 40

ibuf ofs = 376572 (prim type = triangels)
indices num = 26304 (ushort)

```




Infested_legion.ext.png (28.46 KiB) Viewed 84 times


i made plugin:
## Post #3
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2022-09-30T10:41:15+00:00
- Post Title: [REQUEST] Coretech model format

Great!
