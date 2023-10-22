## Post #1
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-05-10T18:15:41+00:00
- Post Title: Battleborn

Was wondering if anyone could decrpyt the .exe?

[https://www.dropbox.com/s/6d2onqyn3apua ... rn.7z?dl=0](https://www.dropbox.com/s/6d2onqyn3apua9o/Battleborn.7z?dl=0)

Gildor the creator of umodel, cant make any progress cause he needs the decrypted exe.

[http://www.gildor.org/smf/index.php?topic=2987.0](http://www.gildor.org/smf/index.php?topic=2987.0)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-10T18:24:24+00:00
- Post Title: Battleborn

You don't actually need the EXE to export stuff from UE. Though it can be done faster with it.
## Post #3
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2016-05-10T19:01:51+00:00
- Post Title: Battleborn

> Reply from daemon1
>
> You don't actually need the EXE to export stuff from UE. Though it can be done faster with it.

Im not sure the struggles Gildor is facing, but he said he cant do anything without the decrypted .exe
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-12T15:07:48+00:00
- Post Title: Battleborn

I checked the files. Its decompressed with old tools without problems. There are models, textures, everything may be extracted without the EXE. What exactly do you need from this game?
## Post #5
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2016-05-29T12:05:07+00:00
- Post Title: Battleborn

> Reply from daemon1
>
> I checked the files. Its decompressed with old tools without problems. There are models, textures, everything may be extracted without the EXE. What exactly do you need from this game?

how older?
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-29T20:01:54+00:00
- Post Title: Battleborn

I mean existing "extract" and "decompress" tools are working with this game, and you can get all game files.

And then you can convert textures and models manually, without the game .EXE
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-05-31T05:21:29+00:00
- Post Title: Battleborn

pls mods not reason to lock topic in this case..... unlocked..
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-02T18:19:11+00:00
- Post Title: Battleborn

Here's a quick extract & render of that mage provided in the files. There were 2 textures for body and head, but I didn't bother to split them, because maybe nobody is even interested. Skeleton with all bones & weights is also there, fully extractable. Usual UE3 stuff.
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-04T08:14:16+00:00
- Post Title: Battleborn

I'm not going to make a new Umodel. But since gildor is not going to support this game, I will just make a set of simple tools to extract all models and textures.

First set of tools here.

Drag .TFC file onto battleborn_tfc.exe and it will extract all textures (in game internal format)

Put Battleborn_dds.exe into that folder and run. This will convert all textures to DDS. BC7 textures (normal maps mostly) will be converted to DX10 DDS files which are only supported by newest viewers. Like Visual studio 2015 or texconv covertor.

You can already start labelling textures for characters you need. They are all organized simply.
[bbtools.rar](https://xentaxbackup.github.io/file/11008_bbtools.rar)
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-04T10:52:20+00:00
- Post Title: Battleborn

I've heard that umodel can export animations for this game. This is prob. because they are in some standard format. Can anyone check that, while I'm making a model tool?
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-04T12:04:11+00:00
- Post Title: Battleborn

This is how they do it. Every character has a default skin, and a grey-colored skin with a mask to make the clothes any color you choose:
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-04T13:55:59+00:00
- Post Title: Battleborn

And here we go, model convertor is working. Render with all maps, except wind map, I don't know how to apply it.



I don't see much effect from normal map, yet I'm not a modeller, maybe I do something wrong.
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-06-04T19:11:09+00:00
- Post Title: Battleborn

Some formats were a little different between characters. But now it looks like the tool works for them all. Bones are not exported yet, just OBJ files, but I can already publish the tool.
## Post #14
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2016-06-05T23:17:57+00:00
- Post Title: Battleborn

Yes Umodel seems to be able to export the animation by using the "-border" switch, dunno if it's all of them but it's still 3.55 gb of .psa files :V
