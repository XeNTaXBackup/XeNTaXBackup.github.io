## Post #1
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-05-08T22:38:48+00:00
- Post Title: Onechanbara .dlc

So daemon1 [released a tool to convert Onechanbara Z2 Chaos (PC) models to smd/mesh.ascii](http://forum.xentax.com/viewtopic.php?p=130377#p130377) and it works pretty good. However, he has left it up to others to figure out textures and the dlc extraction but nobody has released anything. While we can get textures with some ninjaripper shenanigans, the dlc models are packed up and unusable with his tool (but apparently work if extracted). Hoping someone can help out with extracting the files for use with his tool. 

Here are the tools and what I was able to dig up about the dlc files. 

-The base game files are *.cat archives while the dlc files are, according to chroxx, ["just a .cat file xored with 0xEDDCBBE1C1FEDAAA](http://forum.xentax.com/viewtopic.php?p=119273#p119273)

-[The Tamsoft.cat bms script I posted here (that I didn't write) was used for extracting the base game *.cat files that are used with his tool](http://forum.xentax.com/viewtopic.php?p=130296#p130296). It does not extract the dlc files at all. 

Here are a few dlc samples. Will upload more if needed.

[https://mega.nz/#!joxXFIbI!Dr47Pb9Ub-FO ... 1_F35fihwY](https://mega.nz/#!joxXFIbI!Dr47Pb9Ub-FODHbMWZAHl0ec8dGRIrXgc1_F35fihwY)
## Post #2
- Username: phay008
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-05-09T09:06:34+00:00
- Post Title: Onechanbara .dlc

[viewtopic.php?f=10&t=14431&p=119273&hilit=cat#p119273](http://forum.xentax.com/viewtopic.php?f=10&t=14431&p=119273&hilit=cat#p119273)


its just a .cat file xored with 
0xEDDCBBE1C1FEDAAA

xor.exe "data00.dlc" "data00.dlc".cat 0xEDDCBBE1C1FEDAAA

works fine.
[data00.dlc.cat.7z](https://xentaxbackup.github.io/file/12872_data00.dlc.cat.7z)
## Post #3
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-05-09T16:38:45+00:00
- Post Title: Onechanbara .dlc

Yeah I got that part. Unfortunately none of the existing scripts (that I have at least) can extract the files afterwards.
## Post #4
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2017-08-23T21:03:03+00:00
- Post Title: Onechanbara .dlc

Taking another shot at this. Still hoping someone can help out with an extraction script for the dlc files. While the original thread/tools got deleted for whatever reason, my sample files still work.
