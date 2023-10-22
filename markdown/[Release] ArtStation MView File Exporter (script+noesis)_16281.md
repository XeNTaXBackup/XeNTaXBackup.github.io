## Post #1
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2017-05-15T08:42:56+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

Today I saw this post. The OP got into my nerves for dissing at shakotay2, a member I highly respect.

To prove the OP wrong I decided to check out how to unpack the mview file. With zero previous knowledge about the format I checked the link shakotay2 provided and it was in fact quite helpful. 

I then proceeded to write a parser and converter in about 30 minutes. This proved that the OP was completely ignorant for saying shakotay2's link was useless.

So, here are the scripts I wrote for unpacking the mview files: DOWNLOAD SCRIPT & NOESIS PLUGIN. 

Others might find it useful as I don't have any use for it.

Cheers!

EDIT: A Noesis plugin is also available:
## Post #2
- Username: soulbrother73
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jan 24, 2016 7:47 pm
- Post datetime: 2017-05-17T23:45:43+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

This works perfectly , the noesis plugin let's you convert the files to whatever I need.  Thanks
## Post #3
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2019-03-02T19:50:52+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

I noticed that people are still using this. I haven’t updated this for awhile now. But, if someone wishes to contribute in fixing the reported bugs feel free to make a PR.
## Post #4
- Username: projinf3d
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jul 17, 2016 8:56 am
- Post datetime: 2019-08-29T02:32:30+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

> Reply from majidemo ↑Mon May 15, 2017 4:42 pm at Mon May 15, 2017 4:42 pm
>
> 
Today I saw this post. The OP got into my nerves for dissing at shakotay2, a member I highly respect.

To prove the OP wrong I decided to check out how to unpack the mview file. With zero previous knowledge about the format I checked the link shakotay2 provided and it was in fact quite helpful. 

I then proceeded to write a parser and converter in about 30 minutes. This proved that the OP was completely ignorant for saying shakotay2's link was useless.

So, here are the scripts I wrote for unpacking the mview files: DOWNLOAD SCRIPT & NOESIS PLUGIN. 

Others might find it useful as I don't have any use for it.

Cheers!


Does this extract the bones for animated files also?

**EDIT I was successfully able to extract static m.view files but the animated ones give off the error below:

NOESIS PYTHON ERROR

Traceback (most recent call last):
File"C:\Users BLAH BLAH BLAH..\fmt_artstation_mview.py", line 19 in loadModel 
files = extract(bs)
File "C:\Users BLAH BLAH BLAH\fmt_artstation_mivew.py", line 136, in extract
	files[ftype}.append({ "filename": name, "data": bin })
KeyError: 'animData/mset'

I'm not after the animations so much, just the preservation of the bones so the characters can be configured for a default T-Pose..

Any help greatly appreciated...
## Post #5
- Username: alivekta
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 30, 2020 8:14 am
- Post datetime: 2020-04-30T13:56:34+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

can someone fix that error
## Post #6
- Username: DanGM
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 08, 2016 6:34 pm
- Post datetime: 2020-06-21T13:08:11+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

Is this development still alive? I have got it to work with a couple of models but getting some weird meshes on the specific model i am after. Anyone able to help?
## Post #7
- Username: Zaffar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 24, 2019 6:11 am
- Post datetime: 2020-07-17T07:11:57+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

> Reply from wubbaworwee ↑Thu Aug 29, 2019 10:32 am at Thu Aug 29, 2019 10:32 am
>
> 

Does this extract the bones for animated files also?

**EDIT I was successfully able to extract static m.view files but the animated ones give off the error below:

NOESIS PYTHON ERROR

Traceback (most recent call last):
File"C:\Users BLAH BLAH BLAH..\fmt_artstation_mview.py", line 19 in loadModel 
files = extract(bs)
File "C:\Users BLAH BLAH BLAH\fmt_artstation_mivew.py", line 136, in extract
	files[ftype}.append({ "filename": name, "data": bin })
KeyError: 'animData/mset'

I'm not after the animations so much, just the preservation of the bones so the characters can be configured for a default T-Pose..

Any help greatly appreciated...

I wonder if have some alternative for this error, i want to open a model but having a problem with the anims, there some way to cut off the animdata content from mview to import the static model?
## Post #8
- Username: guidkal
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 15, 2019 5:44 pm
- Post datetime: 2020-08-31T13:05:50+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

> I wonder if have some alternative for this error, i want to open a model but having a problem with the anims, there some way to cut off the animdata content from mview to import the static model?

I am wondering about the same thing. Would be cool if the creator of this script could give us a hint here. Cheers and thx for your work anyways!
## Post #9
- Username: W0lfy
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Mar 24, 2016 3:59 am
- Post datetime: 2020-09-16T10:19:09+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

NOESIS PYTHON ERROR

Traceback (most recent call last):
File"C:\Users BLAH BLAH BLAH..\fmt_artstation_mview.py", line 19 in loadModel
files = extract(bs)
File "C:\Users BLAH BLAH BLAH\fmt_artstation_mivew.py", line 136, in extract
files[ftype}.append({ "filename": name, "data": bin })
KeyError: 'animData/mset'

Got this error when trying to open an .mview with aniamtion data in it !

Please can anyone help, i just want the model don't need animation !
## Post #10
- Username: Lys
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 08, 2015 7:16 pm
- Post datetime: 2020-09-19T22:16:30+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

This may be a dumb question, but why not just use the python batch file  It should still pull static model and convert to obj even with animated mview. All you need is 32-bit python 3.6.1.
## Post #11
- Username: Chaotic1870
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 30, 2020 2:14 pm
- Post datetime: 2021-01-03T07:56:17+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

Hello, im very new to all this stuff, could someone walk me through how to do this? I have the mview file but im not sure where to go from there.
## Post #12
- Username: Volcanus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 12, 2021 1:17 pm
- Post datetime: 2021-09-12T05:30:39+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

I'm new to this forum as of 10min ago. I subbed just so that I could thank you for this plugin. I know this is an older post.
Thank you majidemo, you are seriously a rockstar.
## Post #13
- Username: JuanCarlos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 04, 2023 6:52 am
- Post datetime: 2023-01-03T23:06:16+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

Hi!
First of all, thank you for posting this awesome tool. I tried it and works perfectly for extracting 3D Models and PBR Textures. But, I have a problem when extracting HDRIs. When extracting an HDRI from an mview file, the format comes in a .dat file (sky.dat). I've been trying to change it from dat to .hdr or .exr but with no avail. Is it possible to extract an hdri from an mview file? 

Thanks.
## Post #14
- Username: race
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 12, 2023 1:26 am
- Post datetime: 2023-01-11T17:36:55+00:00
- Post Title: [Release] ArtStation MView File Exporter (script+noesis)

Hey people! I just found a modified file "fmt_artstation_mview.py" which accepts animations. Not export it, but doesn't give any error loading the file and exports the mesh in T-Pose.

I have tried it righty now and works perfectly.

The file is in this link:
[https://mega.nz/file/GsMDWChI#aiwj-hbKX ... Iv8aBVhqE4](https://mega.nz/file/GsMDWChI#aiwj-hbKXew3qq6dQ53LT_uMq1rbhY1m2Iv8aBVhqE4)

And this is the post of the original author of the modified file "fmt_artstation_mview.py":
[https://groinkick.freeforums.net/thread ... view-files](https://groinkick.freeforums.net/thread/20/ripping-marmoset-viewer-mview-files)

Enjoy and thank it to Stym from groinkick.
