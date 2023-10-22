## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-03T03:05:23+00:00
- Post Title: Longwu Online 《龙武》

Web: [http://lw.q1.com/](http://lw.q1.com/)
Download: [http://dl.q1.com/lw/LWSetup_BC_FD_0311.exe](http://dl.q1.com/lw/LWSetup_BC_FD_0311.exe)

Hello guys, well with help of Ekey I got files unpacked of this game, checking files unpacked I got some strange formats there, files with format .Fb and .mz in models and textures in dds, so well I ask for help with this format, maybe somebody can open files for view in 3d program, many thanks for all guys.

[http://puu.sh/bjb5v/719f71f4a2.7z](http://puu.sh/bjb5v/719f71f4a2.7z)
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-09-03T07:38:05+00:00
- Post Title: Longwu Online 《龙武》

Why there's only diffuse texture? You forgot to upload bump/spec maps or game doesn't use them?!
[onl.jpg](https://xentaxbackup.github.io/file/7767_onl.jpg)
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-03T16:20:59+00:00
- Post Title: Longwu Online 《龙武》

> Reply from zaramot
>
> Why there's only diffuse texture? You forgot to upload bump/spec maps or game doesn't use them?!omg thats great result, the model quality look very good, well about textures I upload all found in folder, sure no use them, rarely, but I upload all I found when unpacked files.

PS: you need more samples?
## Post #4
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-09-14T15:24:16+00:00
- Post Title: Longwu Online 《龙武》

Longwu Online for Blender 249  importer:
- mz - skinned mesh file
- fb - animation file 

How use:
- install Blender 249 and Python 26
- unpack importer
- click Blender249.blend
- press alt+p in Text Window
- select supported file type

If something is wrong send console error or file
[Blender249[LONGwuOnline][mz][fb][2014-09-14].zip](https://xentaxbackup.github.io/file/7816_Blender249[LONGwuOnline][mz][fb][2014-09-14].zip)
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-16T08:09:41+00:00
- Post Title: Longwu Online 《龙武》

wow thats great, awesome job, I format some minutes so I need install all my games again but no problem, I go to check it to soon, many thanks again for support, cheers.
## Post #6
- Username: hugo7yang
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 18, 2014 11:26 am
- Post datetime: 2014-09-19T03:30:24+00:00
- Post Title: Longwu Online 《龙武》

can you post unpacked tool,thanks very much.
## Post #7
- Username: Larss
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Aug 13, 2012 6:54 am
- Post datetime: 2015-01-29T19:09:27+00:00
- Post Title: Longwu Online 《龙武》

can anyone make a noesis script for the model format?
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-09-09T04:35:57+00:00
- Post Title: Longwu Online 《龙武》

any update zaramoth?
## Post #9
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-09-09T08:00:59+00:00
- Post Title: Longwu Online 《龙武》

Update? Script from Szkaradek123 doesn't work?
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-09-09T12:31:12+00:00
- Post Title: Longwu Online 《龙武》

client still updating and files was change I think.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2015-09-20T20:59:55+00:00
- Post Title: Longwu Online 《龙武》

Archives similar format as Blizzard's MPQ, so the MPQ editor can unpack them.
[viewtopic.php?f=10&t=10873](http://forum.xentax.com/viewtopic.php?f=10&t=10873)

I just tried it on the client linked in the OP.

However I just realized the latest client is 0915 (sep 2015??) so I'm DL'ing that now, but it's really slow.

If someone can just upload new models that don't work that would be easier.

The format from 0315 client presents a block-based format.

```
    char[4] NAME
    int SIZE
    byte[size] DATA
}

```


The first block has an REVM name, which, when you read it backwards, is MVER, which you can deduce as "Mesh version" or something like that. So far I have seen versions 22, 29, and 30, so one can presume that they continually update the model format.
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2015-09-20T22:50:00+00:00
- Post Title: Longwu Online 《龙武》

I've loaded the materials, but the material chunks are a bit weird
Example: [https://twitter.com/HimeWorks/status/645731531865092096](https://twitter.com/HimeWorks/status/645731531865092096)

So far there are four "versions" of the model format. 32 is the latest one I found from 0315 client.

I just finished downloading 0915 client and there's just more files.
Formats are the same as before.
