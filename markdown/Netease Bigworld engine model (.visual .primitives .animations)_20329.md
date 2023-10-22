## Post #1
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-05-06T16:23:26+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

I've been working on this for a while.
I found netease games based on bigworld engine all of nearly.And I found a complete set model use Hex Editor
I tried many ways to view it，but
1.I use  viewtopic.php?p=126589#p126589  to import ".visual" and ".primitives",it Success，but model bone has make mistakes.
2.Wot model viewer. It can import primitive and visual information（netease .visual have been encrypted,it can deciphering.）but it can′t view and export bone
3.bigworld engine 2.1 it can import all of model information nearly(import.model files).But it can′t view Skinning.(maybe has been import)and,bigworld engine may can import animation,but I failed.It seems to be the most promising
So,I need help to import primitive and visual，animation better.
if I did,means all of old netease game model or bigworld model can be import Perfect,It can do a lot of things！
Here is a sample [https://www.mediafire.com/file/jcbcn2l1 ... r.rar/file](https://www.mediafire.com/file/jcbcn2l1n1aacke/char.rar/file)
try to use bigworld engine to view it?
Thanks!
## Post #2
- Username: Nguyen Thanh Tùng
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jan 12, 2019 8:53 am
- Post datetime: 2019-05-07T13:55:39+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

What games support ?
## Post #3
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-05-08T01:06:04+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from Nguyen Thanh Tùng ↑Tue May 07, 2019 9:55 pm at Tue May 07, 2019 9:55 pm
>
> 
What games support ?
so many
TianXia2
TianYu
Dragon Sword (JianLong)
## Post #4
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2019-05-10T02:14:51+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

Do you have more animation samples?   Maybe one sample from each game for comparison?
## Post #5
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-05-10T11:33:30+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from roswell ↑Fri May 10, 2019 10:14 am at Fri May 10, 2019 10:14 am
>
> 
Do you have more animation samples?   Maybe one sample from each game for comparison?
Here,this is bigworld engine provideed model
[https://www.mediafire.com/file/ot63o09p ... 64243/file](https://www.mediafire.com/file/ot63o09pqm0rh46/264243/file)
## Post #6
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2019-05-11T05:28:48+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

Thanks, but that's not the same animation file format as the first one.  The first animation file has a "AHED" id in the header.  The second one doesn't have it, so the animation format has changed or is different.  Do you have more AHED animations?
## Post #7
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-05-11T12:04:12+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from roswell ↑Sat May 11, 2019 1:28 pm at Sat May 11, 2019 1:28 pm
>
> 
Thanks, but that's not the same animation file format as the first one.  The first animation file has a "AHED" id in the header.  The second one doesn't have it, so the animation format has changed or is different.  Do you have more AHED animations?
here.
[https://www.mediafire.com/file/iqa9euu7 ... s.zip/file](https://www.mediafire.com/file/iqa9euu7wyelo85/animations.zip/file)
## Post #8
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2019-05-11T22:18:16+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

Thanks, that's a AHED file.  is that the original game extension, ".animations" ?  Bigworld engine are named ".animation".   Just wondering if the file has been renamed through extraction or some other means. 

Can you verify that Bigworld Engine is able to read these AHED animations, which have a different file format?
## Post #9
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-05-11T23:44:05+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from roswell ↑Sun May 12, 2019 6:18 am at Sun May 12, 2019 6:18 am
>
> 
Thanks, that's a AHED file.  is that the original game extension, ".animations" ?  Bigworld engine are named ".animation".   Just wondering if the file has been renamed through extraction or some other means. 

Can you verify that Bigworld Engine is able to read these AHED animations, which have a different file format?
No,original game extension is“.dat” .Bigworld engine can't 
read.But .primitve .visual also named “.dat”. .visual can be read.but .primitive skin  can't be view,only have bone.
## Post #10
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2019-05-12T06:44:09+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

Are you a programmer?  Do you write code or scripts?

This new animation file format is a chunked format.  I see 3 distinct chunks:
AHED
ACH1
ADAT

Chunk structure:
DWORD unk;		// always 4
DWORD chunk_id;		// AHED, ACH1, ADAT
DWORD data_length;	// bytes to follow

Basically, just loop chunks until end of file.


AHED contains some basic header information (names).
ACH1 contains some basic channel information (scale,pos,rot).
ADAT is unknown data.  I see no floats or other strings, so this data must be packed somewhow.

I'm guessing ACH1 means "channel 1", it only contains data for first animation channel (root?). 
The remaining animation channels must be packed in ADAT.

BigWorld animation format doesn't use chunks or packed data, so this is new to me.
## Post #11
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-05-12T07:13:34+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from roswell ↑Sun May 12, 2019 2:44 pm at Sun May 12, 2019 2:44 pm
>
> 
Are you a programmer?  Do you write code or scripts?

This new animation file format is a chunked format.  I see 3 distinct chunks:
AHED
ACH1
ADAT

Chunk structure:
DWORD unk;		// always 4
DWORD chunk_id;		// AHED, ACH1, ADAT
DWORD data_length;	// bytes to follow

Basically, just loop chunks until end of file.


AHED contains some basic header information (names).
ACH1 contains some basic channel information (scale,pos,rot).
ADAT is unknown data.  I see no floats or other strings, so this data must be packed somewhow.

I'm guessing ACH1 means "channel 1", it only contains data for first animation channel (root?). 
The remaining animation channels must be packed in ADAT.

BigWorld animation format doesn't use chunks or packed data, so this is new to me.
No，just out of curiosity.Netease game have so many good resources.
animation files can give up....
So,do you know how to import model(.primitives) and bone(.visual)？I can‘t import it simultaneously
And,thanks your help
## Post #12
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2019-05-12T08:25:19+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

This is the same format used in World of Tanks (WoT) (visual, primitives).  It's been a while, but I don't think the format hasn't changed.

You could try this Blender script:
[https://github.com/SkaceKamen/wot-model-converter](https://github.com/SkaceKamen/wot-model-converter)
## Post #13
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-05-12T13:48:15+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from roswell ↑Sun May 12, 2019 4:25 pm at Sun May 12, 2019 4:25 pm
>
> 
This is the same format used in World of Tanks (WoT) (visual, primitives).  It's been a while, but I don't think the format hasn't changed.

You could try this Blender script:
https://github.com/SkaceKamen/wot-model-converter
Thanks,but it can't export bone.......
## Post #14
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-05-14T07:50:53+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

Any other iders to make bigworld import to 3dsmax  or blender?
## Post #15
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2019-05-14T18:10:49+00:00
- Post Title: Netease Bigworld engine model (.visual .primitives .animations)

BigWorld Blender tools:
[http://www.twcenter.net/forums/showthre ... to-Blender](http://www.twcenter.net/forums/showthread.php?755614-World-of-Tank-into-Blender)

I can't seem to find a non-forum link to this file:
SkepticalFox-bigworld-blender-tools-wot-wowp-wows-23405f14ea7a.zip

It might contain something useful, as they use the same formats.
## Post #16
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-05-18T03:42:06+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from roswell ↑Wed May 15, 2019 2:10 am at Wed May 15, 2019 2:10 am
>
> 
BigWorld Blender tools:
http://www.twcenter.net/forums/showthre ... to-Blender

I can't seem to find a non-forum link to this file:
SkepticalFox-bigworld-blender-tools-wot-wowp-wows-23405f14ea7a.zip

It might contain something useful, as they use the same formats.
It still can‘t view bone.  
But,I  find a plugin in bigworld engine ‘visual_to_collada'.The plugin need Python 2.6 import _AssetProcessor.pyd.I can't  import  it.
ImportError: DLL load failed
## Post #17
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-05-25T00:29:40+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

I found ultimate unwrap 3d can import it,I  finished.
but, it need 56$ to resign that can be export......
## Post #18
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-06-19T15:03:47+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

@Bigchillghost Hello,and sorry to disturb you.Can you analyse the bigworld engine model？(World of tank,World of warships .etc)the bone is .visual
## Post #19
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-07-25T18:01:19+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

netease .visual  has been encryption.use unwrap 3d Wot plugin can Decrypt it ,you can find a visualtxt and get bone information.So,can convert it to fbx or dae?
## Post #20
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-08-22T18:46:35+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

any other idears?I can't find it anywhere.
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-24T03:12:04+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from 723119159 ↑Wed Jun 19, 2019 11:03 pm at Wed Jun 19, 2019 11:03 pm
>
> 
@Bigchillghost Hello,and sorry to disturb you.Can you analyse the bigworld engine model？(World of tank,World of warships .etc)the bone is .visual
The mesh format is simple, though normal vectors are encoded as vec2. The string "xyznuviiiwwtb" at offset 4 reveals the struct definition:

```
short	normal[2]
float	uv[2]
byte	boneIdx[3]
byte	weight[2]
short	tangent[2]
short	binormal[2]

```




1001.primitives.png (76.13 KiB) Viewed 219 times



The .visual bone file simply is an XML style document containing the bone tree, which'll be annoying to deal with, let alone its transformation format is nothing new.
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-24T03:20:04+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

Here's a param list file of 1001.primitives for [AMR](https://forum.xentax.com/viewtopic.php?f=33&t=20995).
...attachment removed...

Place it along with 1001.primitives into the location of AMR and open it from the panel to access to all param sets of all meshes in 1001.primitives.
## Post #23
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-08-24T04:54:48+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from Bigchillghost ↑Sat Aug 24, 2019 11:20 am at Sat Aug 24, 2019 11:20 am
>
> 
Here's a param list file of 1001.primitives for AMR.
1001.primitives.zip

Place it along with 1001.primitives into the location of AMR and open it from the panel to access to all param sets of all meshes in 1001.primitives.
Ok，thank you so much.
so,no ways to export  the bone?
I can use bigworld engine and uu3d to view it
## Post #24
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-24T05:48:15+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from 723119159 ↑Sat Aug 24, 2019 12:54 pm at Sat Aug 24, 2019 12:54 pm
>
> 
so,no ways to export  the bone?
There is an obvious one, just lack of interests though.
## Post #25
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-08-24T09:49:53+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from Bigchillghost ↑Sat Aug 24, 2019 1:48 pm at Sat Aug 24, 2019 1:48 pm
>
> 
723119159 wrote: ↑Sat Aug 24, 2019 12:54 pm
so,no ways to export  the bone?

There is an obvious one, just lack of interests though.
ok，thanks
## Post #26
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-08-24T17:04:00+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from Bigchillghost ↑Sat Aug 24, 2019 1:48 pm at Sat Aug 24, 2019 1:48 pm
>
> 
723119159 wrote: ↑Sat Aug 24, 2019 12:54 pm
so,no ways to export  the bone?

There is an obvious one, just lack of interests though.
But....could you tell me what is obvious one?
## Post #27
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-25T06:26:50+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from 723119159 ↑Sun Aug 25, 2019 1:04 am at Sun Aug 25, 2019 1:04 am
>
> 
But....could you tell me what is obvious one?
It's programing of course. If you need only the skeleton, you may try with SkelBuilder. Or you can use Noesis python if you need also the skin info.
## Post #28
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-08-27T18:04:15+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

> Reply from Bigchillghost ↑Sun Aug 25, 2019 2:26 pm at Sun Aug 25, 2019 2:26 pm
>
> 
723119159 wrote: ↑Sun Aug 25, 2019 1:04 am
But....could you tell me what is obvious one?

It's programing of course. If you need only the skeleton, you may try with SkelBuilder. Or you can use Noesis python if you need also the skin info.
I can't programing.....I just want to get this games and another netease bigworld engine model,and make xps...
Could you help me?
If you don't wanna do this, fair enough.
Thanks for you help
## Post #29
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2019-10-07T17:38:30+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

Complex Engine....
## Post #30
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2020-01-03T16:42:56+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

Months passed and I still can't get the bigworld engine bone.Because of the limitations of our country,I can't buy ultimate unwrap 3d...   
I want convert bigworld model to xnalara.
Any one have ultimate unwrap 3d?Just convert some models.I never use them for commercial purposes.
## Post #31
- Username: 723119159
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Dec 02, 2018 11:27 pm
- Post datetime: 2020-03-03T17:45:42+00:00
- Post Title: Re: Netease Bigworld engine model (.visual .primitives .animations)

...
