## Post #1
- Username: truston
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 15, 2014 5:42 pm
- Post datetime: 2015-12-19T08:31:54+00:00
- Post Title: !! Dirge of Cerberus FF7 (ver: us or int) (can NOT extract)

Hola everyone!   

I'm a FF fan. I wanna extract all FMV from Dirge of Cerberus FF7. I have original discs of US, JP, International versions. 
There's a fmv extractor for JP version ONLY (it works). 
But I need US or Int version FMV extractor. 
(If there's already a way to do this, pls give me the link.)

Thx everyone!!   
------------------------------------------
DCFF7 JP fmv extractor is attached here
[dcff7tomov_1.04.zip](https://xentaxbackup.github.io/file/10165_dcff7tomov_1.04.zip)
## Post #2
- Username: truston
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 15, 2014 5:42 pm
- Post datetime: 2015-12-19T11:50:22+00:00
- Post Title: !! Dirge of Cerberus FF7 (ver: us or int) (can NOT extract)

> Reply from falconcool
>
> Hi gentlemen,,I found a  way to extract the container.
There is a filelist.bin in disk's parent directory,it let me think of ff13's container structure.
I viewed both of the filelist,,they're the same structure in hexeditor.
So i used aluigi's bms script of ff13 to open it,,1st time,it failed,,then i rename
filist.bin into Filelist_scru.x360 ,and rename KEL.DAT into White_scru.x360,,

Haha aluigi's script extract everything!!!

here is the stuff i found in KEL.DAT



Now,,it's time to dig 3d model out!!!please help~
Some samples here
http://www.2shared.com/file/Xefqh00b/samples.html

I just found something, a menber "falconcool" managed to extract the big file kel.dat . 
I used his method and it worked! but this big file is not the videos... videos must be in b08ed50c.aa or 23cfdd41.f7 . but I cant extract these files the same way, got errors. 

anyone can help?
## Post #3
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-04-27T16:00:31+00:00
- Post Title: !! Dirge of Cerberus FF7 (ver: us or int) (can NOT extract)

Hi folks, I don't know if this is going to help but I just ran across this piece of code:
[docdec](http://hcs64.com/files/docdec.exe) ([source](http://hcs64.com/files/docdec.c))
which claims to decode Dirge of Cerberus video. I don't have any more information, feel free to give it a try and let me know how it turns out.
## Post #4
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-04-22T13:05:59+00:00
- Post Title: !! Dirge of Cerberus FF7 (ver: us or int) (can NOT extract)

All it does is decrypt the files contained in "video archives" such as d8f7bc60.45 and 7570f45e.f7(and that`s just the Japanese version) and then dump them. It doesn`t actually "decode" them.
## Post #5
- Username: truston
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 15, 2014 5:42 pm
- Post datetime: 2017-10-01T06:54:25+00:00
- Post Title: !! Dirge of Cerberus FF7 (ver: us or int) (can NOT extract)

> Reply from hcs
>
> Hi folks, I don't know if this is going to help but I just ran across this piece of code:
docdec (source)
which claims to decode Dirge of Cerberus video. I don't have any more information, feel free to give it a try and let me know how it turns out.

> Reply from AnonBaiter
>
> All it does is decrypt the files contained in "video archives" such as d8f7bc60.45 and 7570f45e.f7(and that`s just the Japanese version) and then dump them. It doesn`t actually "decode" them.

thank u for giving me this tool to try out. 
I tried with both US and JP versions. for JP, it does decrypt the big files and dump video files. 
for US, it also dumps files, 19 files totally, but no players or software can decode them! these are not recognizable video files! I guess, this tool may cut the big files RIGHT, but decrypt them WRONG... 
(also, these dumped files have standard PSS header, but nothing can decode them. don't know why...)
well, cutting the big files right can be a big step, I hope someone can decrypt them soon... 
thanx again!
## Post #6
- Username: Darius Charles
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 23, 2017 3:53 pm
- Post datetime: 2017-10-23T07:54:35+00:00
- Post Title: !! Dirge of Cerberus FF7 (ver: us or int) (can NOT extract)

I'll try JP version, tnx!
