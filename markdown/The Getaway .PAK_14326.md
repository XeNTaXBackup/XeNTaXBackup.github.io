## Post #1
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2016-05-10T14:34:26+00:00
- Post Title: The Getaway .PAK

This has been requested before, alas for the music only~

Although I don't think someone might look into it, but here is the [PACK_EE.PAK](https://mega.nz/#!Y0pRWJhA!Qky4nG1I5pj7LHshHTQwzHPaQiB3_LHp_6hexVoNmKo) (560MB, if someone tells me how, I can split it).

This might be useful: [http://code.openhub.net/file?fid=RK8iuv ... ed=true#L0](http://code.openhub.net/file?fid=RK8iuvJ-51xlnhtKGL21mp0Is1U&cid=Yk9xRS96mpI&s=&fp=366660&mp&projSelected=true#L0)

[viewtopic.php?f=21&t=4442](http://forum.xentax.com/viewtopic.php?f=21&t=4442)

Thanks in advance. The game might be old, but the car models and the recreation of London are on very realistic levels, even to today's standards in my opinion.
## Post #2
- Username: DentistGuba
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Jun 11, 2017 1:27 am
- Post datetime: 2017-06-10T21:25:16+00:00
- Post Title: The Getaway .PAK

Hey RacingFreak, watched all your YouTube Getaway vids.

Not sure if you spotted this other forum with almost the same name as this one haha, aluigi over there wrote a script to unpack the .pak:
[http://zenhax.com/viewtopic.php?t=2625](http://zenhax.com/viewtopic.php?t=2625)

Been checking out the contents of EE/BigFiles after using that, inside there are a bunch of files with names like "00002b1e.por". The .por doesn't really mean anything, just the first three letters from the data, guessing the number part is the offset from the archive.

Trying to figure out mesh format, looks like this:



6D 6F 64 65 6C 00 00 00                       "model" header

A0 00 00 00 20 67 23 00 Some kind of generic parameters for "model" container? (40 byte fixed length)
00 00 00 00 6B BF 67 43 
00 00 00 00 87 14 6D 43 
A3 0E 1C 0C 07 00 09 00 
01 00 00 CD 00 00 00 00 

00 80 02 69 07 00 1C 0C Beginning of sub-mesh/element, thought 02 in tag meant 'two vertices' from similarity with next tag but first byte after tag (07) always matches vert number in next tag so this fixed length block (12 byte) must be some sub-mesh properties
08 00 CD CD 00 00 00 00 

02 80 07 69 00 7D 00 7D Vertices - third byte in tag should be count. Seems to divide into 7 x 6 bytes here but other models divide into 8 or 9 so must be something i'm missing
00 00 00 83 00 7D 00 00 
00 7D 43 5C 00 00 00 83 
43 5C 00 00 00 7D 43 5C 
00 00 00 83 00 00 00 00 
00 7D 00 00 00 00 00 00

01 80 07 6A 00 00 80 00                       Normal - 7 x 3(3x1 byte) with zero padding keeping 8 byte alignment, ps2 is 64bit
00 80 01 00 81 00 00 81 
00 00 80 00 00 81 01 00 
81 00 00 00 00 00 00 00 

00 80 07 65 3E 00 00 00                       UV - 7 x 4(2x2 byte)
33 03 00 00 3E 00 8C 04 
33 03 8C 04 3E 00 8C 04 
33 03 EB 00 3E 00 EB 00 


Guessed the normals and UV would be the same as God Of War - FurryFan found the same two 4 byte tags there, vertices seem to have '69' instead of '6D' in tag, maybe devs were feeling naughty.
[viewtopic.php?f=16&p=68272#p68272](http://forum.xentax.com/viewtopic.php?f=16&p=68272#p68272)
