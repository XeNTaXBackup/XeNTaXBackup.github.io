## Post #1
- Username: ForgedInception
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 19, 2018 12:39 am
- Post datetime: 2018-03-20T18:19:14+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

Hi , i am trying to open Gangster Vegas .bdae files but getting this error.
Can anyone help? I searched for OLYA script but i am unable to find. 



```
offset           filesize   filename
--------------------------------------

- signature of 7 bytes at offset 0x0000000000000000 doesn't match the one
  expected by the script:

  this one: "OLY"
  4f 4c 59 41 18 08 00                              OLYA...

  expected: "Voxarch"
  56 6f 78 61 72 63 68                              Voxarch

- 0 files found in 0 seconds
  coverage file 0     0%   7          22398018   . offset 0000000000000007

Press ENTER or close the window to quit


```


Sample Files :-

 https://mega.nz/#F!9ep10RDa!DJ-MxX41nLxlj_B7Pvcofg
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-21T01:54:17+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

Honestly I am really tired of asking you guys to upload sample files over and over again.
## Post #3
- Username: ForgedInception
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 19, 2018 12:39 am
- Post datetime: 2018-03-21T08:49:46+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

> Reply from Bigchillghost
>
> Honestly I am really tired of asking you guys to upload sample files over and over again.

Sorri , Link to sample files.

[https://mega.nz/#F!9ep10RDa!DJ-MxX41nLxlj_B7Pvcofg](https://mega.nz/#F!9ep10RDa!DJ-MxX41nLxlj_B7Pvcofg)
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-03-21T12:04:22+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

> Reply from ForgedInception
>
> 
Sorri , Link to sample files.

https://mega.nz/#F!9ep10RDa!DJ-MxX41nLxlj_B7Pvcofg
Archives are zstd compressed. Here is a BMS script for proper decompression. You'll need to update your QuickBMS to the lastest version. Still there're some files that cannot be decompressed correctly due to QuickBMS's incomplete support for zstd.


 Gangstar Vegas 4 BDAE Decompressor.rar
(405 Bytes) Downloaded 87 times
## Post #5
- Username: ForgedInception
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 19, 2018 12:39 am
- Post datetime: 2018-03-21T13:06:11+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

> Reply from Bigchillghost
>
> ForgedInception wrote:
Sorri , Link to sample files.

https://mega.nz/#F!9ep10RDa!DJ-MxX41nLxlj_B7Pvcofg
Archives are zstd compressed. Here is a BMS script for proper decompression. You'll need to update your QuickBMS to the lastest version. Still there're some files that cannot be decompressed correctly due to QuickBMS's incomplete support for zstd.
Gangstar Vegas 4 BDAE Decompressor.rar

How to convert .bdae to .fbx , .obj or .dae ??
Any Support for animations export ?
## Post #6
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2018-06-08T11:58:14+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

I've been looking into this aswell, not for this game but for another gameloft game called Dungeon Hunter Champions. Also .bdae file format
To convert it to 3D Models.

Not a lot atm. only the names of the objects in the file.

So it has a 32 byte header, than the next one is the offset where the names start, which is a Int64
Than there is a long list of Int64, I thought they were all offsets, but some are bigger than the filesize.... so not quite sure what that is.

Names:
They start with a int, which is the length of the name, but the names length are always a multiplier of 4, weird, but hey thats how they do it

I just downloaded the Dungeon Hunter game for Windows 10, its free, so you can get the file easy.

Thats how far I got atm
T.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-08T15:13:39+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

> Reply from ForgedInception
>
> How to convert .bdae to .fbx , .obj or .dae ??
obj is easy:



bikerfemale-bdae.jpg (179.04 KiB) Viewed 299 times



> Any Support for animations export ?
As always you'll need the skeleton first.
## Post #8
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2018-06-09T09:08:38+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

Hey, is there any logic to finding the offsets for the vertices and faces, or just gut feeling by try and error with the hex editor?

T.
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-09T09:36:37+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

> Reply from TaylorMouse
>
> Hey, is there any logic to finding the offsets for the vertices and faces, or just gut feeling by try and error with the hex editor?
You'll have to reverse the file structure at least to obtain the offsets and counts if you're planning to write a convertor. But if you want only one to two meshes in the file, why bother to waste any time on that?
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-09T09:55:00+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

> Reply from Bigchillghost
>
> TaylorMouse wrote:Hey, is there any logic to finding the offsets for the vertices and faces, or just gut feeling by try and error with the hex editor?
You'll have to reverse the file structure at least to obtain the offsets and counts if you're planning to write a convertorI think, T. is aware of that.  But sometimes it's as simple as having some offsets at the beginning of the file, for example.

But I'm sorry, T., all I can see at a quick glance is the filesize at offset 0x000C.

(Maybe there's some pattern nearby the counts? 00 01000000 being a candidate; maybe check this for other bdaes.)



bdae-counts.jpg (244.67 KiB) Viewed 283 times



well, here's the assumed patterns to search for:
a) 14 000000 00000000 00000000 00000000 00000000
DWORD FI count before the found address (first finding)

b) 00 01000000 xx xx 0000 05
where xx is the pattern for a wildcard search. (If your hexeditor doesn't support this you'll need to split up the search pattern,
search for 00 01000000, and then look at an offset of 7 to the found address for 00 00 05)

xx xx will contain the low word of the vertex DWORD count.

(For char_cutscene_benny.bdae you'll have to repeat search b) until xx xx are != 0.)

Tested with 3 bdaes only! b) needs another xx for vertex counts >65535 dec.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-09T10:39:56+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

> Reply from shakotay2
>
> Maybe there's some pattern nearby the counts?



location.jpg (248.25 KiB) Viewed 282 times


The only thing left is to find the offset of the vert count now.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-09T10:42:45+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

yeah, see, you were 1 minute quicker
## Post #13
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2018-06-09T11:47:34+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

mm... the format is not quite the same for the looks of it...
maybe I should start another topic for Dungeon Hunter Champions bdae files.
## Post #14
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2018-06-09T11:52:42+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

this is the file opened in my hex viewer, at pos 32 there the offsets start



bdae-resaerch-001.PNG (43.88 KiB) Viewed 277 times



and the first int64 points to the list of object names
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-09T15:55:17+00:00
- Post Title: Gangster Vegas 4 - Gameloft - .bdae files

did you check here:
[http://wiki.tockdom.com/wiki/BRRES_(File_Format)](http://wiki.tockdom.com/wiki/BRRES_%28File_Format%29)

or here:
[viewtopic.php?f=21&t=13899&p=115515&hilit=bres#p115515](http://forum.xentax.com/viewtopic.php?f=21&t=13899&p=115515&hilit=bres#p115515)
(posts from lolbas and AceWell)
## Post #16
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2018-06-16T10:18:37+00:00
- Post Title: Re: Gangster Vegas 4 - Gameloft - .bdae files

Oh, no I haven't yet, but doing so now 

The first looks an empty site... 

The second one is more of the same of what I already had ...

Thnx tho

T.
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-16T10:35:10+00:00
- Post Title: Re: Gangster Vegas 4 - Gameloft - .bdae files

> Reply from TaylorMouse
>
> 
The first looks an empty site...
That's because the right parentheses is missed in the link.
Check this:
[http://wiki.tockdom.com/wiki/BRRES_(File_Format)](http://wiki.tockdom.com/wiki/BRRES_%28File_Format%29)
## Post #18
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2018-06-16T12:47:19+00:00
- Post Title: Re: Gangster Vegas 4 - Gameloft - .bdae files

Yeah, ok, that seems to work for the vehicle, but not for a newer format...

T.
## Post #19
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2018-06-18T11:55:12+00:00
- Post Title: Re: Gangster Vegas 4 - Gameloft - .bdae files

> Reply from TaylorMouse
>
> mm... the format is not quite the same for the looks of it...
maybe I should start another topic for Dungeon Hunter Champions bdae files.
If you really gonna start this topic, I'm up to collaborate with you doing RE of the format. BDAE format has different versions that only contain required logic (unsure about this) but versions differ from each other by different size of offset values, sometimes different order of blocks. I've done some good work on working over BDAE v0.0.0.946 (Order & Chaos 2) and while I haven't yet come to meshes faces/vertices/other details, I found sections that relate to audio, material and its properties, packages, nodes, node transaltions, textures - just sections, without "this data means this" since I lack knowledge of what does 3D model actually contains. This things could be mapped to DHC bdae. Should be easier than starting from scratch
