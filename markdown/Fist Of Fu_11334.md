## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-03-20T16:50:15+00:00
- Post Title: Fist Of Fu

Hello, well here I come back some years ago and post this format, this is a old anime game very funny models, I unpack all and get a couple of files like DDS, X and XET, so maybe somebody can take a look this format? this is header of X and XET files.

X


XT


[https://www.dropbox.com/s/urkm6j6nvs293 ... ata0%29.7z](https://www.dropbox.com/s/urkm6j6nvs2933p/FistOfFu%20%28data0%29.7z)
## Post #2
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-03-20T18:35:10+00:00
- Post Title: Fist Of Fu

.X looks like a standard [DirctX 3D file](http://paulbourke.net/dataformats/directx/)

I think Milkshape and older Blender versions can import it.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-03-20T19:53:47+00:00
- Post Title: Fist Of Fu

They are compressed so you will want to decompress the model file first before importing it into a program.
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-04-25T23:59:29+00:00
- Post Title: Fist Of Fu

> Reply from chrrox
>
> They are compressed so you will want to decompress the model file first before importing it into a program.so any help to descompress this files? can you provide some help please? or maybe you want money for do it don't know.
## Post #5
- Username: CriticalError
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-26T00:17:13+00:00
- Post Title: Fist Of Fu

sure you can pay me if you want.
[viewtopic.php?f=21&t=9064](http://forum.xentax.com/viewtopic.php?f=21&t=9064)
## Post #6
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-04-26T14:20:25+00:00
- Post Title: Fist Of Fu

> Reply from chrrox
>
> sure you can pay me if you want.
viewtopic.php?f=21&t=9064well many thanks for your help but when try descompress files I get that.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-26T16:50:46+00:00
- Post Title: Fist Of Fu

what .x file are you running it on? i tried them no problem.
the extractor you have looks wrong a lot of those .x files are not .x files.
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-04-26T18:38:27+00:00
- Post Title: Fist Of Fu

> Reply from chrrox
>
> what .x file are you running it on? i tried them no problem.
the extractor you have looks wrong a lot of those .x files are not .x files.the files I upload here, I try with them and no luck, so using your script to unpack them and after that modify the header how you say before, but can't descompress .X

PD: I have latest QuickBMS
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-26T23:29:54+00:00
- Post Title: Fist Of Fu

I used the file you posted the only ones that work are the xof ones.
MOST of the files you posted are not .x files.
Try it on Avatar_Xiaohu_Leg0080.x
it will create
Avatar_Xiaohu_Leg0080.X.cab
then extract the cab with Microsoft tool.



Avatar_Bow_weapon001.x is not a .x FILE.
look at it in a hex editor
starts with "KSM "


Only the files with a CAPITAL X are xof files.
the lowercase x files are KSM files.
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-04-27T04:52:42+00:00
- Post Title: Fist Of Fu

> Reply from chrrox
>
> I used the file you posted the only ones that work are the xof ones.
MOST of the files you posted are not .x files.
Try it on Avatar_Xiaohu_Leg0080.x
it will create
Avatar_Xiaohu_Leg0080.X.cab
then extract the cab with Microsoft tool.



Avatar_Bow_weapon001.x is not a .x FILE.
look at it in a hex editor
starts with "KSM "


Only the files with a CAPITAL X are xof files.
the lowercase x files are KSM files.
well many thanks for all your support chrrox, my question is next, why after editing with hex and adding 78 6F 66 20 30 33 30 33 74 78 74 20 30 30 33 32 or 78 6F 66 20 30 33 30 33 62 69 6E 20 30 30 33 32 and try load into 3DS Max with X Files Importer get error and can't be imported, my 3DS Max crash and close.

PD: so I understand what says in contribution of [Microsoft Direct X XOF Extractor](http://forum.xentax.com/viewtopic.php?f=21&t=9064) you say need change first 0x10 bytes but  Itry with 2 samples you put there and well anyway I get error when try load file.

Original CAB Unpacked



Header with XOF 0303txt 0032



Header with XOF 0303bin 0032
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-27T05:15:06+00:00
- Post Title: Fist Of Fu

you do not change you add one or the other before it.
## Post #12
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-04-27T05:27:45+00:00
- Post Title: Fist Of Fu

> Reply from chrrox
>
> you do not change you add one or the other before it.I add this values too before but no work.






PD: any chance get your skype ID via private?
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-04-27T16:46:32+00:00
- Post Title: Fist Of Fu

Most .x importers are terrible.
you can try deep exploration.
## Post #14
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-04-27T16:50:44+00:00
- Post Title: Fist Of Fu

I know it's not a very good method but personally I open .x files in mview.exe (MeshView from DirectX 9 SDK) and rip the meshes using a 3D ripper. That may be a bad choice if you want to export the bones and whatnot.

You could also try fragMOTION. It's not a free program but it has a trial version. It seems to have a pretty decent importer for .x files
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-28T04:48:13+00:00
- Post Title: Fist Of Fu

> Reply from CriticalError
>
> try load into 3DS Max with X Files Importer get error and can't be imported, my 3DS Max crash and close.using mofo's XPorter ([http://mofo.pns.to/wibs/#5](http://mofo.pns.to/wibs/#5)) with 3dsmax2013 works:



Avatar_Xiaohu_Leg0080_X.JPG (10.61 KiB) Viewed 163 times
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-28T05:14:09+00:00
- Post Title: Re: Fist Of Fu

using hex2obj on Avatar_Bow_weapon001:



Avatar_Bow_weapon001.JPG (67.36 KiB) Viewed 44 times
## Post #17
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-04-28T05:20:05+00:00
- Post Title: Re: Fist Of Fu

ok many thanks to all to give me support, in special to chrrox for script to descompress X files, really grateful for that, keep working guys, you're bests.
