## Post #1
- Username: omar93
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 07, 2010 10:35 pm
- Post datetime: 2010-11-08T20:14:56+00:00
- Post Title: EA Sports MMA .ast textures

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-08T20:42:54+00:00
- Post Title: EA Sports MMA .ast textures

you need to post a sample file or 2 for us to look at to help you.
use a free file host like sendspace or mediafire.
## Post #3
- Username: omar93
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 07, 2010 10:35 pm
- Post datetime: 2010-11-08T20:48:25+00:00
- Post Title: EA Sports MMA .ast textures

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: dragbody
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-08T22:05:07+00:00
- Post Title: EA Sports MMA .ast textures

this is a bms script to extract the files they are dds files with an incorrect header just paste a valid 0x80 byte header on them and you get images like this.

```
get unk long
get files long
goto 0x2C
get nsize long
goto 0x4C
comtype zlib
for i = 0 < files
getdstring hash 0xA
get offset threebyte
math offset * 8
get zsize threebyte
get size threebyte
math size + zsize
getdstring name nsize
clog name offset zsize size
next i

```
## Post #5
- Username: omar93
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 07, 2010 10:35 pm
- Post datetime: 2010-11-09T19:17:42+00:00
- Post Title: EA Sports MMA .ast textures

Thanks very much for the script it works great!  
But after I don't know what to do to change the header file to have .dds.
## Post #6
- Username: omar93
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 07, 2010 10:35 pm
- Post datetime: 2010-11-13T23:19:35+00:00
- Post Title: EA Sports MMA .ast textures

Help please
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-11-16T19:47:13+00:00
- Post Title: EA Sports MMA .ast textures

What's about the converted files ?
[geom_to_obj.zip](https://xentaxbackup.github.io/file/3612_geom_to_obj.zip)
## Post #8
- Username: nbajam
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 24, 2010 5:39 am
- Post datetime: 2010-11-25T01:34:40+00:00
- Post Title: EA Sports MMA .ast textures

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-11-25T06:32:00+00:00
- Post Title: EA Sports MMA .ast textures

> Reply from Karpati
>
> What's about the converted files ?
How you converted the geometry?
## Post #10
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-11-25T06:40:42+00:00
- Post Title: EA Sports MMA .ast textures

> Reply from Tosyk
>
> How you converted the geometry?

I added a new loader module to the 3D Object C., but I did not released it yet.
(The vertex format definition is too horrible, so I must rewrite it)
## Post #11
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2011-08-02T17:25:42+00:00
- Post Title: EA Sports MMA .ast textures

Hi Karpati. 

Have you released the tool for this game yet?
I am looking forward to it.

Thank
## Post #12
- Username: skstylez
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 20, 2011 8:15 pm
- Post datetime: 2011-11-20T12:57:09+00:00
- Post Title: EA Sports MMA .ast textures

Sorry to bump this, but does anyone know which dds header will be the best one to use? If you can post the hex code, then that would be great.
## Post #13
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2011-11-20T16:04:39+00:00
- Post Title: EA Sports MMA .ast textures

> Reply from chrrox
>
> just paste a valid 0x80 byte header on them and you get images like this.

Hi chrrox or anyone
Can you tell me how to "paste a valid 0x80 byte header"
OR point me the web the do this

Thank you
## Post #14
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-03-08T18:27:30+00:00
- Post Title: EA Sports MMA .ast textures

> Reply from nattakorn
>
> Hi Karpati. 

Have you released the tool for this game yet?
I am looking forward to it.

Thank

I added the _GEOM model and the _COL / _COMP texture formats to my program (officially unreleased yet).
[http://3dconverter.webege.com/develop/3 ... 120308.zip](http://3dconverter.webege.com/develop/3doc_4801_20120308.zip)


You can add the texture file (_COL ; _COMP) to the material table by hand using the following procedure:

- open your model
- click on the Object and Material selector on the toolbar (from left the 3rd icon)
- click on the Materials line
- right click on the Material* line
- browse the texture file. (The texture files must be in same directory than the geometry files) .
- OK


After it the registered user can use the Tools/Export the material table's textures to .bmp files function (_COL ; _COMP to .bmp conversion)


I uploaded the original _GEOM; _COL; _COMP and the converted .obj/mtl and .bmp files:
[http://3dconverter.webege.com/converted ... pc_big.zip](http://3dconverter.webege.com/converted/EASPORTS_MMA_couturerandy_trainer_npc_big.zip)
## Post #15
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2012-03-15T11:03:07+00:00
- Post Title: EA Sports MMA .ast textures

Hi Karpati, thank you so much for the tool.
so far the tool seen to load all the "couturerandy_trainer_npc_big" files but for other characters the tool seen to only load the head model (face, eyes...). 
I try to load the texture files but it wouldn't load for me.

Anyways thank for this tool.
## Post #16
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-03-15T12:29:17+00:00
- Post Title: Re: EA Sports MMA .ast textures

> Reply from nattakorn
>
> so far the tool seen to load all the "couturerandy_trainer_npc_big" files but for other characters the tool seen to only load the head model (face, eyes...).

My program can load all of the *_GEOM files.

I don't know why, but not all .ast files have the full model.

The emelianenkofedor_big.ast file has only the following files (subobjects):

EMELIANENKOFEDOR_EYE_LEFT_GEOM
EMELIANENKOFEDOR_EYE_RIGHT_GEOM
EMELIANENKOFEDOR_EYELASHES_GEOM
EMELIANENKOFEDOR_HEAD_GEOM
EMELIANENKOFEDOR_MOUTHGUARD_GEOM 

As you can see it has not the body_geom file.  

> Reply from nattakorn
>
> I try to load the texture files but it wouldn't load for me.

Can you tell me what *_COL or *_COMP file(s)  did you try to open ?
## Post #17
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2012-03-16T18:36:18+00:00
- Post Title: Re: EA Sports MMA .ast textures

Hi Karpati, thank for the reply.

Yes, for the body I did not find any "body_geom" so I try to open the "SHAMROCKKEN_CLASSIC_BODY_MESH" and of course the program did not load it.

So to complete this character I think I need to find something like: SHAMROCKKEN_CLASSIC_BODY_geom and SHAMROCKKEN_CLASSIC_SHORT_geom right?

For the texture:
After I load "SHAMROCKKEN_CLASSIC_HEAD" file, I go to the materials and right click on the "1. material_1" and then browse the "SHAMROCKKEN_CLASSIC_HEAD_COL" file which is in the same folder. then I click ok at the "Detailed Material Information" and the window come up said that "Could not open the E:\...SHAMROCKKEN_CLASSIC_HEAD_COL file !"

Also, I think there are other textures that needed for the character like:
SHAMROCKKEN_CLASSIC_HEAD_NORM = Normal map
SHAMROCKKEN_CLASSIC_HEAD_SPEC = Specular map
SHAMROCKKEN_CLASSIC_HEAD_OCC = AO map
SHAMROCKKEN_CLASSIC_HEAD_FLEX = ??? maybe another Normal map.

finaly, I saw Chrrox posted about "paste a valid 0x80 byte header on them" but I am not sure how to do that. If you can help me? Thank.
## Post #18
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-03-17T19:13:41+00:00
- Post Title: Re: EA Sports MMA .ast textures

Can you send me ( [kz_3d@tvn.hu](mailto:kz_3d@tvn.hu) ) the .zip packed SHAMROCKKEN_CLASSIC_HEAD and the SHAMROCKKEN_CLASSIC_HEAD_COL files ?
## Post #19
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2012-03-19T15:01:37+00:00
- Post Title: Re: EA Sports MMA .ast textures

Hi Karpati. 
I sended you the files that I packed from SHAMROCKKEN_CLASSIC and normal SHAMROCKKEN packages to your mail.
and this like just for in case: [http://www.sendspace.com/file/tx0w7k](http://www.sendspace.com/file/tx0w7k)
## Post #20
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-03-21T20:59:19+00:00
- Post Title: Re: EA Sports MMA .ast textures

Thank you for your sample files.

I compared my and your files and I did find what was the diference.
My files are from the PC game, yours from XBOX. The XBOX file has an XPR2 container, it is not a problem, but I don't know how can I extract the bitmap datas correctly.
## Post #21
- Username: d2rnattakorn
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Mar 19, 2010 9:18 pm
- Post datetime: 2012-03-24T15:22:49+00:00
- Post Title: Re: EA Sports MMA .ast textures

What? There is a PC version of this game? I though that this game only release on  PS3 and Xbox360.

Anyways thank you for the reply, the only version that I have is Xbox360. If you would like me to upload anything please feel free to asks. I will upload them for you.
## Post #22
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-03-24T16:02:43+00:00
- Post Title: Re: EA Sports MMA .ast textures

> Reply from nattakorn
>
>     What? There is a PC version of this game? I though that this game only release on  PS3 and Xbox360.

Oh, no. I thinked for the PS3 (I am not a gamer).
## Post #23
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-02-19T17:00:22+00:00
- Post Title: Re: EA Sports MMA .ast textures

Hello everyone,

I'm sorry to bring up an old topic...

I've been able to extract the col files with no problem from the xbox version. I'm afraid that I'm a hex editing noob though and I don't know how to do what chrrox means when he says "paste a valid 0x80 header on them." I've tried a few things but have only gotten files that look like this...

[](http://imgbox.com/adnfnt1F) 

Are chrrox's instructions only good for the ps3 files? The xbox textures have an xpr2 container. I've tried some conversions for the xpr format without any better luck.

If anyone can please help me out, I'll be thankful for the assistance and the knowledge
## Post #24
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-09-28T01:42:16+00:00
- Post Title: Re: EA Sports MMA .ast textures

Is there any word on this? Reading through this thread, I see multiple people asking about the method of pasting the 0x80 header on the textures to make them work but there has not yet been an explanation. I've googled everything I can think of to read and figure it out on my own but with no luck, and I've tried cutting and pasting all sorts of things in a hex editor on these textures. At most I get various images like the one in my last post. 

I've linked the original files I'm trying to work with here: [http://www.mediafire.com/?a8nj6ms8c64fd4x](http://www.mediafire.com/?a8nj6ms8c64fd4x)

I would like to know how to convert them so that I can work with other files from the game. Even an image of what I should see from a hex editor will be sufficient. This is an off and on project for me with little progress for over six months now. I hope for someone kind in the forum to help.
## Post #25
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2013-09-28T03:54:17+00:00
- Post Title: Re: EA Sports MMA .ast textures

0x80 is the length of a dds header. I think chrrox was looking at PS3 textures, that probably won't apply to Xbox360 textures since they are likely swizzled.
## Post #26
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-09-28T03:59:36+00:00
- Post Title: Re: EA Sports MMA .ast textures

Thanks AceWell. I wondered if Chrrox was looking at ps3 files. I even bought the game for ps3 at one point with the intention of figuring out how to create an iso from it. I never got it though. 

So you think unswizzling the texture with the program from the Xbox developers kit might work? I may have to find a friend with that program.
## Post #27
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2013-09-28T04:33:50+00:00
- Post Title: Re: EA Sports MMA .ast textures

Maybe you can get chrrox to add support for it in his Noesis plugin.

[viewtopic.php?f=18&t=8102](http://forum.xentax.com/viewtopic.php?f=18&t=8102)
## Post #28
- Username: GTPunk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 22, 2018 2:32 am
- Post datetime: 2019-04-25T08:14:31+00:00
- Post Title: Re: EA Sports MMA .ast textures

i'm very sorry for resurrecting such old topic, and i'm ready for ban, but how to open .ast files actually? first answers are removed by 'rules violations' ,and i can't find another answers neither. i need mostly fedor's normals, hair textures, and some other fighters. if somebody can help (before my ban here, obviously) much appriciated
