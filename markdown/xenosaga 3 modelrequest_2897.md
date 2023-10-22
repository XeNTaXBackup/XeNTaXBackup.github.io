## Post #1
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-01-21T17:55:23+00:00
- Post Title: xenosaga 3 model??request

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-01-22T10:13:34+00:00
- Post Title: xenosaga 3 model??request

From what I can tell, they doesn't look like containing any 3D models but lots of texture.

```
word       "Xc"
word      version??
dword     fileLength
dword     fileLength2     //same as above??
word      SectionCount
word      "Xp"??            //Tag/Section name??
struct SectionName {
  char[4] / szString       //not sure
}

```


at 0x40 is the offset table

```
 dword    ofsStart
 dword    ofsLength
}
```
## Post #3
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-01-22T17:48:47+00:00
- Post Title: xenosaga 3 model??request

"From what I can tell, they doesn't look like containing any 3D models but lots of texture. "


hum
"Mario_Kart64n
here are nearly 100 files, seems the model maybe broken up into many smaller files, instead of being in a containing file, meaning everything shouyld be plain and simple.
there are a few file type here:
SED - ??
SWD - ??
XTX - ?texture data
BIN - base model?
ESD - ?contains icons?
JNT - bone chain?
LEX - ??index file
FPK - ??"

"hmm :\ ..
it seems all the textures are in a few places, mainly the .bin files, which i believe are model data. then the .xtx which was previously thought as texture data, which it is. but i don't fully understand whats happening?

i take the .xtx and place a 512x512 TIM2 texture header on it, and open it up, and get the same darn result
Click to view attachment
all alpha related textures show fine. anything else does not, like its on a seperate pallete, or the images are seperate.. like instead of one huge 512x512 there dozens of those little 8x8, or 16x16 images.. then they might be a P8 texture.. frig i hope not >_<

anyway if you llok close, you can see shions face texture in there.. black and white tho... sad.gif"

Link
Dark-Matter forum

J search....
## Post #4
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-01-22T17:49:35+00:00
- Post Title: xenosaga 3 model??request

From what I can tell, they doesn't look like containing any 3D models but lots of texture. "


hum
"Mario_Kart64n
here are nearly 100 files, seems the model maybe broken up into many smaller files, instead of being in a containing file, meaning everything shouyld be plain and simple.
there are a few file type here:
SED - ??
SWD - ??
XTX - ?texture data
BIN - base model?
ESD - ?contains icons?
JNT - bone chain?
LEX - ??index file
FPK - ??"

"hmm :\ ..
it seems all the textures are in a few places, mainly the .bin files, which i believe are model data. then the .xtx which was previously thought as texture data, which it is. but i don't fully understand whats happening?

i take the .xtx and place a 512x512 TIM2 texture header on it, and open it up, and get the same darn result
Click to view attachment
all alpha related textures show fine. anything else does not, like its on a seperate pallete, or the images are seperate.. like instead of one huge 512x512 there dozens of those little 8x8, or 16x16 images.. then they might be a P8 texture.. frig i hope not >_<

anyway if you llok close, you can see shions face texture in there.. black and white tho... sad.gif"

Link
Dark-Matter forum

J search....
## Post #5
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2008-01-23T04:12:00+00:00
- Post Title: xenosaga 3 model??request

I'll have to get these sample files rehosted. but I'll need to redump the game, and re-find that xenosaga2 extractor.
## Post #6
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-01-23T19:10:08+00:00
- Post Title: xenosaga 3 model??request

"re-find that xenosaga2 extractor."
G

There are Two
first use  C.RC console Ripper Creator

The secund is xenosaga extractor.exe

"'ll have to get these sample files rehosted"
Good idea, but, there  extractor no dump .bin or JNT or lex files


Ps
save modification or model switch
[http://www.youtube.com/watch?v=2Sd1gJmf ... ed&search=](http://www.youtube.com/watch?v=2Sd1gJmf8Ec&mode=related&search=)
## Post #7
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2008-01-24T15:20:30+00:00
- Post Title: xenosaga 3 model??request

O.O

how'd you do that? just replace the .bin file for kosmos an telos?

also I was able to get model rips using pcsx2(playstation2 emulator) its not perfect, but it works

i presume then, you don't require me to post X3 files, since it appears you already have a working extractor.

but of course it wouldn't extract lex or bin, because these aren't container files.
## Post #8
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-01-25T13:45:25+00:00
- Post Title: xenosaga 3 model??request

"O.O

how'd you do that? just replace the .bin file for kosmos an telos?

also I was able to get model rips using pcsx2(playstation2 emulator) its not perfect, but it works

i presume then, you don't require me to post X3 files, since it appears you already have a working extractor.

but of course it wouldn't extract lex or bin, because these aren't container files."


"how'd you do that? just replace the .bin file for kosmos an telos?
"
i dont idea.


"
also I was able to get model rips using pcsx2(playstation2 emulator) its not perfect, but it works"

No, j' have a "flat mesh", pcsx2 reset z data geometry .

"i presume then, you don't require me to post X3 files, since it appears you already have a working extractor.
"
J want :


BIN  and lex and JNT file.
"but of course it wouldn't extract lex or bin, because these aren't container files."
"
AÏE?!


Hum,Mario_Kart, the data content CHR file,---->header XTX file texture,or not ??


PS: sorry for my bad english
## Post #9
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2008-01-25T19:35:16+00:00
- Post Title: xenosaga 3 model??request

Quote from Mario Kart:
also I was able to get model rips using pcsx2(playstation2 emulator) its not perfect, but it works 

Whoa, that is exciting. Mario Kart or anyone else, could you explain how this was done? Did PCSX2 have to be modded to dump the model geometry and then the models were re-constructed from that? Or is there a model ripping program that can be used successfully with PCSX2?

Bah, I'd ask over at DarkMatter, but it's down atm.
## Post #10
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2008-01-25T19:59:40+00:00
- Post Title: xenosaga 3 model??request

sorry, kalrua. i'm having a hard time understanding you. but I'll find the files and post them as soon as i can.

also @FaustWolf

you just take 2 rips then combine them, to solve for Z.
## Post #11
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-01-25T21:12:26+00:00
- Post Title: xenosaga 3 model??request

"sorry, kalrua. i'm having a hard time understanding you. but I'll find the files and post them as soon as i can.

also @FaustWolf

you just take 2 rips then combine them, to solve for Z. "



OUAHHHHHHHH
No perspective error O
I try the two last week

Tutorials, please...... :D  :D  :D  :D  :D
## Post #12
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2008-01-25T21:43:34+00:00
- Post Title: xenosaga 3 model??request

Holy cow Mario Kart, that sounds ingenious. Which model-ripping utility are you using with PCSX2? And which model viewing program are you using? Does Blender, for example, have the necessary capabilities? Do you have any documentation on this model-ripping method you could share? 

Also, anyone have links where the various file extraction utilities for the Xenosaga games can be downloaded? Will these be hosted one day at your site Mario Kart?

This is a breakthrough for videogame model enthusiasts. Thanks for all your work Mario!
## Post #13
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-01-27T20:48:38+00:00
- Post Title: xenosaga 3 model??request

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2008-01-28T16:37:41+00:00
- Post Title: xenosaga 3 model??request

Thanks for the info kalrua!
## Post #15
- Username: kronos
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 29, 2008 3:30 am
- Post datetime: 2008-01-28T20:47:40+00:00
- Post Title: xenosaga 3 model??request

Hi to Everyone.

Interesting ... I have the following original Games: XENOSAGA I+ II + III + Namco X Capcom. I would like to extract KOSMOS 3d model ( Xenosaga 3 especially ) into a 3D program ( Metasequoia or Blender can be used instead of 3ds max? ). I would like to build a KOSMOS MS AGENT for personal use. I'm interested in AI and I would like to use such Agent with Universal Virtual Human Interface when It will be available: [http://www.vrconsulting.it/vhf/topic.as ... hichpage=1](http://www.vrconsulting.it/vhf/topic.asp?TOPIC_ID=446&whichpage=1)

Then I would like to extract kosmos voice files and subtitles to associate sounds to events and to build a dedicated AIML file for Her. Ingame script can be easily found but if everything could be extracted it would be the best. 

As an alternative I could buy Poser 7 or use DAZ studio but I don't know if I can build a 3D model that resembles KOSMOS using DAZ packages. It would be great due to HQ models like Victoria 4.1. With Poser Pro ( this winter release ) and Powerfusion plugins it is possible to import into 3ds max or maya 3d models with animations. I don't know if it will work with a trial version of 3ds max or with MAYA 8.5 ple. 

Can be posted direct links for related tools? 
Doesn't exist a program like Dragon unpacker for Xenosaga series?

Could You help me, please? Thank You.
Hi.
## Post #16
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-01-29T19:43:12+00:00
- Post Title: 

"Doesn't exist a program like Dragon unpacker for Xenosaga series?
"

No   :cry: 

"Can be posted direct links for related tools? "

No, search here:[http://www.alucard.cc/forums/](http://www.alucard.cc/forums/)
## Post #17
- Username: kronos
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 29, 2008 3:30 am
- Post datetime: 2008-01-29T20:01:39+00:00
- Post Title: 

Hi. Thank You. Hi.
## Post #18
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-06-23T12:09:19+00:00
- Post Title: 

The contents of this post was deleted because of possible forum rules violation.
## Post #19
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-07-01T16:42:54+00:00
- Post Title: 

The contents of this post was deleted because of possible forum rules violation.
## Post #20
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2008-07-08T07:28:00+00:00
- Post Title: 

wow that's awesome, does any animation work, or is it totally in a neutral pose.
## Post #21
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-07-08T13:27:23+00:00
- Post Title: 

"(: wow that's awesome, does any animation work, or is it totally in a neutral pose."


It telos's red eyes version, no animation(only hairs simulation), but shion animations work on kos mos (;
## Post #22
- Username: Novax
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 29, 2008 5:41 pm
- Post datetime: 2008-08-23T09:10:13+00:00
- Post Title: 

Hmm...maybe a converter can bring about a feasible model for us to view. Anyways, how are things going with this?
## Post #23
- Username: Kos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 26, 2008 3:52 am
- Post datetime: 2008-12-27T21:09:53+00:00
- Post Title: 

Hey was wondering if anyone still had that extracter or the kos-mos model for 3ds 9 or any other version been trying to find a model for a while now if you could help that would be awesome thanks.
## Post #24
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2008-12-28T20:05:13+00:00
- Post Title: 

"Hey was wondering if anyone still had that extracter or the kos-mos model for 3ds 9 or any other version been trying to find a model for a while now if you could help that would be awesome thanks.
Hey was wondering if anyone still had that extracter or the kos-mos model for 3ds 9 or any other version been trying to find a model for a while now if you could help that would be awesome thanks.
	Post 	Posted: Sat Dec 27, 2008 10:09 pm
"


3d via printscreen + gskosmos +pcsx2 no vm

into 3ds, use scale tool for Z axis

j dump:kosmos v4, v3+wings, and durandale, etc

Need uvmap rescale.
texmod + gsdx = texture file fragments.
Its hard, j dump only kos mos texture(two)


Animation=slave
Skeleton=master---------->shion, momo, kosmos, etc=one set animations.

Kosmos blues eyes textures= shion eyes textures.(multimaterials)
## Post #25
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2009-05-09T22:01:29+00:00
- Post Title: 

Sorry for reviving this, but I have a few questions...

I'm guessing you used 3D Ripper DX to rip the models, but what were you viewing them in? Were you using pcsx2?

Can someone explain the "solving for z" using two rips...?

Is anyone still messing with this at all?
## Post #26
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-10T01:43:50+00:00
- Post Title: 

you need to have 2 views of the exact same frame capture using 3d ripper dx.
the only way to do this is in the model viewer mode.
take 1 capture straight on then take one side profile snapshot.
then there is a max script you must run on the 2 files that will solve for the depth and it will make the image 3d again.
I can't remember the name of the script off the top oif my head if I can dig it up ill post it.
## Post #27
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2009-05-22T12:23:12+00:00
- Post Title: 

"you need to have 2 views of the exact same frame capture using 3d ripper dx.
"


3dvia printscreen grab the axis data.
## Post #28
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2009-05-22T17:28:03+00:00
- Post Title: 

How can I possibly make two different views from one frame?



And I should use PCSX2?
## Post #29
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2009-10-27T21:30:50+00:00
- Post Title: 

HI
.chr shion and kosmos .chr replacement
[img][http://img260.imageshack.us/i/kosmosshion.png/](http://img260.imageshack.us/i/kosmosshion.png/)[/img]

Animation:full work, no error
model:full work, no error

use Xeno3TradKit-complete.rar
decompresse archive
replace .chr
repack archive
repack ps2 format
run pcsx2

.chr=data archive:3d models?, materials and textures

pcsx2 shader 2.0 gsdx + 3dviaprinscreen

durandale(no textured)
[img][http://img210.imageshack.us/img210/9969/durandale.png](http://img210.imageshack.us/img210/9969/durandale.png)[/img]
kosmos(texture repared and rescale uvmap)
[img][http://img340.imageshack.us/img340/999/kosmosv4.png](http://img340.imageshack.us/img340/999/kosmosv4.png)[/img]
## Post #30
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-10-31T04:07:00+00:00
- Post Title: 

O_o 3dvia extracted the UV map?

usually when I did it 3dvia would extract a damaged UV map
## Post #31
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2009-10-31T04:40:28+00:00
- Post Title: Re: xenosaga 3 model??request

I tried 3DVia, but it would only let me capture a random body part at a time... (I have an index finger, a pair of wrists, an eyebrow, and a face, and a partial torso chunk... all were stretched in horrible ways and took hours to reshape... even then they were all from different frames of animation, making none of them fit together...)

I extracted them from the model viewer, was that a bad idea?
## Post #32
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-10-31T04:46:01+00:00
- Post Title: Re: xenosaga 3 model??request

sounds like vista
## Post #33
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2009-10-31T05:06:41+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from Mario_Kart
>
> sounds like vista

XP fortunately... but that also means UNfortunately I have no idea what the problem is....
## Post #34
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2009-10-31T19:59:22+00:00
- Post Title: Re: xenosaga 3 model??request

HI  
[quote="Mario_Kart"]O_o 3dvia extracted the UV map?


usually when I did it 3dvia would extract a damaged UV map[/quote]

*
Shader 2.0=uv map grabed
Shader 3.0=uv map error

Rifle capture key (3dviaprintsreen)

see rip size

Pcsx2fhhgg.1ko<---bad
Pcsx2fhhgg.1ko<---bad
Pcsx2fhhgg.1ko<---bad
Pcsx2fhhgg.1057ko<---good!!

Import into 3d editor
Select all flat screen mesh
Use scale tools

Fixe de polygonial normal error
3dviprintcreen grabe the memory buffer

Another solution:analyse .chr data (archive model)
## Post #35
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-10-31T20:28:04+00:00
- Post Title: Re: xenosaga 3 model??request

.. your saying that your UV's were perfect
## Post #36
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2009-11-08T15:16:34+00:00
- Post Title: Re: xenosaga 3 model??request

[quote="Mario_Kart"].. your saying that your UV's were perfect[/quote]


Yes, into shader model 2.0, try (grabe mesh gsdx)

Work: xenosaga III

Edit
"that's weird, that plugin use to never work"

Woooops:
-Grabe mesh [b]ZeroKosmosGS[/b]
             -Grabe texture texmod+ gsdx
Sorry for this error
## Post #37
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-11-08T18:50:09+00:00
- Post Title: Re: xenosaga 3 model??request

that's weird, that plugin use to never work
## Post #38
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2009-11-08T20:44:03+00:00
- Post Title: Re: xenosaga 3 model??request

[quote="Mario_Kart"]that's weird, that plugin use to never work[/quote]

Woooops:
-Grabe mesh [b]ZeroKosmosGS[/b]
-Grabe texture texmod+ gsdx
Sorry for this error
## Post #39
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-11-08T23:45:51+00:00
- Post Title: Re: xenosaga 3 model??request

I hacked the memory to tpose the models, but I lost my old pcsx2 folder.. this was a long time... 

anyway keep up the good work, please share telos if you get her

EDIT
I can confirm that the CHR files are model files. the CHR containers holds 4 common sub blocks.
pxy - Model Data, material data, skin data?
txy - Texture Data?
xhr - bone data?
epf - end of container?



here are some CHR swapping experiments, proving that the CHR file is more then texture data
these are shions hidden character models





EDIT2

I ran float2txt on the pxy data chunk, and got what appears to be the vertices of telos
## Post #40
- Username: EssiMonster
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 06, 2010 9:32 pm
- Post datetime: 2010-01-06T15:37:48+00:00
- Post Title: Re: xenosaga 3 model??request

Hi guys,

I've been desperately searching for the 3d models of Xenosaga for years now and it seems like you made some good progress in extracting those models. Would you mind sharing your recent achievements with me? I tried to download the stuff kalrua posted here (rapidshare links) but sadly they got removed   
It would be really awesome if someone who still has these could reupload it for me. And the models Mario_Kart's discovered look great, too.
I'd soooo like to get them.
So if someone could reupload it for me I'd be grateful forever.

And another question: Did someone already figure out a way to put these models into 3D Studio or some similar program?

thanks
## Post #41
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-01-07T15:06:41+00:00
- Post Title: Re: xenosaga 3 model??request

Mario_kart, can you possibly explain how you hacked the memory, and what addresses to modify?

I'd very much like to see those models, and any others that may be hidden...

Also, did you purposely remove the animations from them or did they just not have any to display? If I could get the models in their bind pose like that it would be very helpful for ripping...
## Post #42
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2010-01-08T12:28:21+00:00
- Post Title: Re: xenosaga 3 model??request

The contents of this post was deleted because of possible forum rules violation.
## Post #43
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-01-08T14:49:46+00:00
- Post Title: Re: xenosaga 3 model??request

The contents of this post was deleted because of possible forum rules violation.
## Post #44
- Username: EssiMonster
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 06, 2010 9:32 pm
- Post datetime: 2010-01-08T16:19:29+00:00
- Post Title: Re: xenosaga 3 model??request

The contents of this post was deleted because of possible forum rules violation.
## Post #45
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-01-08T19:20:58+00:00
- Post Title: Re: xenosaga 3 model??request

The contents of this post was deleted because of possible forum rules violation.
## Post #46
- Username: kalrua
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Nov 23, 2007 5:29 am
- Post datetime: 2010-01-08T21:07:03+00:00
- Post Title: Re: xenosaga 3 model??request

"It could be that some of the unknown blocks are character dialogue, protraits, stats,"


No

Portrait=.jpeg or .bmp files, j can open files with paint!!!
Dialogue and subtitles=another files, see Xenosaga tradkit, subtitle open with....notepad!!
## Post #47
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-01-10T08:17:28+00:00
- Post Title: Re: xenosaga 3 model??request

So, I'm trying to modify the ISO of my XSIII disk to display other models in place of the normal ones(like Mario_Kart did with swapping Shion's model) and I'm fairly confident I did it right, but I'm not sure how to get the new SLUS into the ISO without corrupting the PS2 compatibility...

How did you do it Mario_Kart? (also, I'd like to know what addresses need to be changed to get models in their bind pose)

Did you use save state modding to change the models or did you change the ISO itself?



On another note, I've been trying to pick up on the format of the PXY and TXY... but I'm not sure what documentation is correct... is there a full set of data write-ups anywhere or do I just have to rummage around and piece it together from random posts?

EDIT: I managed to get most of the characters, enemies, and machines into their bind poses by deleting the .sme extensions from the files listed in the PCSX2 savestate... However, for some reason Shion's animations and some of the enemies are unaffected... 

I have yet to be able to change any of the models that display, despite changing all of the listings of "shion" into various other things... I still always end up with Shion...

What do I need to change to get a different model to display in Shion's place in the character viewer...?

When I changed the names of  the .chr entries in the state, it didn't do anything useful... nor when I changed various extensionless entries... the most I managed was to get the models to display as Shion's normal model... but I couldn't get them to display any of her other models...

EDIT2:
I found it now... Seems I could use my printscreening on this game finally... but how do I get UV's to dump?
## Post #48
- Username: Novax
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 29, 2008 5:41 pm
- Post datetime: 2010-03-03T07:20:53+00:00
- Post Title: Re: xenosaga 3 model??request

How goes with the results of everyone's labor? I haven't done this in such a long time and finally getting back to it. I blame my life among other stupid things. Just curious cause I've been hearing another method that may help with this.
## Post #49
- Username: Heroine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 27, 2010 4:13 pm
- Post datetime: 2010-03-28T18:51:56+00:00
- Post Title: Re: xenosaga 3 model??request

Hello,I finally captured the front view and side view but gave up the modeling,because it's too hard for me  .
Could someone please tell me how to do it,or how to view the model in 3D programs(by converting the .chr files)?
Thanks very much.  

And here's my [model swapping screenshots](http://s22.photobucket.com/albums/b327/GundamMk2/Xenosaga/)  .
## Post #50
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-04-16T17:55:20+00:00
- Post Title: Re: xenosaga 3 model??request

actually we have managed to load vertex, found groups but not the faces index and uv's , still working on it on our free time ^^
## Post #51
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-04-16T19:52:44+00:00
- Post Title: Re: xenosaga 3 model??request

seems to use different vertex and face types >.<
## Post #52
- Username: shotgun12ga
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Apr 18, 2010 8:31 am
- Post datetime: 2010-04-18T13:46:29+00:00
- Post Title: Re: xenosaga 3 model??request

Hi all, could someone please post the xenosaga 3 uncensored nude shion model for me.thank you.
## Post #53
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-04-18T18:41:52+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from shotgun12ga
>
> Hi all, could someone please post the xenosaga 3 uncensored nude shion model for me.thank you.
Discretion fail...

There's nothing to see anyway. She's really just a skin colored mannequin... Or do you want the actual file the model is stored in?
## Post #54
- Username: shotgun12ga
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Apr 18, 2010 8:31 am
- Post datetime: 2010-04-18T19:15:09+00:00
- Post Title: Re: xenosaga 3 model??request

Hi, i know that she is in barbie doll form but i still would like to see the pictures of it, they were found by mariokart64n and the censored version can be found earlier in this thread.I would like to see front and back at least. thank you
## Post #55
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-04-19T11:45:54+00:00
- Post Title: Re: xenosaga 3 model??request

another one that don't read fully all users post ^^
## Post #56
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-04-19T17:34:03+00:00
- Post Title: Re: xenosaga 3 model??request

Hi everyone,

I am finally want to start on Xenosaga, I've got Xenosaga II (soon have III as well).
But having trouble to get the resources out of the DVD!
How do you guys get the files with those original names? Or is there any tools to unpack the data!

Could anyone show me the way on this so I can catch up and help.
Thanks
## Post #57
- Username: firsak
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-19T20:13:25+00:00
- Post Title: Re: xenosaga 3 model??request

The contents of this post was deleted because of possible forum rules violation.
## Post #58
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-04-21T19:49:57+00:00
- Post Title: Re: xenosaga 3 model??request

I usually do the texture first and this texture(txy) make me crazy!!!
Two days hard work with almost no result!!!

Image Data seems to be indexed color, indices and palette are Overlapping!?

Here is what I got so far, any help?

```
  char[4]       ResID           //"txy\0"
  dword         ??              //always 1
  dword         TXY_size
  dword         ??              //always 0
  dword         ofsInfo         //always 0x90
}

struct TXY_Info {
  dword         ??              //always 0x40
  dword         ??              //always 8
  dword         ??              //always 0x200
  dword         ??
  dword         ??              //always 0
  dword         numTexture
  dword         numMaterial??
  dword         ??              //always 0
  byte_256      TextureInfo     //32 bytes each, left with 00 padding!
  <Material? 96-bytes each>
}

struct TextureInfo {
  dword         ofsTextureData
  dword
  dword         ImageWidth??
  dword         ImageHeight??
  dword         ??              //always 0
  dword         ImageSize       //real size needs to multiply 16
  dword         ??
  dword         ??
}
```
## Post #59
- Username: shotgun12ga
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Apr 18, 2010 8:31 am
- Post datetime: 2010-04-23T19:02:18+00:00
- Post Title: Re: xenosaga 3 model??request

Please dont forget about my request, thank you
## Post #60
- Username: Heroine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 27, 2010 4:13 pm
- Post datetime: 2010-04-24T08:53:54+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from shotgun12ga
>
> Please dont forget about my request, thank you
[http://anime.geocities.jp/psychicvotare ... sshion.zip](http://anime.geocities.jp/psychicvotaress/gallery/snapsshion.zip)
Is this ok?
## Post #61
- Username: shotgun12ga
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Apr 18, 2010 8:31 am
- Post datetime: 2010-04-24T10:47:50+00:00
- Post Title: Re: xenosaga 3 model??request

hi, it says its forbidden and i dont understand japanese. i cant read anything but english,thank you
## Post #62
- Username: Heroine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 27, 2010 4:13 pm
- Post datetime: 2010-04-24T16:04:01+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from shotgun12ga
>
> hi, it says its forbidden and i dont understand japanese. i cant read anything but english,thank you
[http://www.megafileupload.com/en/file/2 ... n-zip.html](http://www.megafileupload.com/en/file/221818/snapsshion-zip.html)
## Post #63
- Username: shotgun12ga
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Apr 18, 2010 8:31 am
- Post datetime: 2010-04-24T18:11:50+00:00
- Post Title: Re: xenosaga 3 model??request

i really appriecate this ty ty ty
## Post #64
- Username: aramaki
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 23, 2010 5:47 am
- Post datetime: 2010-05-22T22:38:52+00:00
- Post Title: Re: xenosaga 3 model??request

hi, everyone!  new here... just joined for this topic!
just wanna say i'm impressed with the work being done and am very excited about it.  
i'm aware that it's possible to replace models to be viewed in the character viewer... but i was wondering, i've seen a video of T-elos replacing kos-mos in-game and was wondering if the method of swapping models in the viewer changes the in-game models as well to get similar results?
on a side not... have the models been successfully converted to an editable format (.obj for example)?  it would be sweet to be able to make some custom tweaks to models and recompile the iso to play with the changes.
## Post #65
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-05-22T23:03:00+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from aramaki
>
> hi, everyone!  new here... just joined for this topic!
just wanna say i'm impressed with the work being done and am very excited about it.  
i'm aware that it's possible to replace models to be viewed in the character viewer... but i was wondering, i've seen a video of T-elos replacing kos-mos in-game and was wondering if the method of swapping models in the viewer changes the in-game models as well to get similar results?
on a side not... have the models been successfully converted to an editable format (.obj for example)?  it would be sweet to be able to make some custom tweaks to models and recompile the iso to play with the changes.

I think what you saw was the 'Undub' Xenosaga III, in which someone opened up the ISO and changed some files around, replacing the english audio files with the japanese ones, and changing one of the costume items from Kosmos' model to Telos.

Then the ISO was repackaged and burned to disc and played on either an emulator or a modded PS2.

I doubt the method used for changing models in the viewer would work for normal gameplay...



EDIT: Yes the models have been dumped to OBJ, but they are filled with unknown data and no UVs are properly dumped, and OBJ doesn't support skeletal structures, thus, dumping to OBJ is useless for reinserting models.

Secondly, it is much more difficult to get a model back into the ISO than it is to convert it to another format. 

If you really want to minorly tweak models, I suggest opening up the ISO in a hexeditor and playing with that.
## Post #66
- Username: aramaki
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 23, 2010 5:47 am
- Post datetime: 2010-05-23T06:00:43+00:00
- Post Title: Re: xenosaga 3 model??request

i know reinserting data to an iso is never fun, just wasn't sure if the game uses the same files used in the viewer for battle/world models.  as for converting to .obj (or a better format that handles more data) how is this done?
## Post #67
- Username: Heroine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 27, 2010 4:13 pm
- Post datetime: 2010-05-23T08:13:01+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from aramaki
>
> i know reinserting data to an iso is never fun, just wasn't sure if the game uses the same files used in the viewer for battle/world models.  as for converting to .obj (or a better format that handles more data) how is this done?
Probably right(Some models seemed broken in the viewer,for I did an incompletely swapping,but they looked normal in battle/world) .
[gsdx_20100327174055.jpg](http://i22.photobucket.com/albums/b327/GundamMk2/Xenosaga/gsdx_20100327174055.jpg)
[gsdx_20100327174130.jpg](http://i22.photobucket.com/albums/b327/GundamMk2/Xenosaga/gsdx_20100327174130.jpg)
## Post #68
- Username: aramaki
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 23, 2010 5:47 am
- Post datetime: 2010-05-23T18:31:05+00:00
- Post Title: Re: xenosaga 3 model??request

very cool!  if only i wasn't house sitting i would start playing around with this.
## Post #69
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-05-28T21:40:45+00:00
- Post Title: Re: xenosaga 3 model??request

Does it continue to work once the models are unloaded and loaded again, such as after changing maps to a completely different level set?
## Post #70
- Username: Heroine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 27, 2010 4:13 pm
- Post datetime: 2010-05-31T15:50:06+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from Satoh
>
> Does it continue to work once the models are unloaded and loaded again, such as after changing maps to a completely different level set?
I replaced kosmos' chr files with shion's,so it works(I think).
[gsdx_20100327180414.jpg](http://i22.photobucket.com/albums/b327/GundamMk2/Xenosaga/gsdx_20100327180414.jpg)
[gsdx_20100327180254.jpg](http://i22.photobucket.com/albums/b327/GundamMk2/Xenosaga/gsdx_20100327180254.jpg)
By the way,do you have the tool to convert the models into .obj files?  
[I saw the article here.](http://blogs.yahoo.co.jp/osaka_0705/60087913.html)
## Post #71
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-05-31T20:08:52+00:00
- Post Title: Re: xenosaga 3 model??request

HOLY SHIT! And it works on VP2 as well!?

Do YOU have the file for it? I certainly don't. This looks a lot more finished than the one we were working on.... I have to forward this to MarioKart like NAO!

EDIT: SHITSHITSHIT This guy has cracked all three of the games I've been wanting models from... Xenosaga III, Valkyrie Profile 2, and Star Ocean 3... And there's no program link DX
## Post #72
- Username: shotgun12ga
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Apr 18, 2010 8:31 am
- Post datetime: 2010-06-01T04:07:16+00:00
- Post Title: Re: xenosaga 3 model??request

hi, is there anything like the model viewer for ffx and x-2 available for xenosaga? ty
## Post #73
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-06-01T04:47:06+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from Heroine
>
> 
I saw the article here.

There IS a program... but I doubt anyone but the author of this blog has it... and since I can only barely read Japanese and sure as hell can't speak it well, as well as a multitude of other reasons... I don't think I'll be able to get a copy of it.

Also, there's not even a contact link on there, so I've no idea how to mail him even if I could speak Japanese well, and form a logical argument as to why he should give it to us...
## Post #74
- Username: Heroine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Mar 27, 2010 4:13 pm
- Post datetime: 2010-06-01T08:01:09+00:00
- Post Title: Re: xenosaga 3 model??request

I don't have it,either.
The author said that he could email his program privately,but maybe it's hard for us to use.
I have sent a comment to him,and hope he can post it.
## Post #75
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-06-01T22:10:45+00:00
- Post Title: Re: xenosaga 3 model??request

Here is my interpertation of the mesh format at least some of it as different types/parts of meshes might have additional sections or have some sections removed:
01 01 00 01 00 C0 (2XX+1) 6C XX 80 00 00
00 00 00 00 00 00 00 00 ?? 00 00 00
{4ByteFloatVertexes(X,Y,Z) +4ByteFloatWeight}
{4ByteFloatNormalMappings(X,Y,Z) +4ByteFloatWeight}
(2XX+1) C0 YY 6E
{1ByteColorMappings(Red,Green,Blue)+80}
ZZ C0 XX 6C
{4ByteFloatWeights(X,Y,Z)}
WW C0 XX 6E
{Unknown1ByteMaps(#1,#2,#3) + FF}
00 00 00 17
Padding

I Will do more in-depth work tomorrow with an explation on how to remove the extra tristrip.
## Post #76
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-06-01T22:52:25+00:00
- Post Title: Re: xenosaga 3 model??request

Ok, since it seems, according to the Jp blog, that Xenosaga III, Valkyrie Profile 2, and and Star Ocean 3 all have similar model formats, I'd like to attempt to use the mockup program(WIP) to grab geometry from SO3... but I don't know how to find the data, when I put the disc in my drive it literally shows the disc to be empty. No hidden folders, no archives, nothing but an SLES(sp?) standard PS2 startup program file.

Does anyone know how I can find the real data?

In the old days of floppy disc games, publishers used to hide the data in between the traditional tracks and use a special program to force the drive to read that space instead of the proper tracks... that may be the case with SO3, but somehow I doubt it...

Suggestions?
## Post #77
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-06-02T00:59:16+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from Satoh
>
> Ok, since it seems, according to the Jp blog, that Xenosaga III, Valkyrie Profile 2, and and Star Ocean 3 all have similar model formats, I'd like to attempt to use the mockup program(WIP) to grab geometry from SO3... but I don't know how to find the data, when I put the disc in my drive it literally shows the disc to be empty. No hidden folders, no archives, nothing but an SLES(sp?) standard PS2 startup program file.

Does anyone know how I can find the real data?

In the old days of floppy disc games, publishers used to hide the data in between the traditional tracks and use a special program to force the drive to read that space instead of the proper tracks... that may be the case with SO3, but somehow I doubt it...

Suggestions?

Well Xenosaga 3, uses a mesh system that comes with the official  Playstation 2 Development Kit which a good third of the 40+ PS2 Games I've seen use, but the system is so flexible, that small things like padding, bones, ect are slightly different just enough that a good programmer, could probably make a program that opens up meshes for many of the games you mentioned, but would need to hard code into the program that the same section header could mean different things depending on the game.

As to getting the data off the disc, I came across similar things with the Ratchet and Clank disc. Try making an ISO image of the DVD with a good program and then you should have all the data. There is probably an easier way, but I know making an image usually works.
## Post #78
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-06-02T01:29:19+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from FurryFan
>
> Satoh wrote:Ok, since it seems, according to the Jp blog, that Xenosaga III, Valkyrie Profile 2, and and Star Ocean 3 all have similar model formats, I'd like to attempt to use the mockup program(WIP) to grab geometry from SO3... but I don't know how to find the data, when I put the disc in my drive it literally shows the disc to be empty. No hidden folders, no archives, nothing but an SLES(sp?) standard PS2 startup program file.

Does anyone know how I can find the real data?

In the old days of floppy disc games, publishers used to hide the data in between the traditional tracks and use a special program to force the drive to read that space instead of the proper tracks... that may be the case with SO3, but somehow I doubt it...

Suggestions?

Well Xenosaga 3, uses a mesh system that comes with the official  Playstation 2 Development Kit which a good third of the 40+ PS2 Games I've seen use, but the system is so flexible, that small things like padding, bones, ect are slightly different just enough that a good programmer, could probably make a program that opens up meshes for many of the games you mentioned, but would need to hard code into the program that the same section header could mean different things depending on the game.

As to getting the data off the disc, I came across similar things with the Ratchet and Clank disc. Try making an ISO image of the DVD with a good program and then you should have all the data. There is probably an easier way, but I know making an image usually works.

The only problem with that is that my hex editor has issues opening 600 meg CD ISO's... a 4 gig DVD ISO would make it shit bricks, have kittens, and spontaneously reboot, as best I can tell.
## Post #79
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-02T02:11:44+00:00
- Post Title: Re: xenosaga 3 model??request

there are iso extractors and hex editors that are good do not load the whole file into memory at one time.
## Post #80
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-06-02T09:58:26+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from FurryFan
>
> 
Well Xenosaga 3, uses a mesh system that comes with the official  Playstation 2 Development Kit which a good third of the 40+ PS2 Games I've seen use, but the system is so flexible, that small things like padding, bones, ect are slightly different just enough that a good programmer, could probably make a program that opens up meshes for many of the games you mentioned, but would need to hard code into the program that the same section header could mean different things depending on the game.

As to getting the data off the disc, I came across similar things with the Ratchet and Clank disc. Try making an ISO image of the DVD with a good program and then you should have all the data. There is probably an easier way, but I know making an image usually works.

FurryFan>do you got my pm ? 
if not are you interested on working on the format ?, i already figurate out the vertex arrays but i don't found the CONN flag in the files for rebuilding the strip !
## Post #81
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-06-02T18:28:17+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from shadowmoy
>
> FurryFan wrote:
Well Xenosaga 3, uses a mesh system that comes with the official  Playstation 2 Development Kit which a good third of the 40+ PS2 Games I've seen use, but the system is so flexible, that small things like padding, bones, ect are slightly different just enough that a good programmer, could probably make a program that opens up meshes for many of the games you mentioned, but would need to hard code into the program that the same section header could mean different things depending on the game.

As to getting the data off the disc, I came across similar things with the Ratchet and Clank disc. Try making an ISO image of the DVD with a good program and then you should have all the data. There is probably an easier way, but I know making an image usually works.

FurryFan>do you got my pm ? 
if not are you interested on working on the format ?, i already figurate out the vertex arrays but i don't found the CONN flag in the files for rebuilding the strip !

I think that maybe the some of the tristrips are removed by hardware in an analogous way  like fur/hair shaders that look very blocky on meshes until the hardware makes them look like fur.  In that case their might not be a flag, and I know several PS2 games that have similar extra tristrips.

How about you write a script, I know chrrox could easily make one  
that would remove any tristrip Edge that is only "Transversed" once,
this is hard for me to explain, but I noticed Every Single Extra tristrip material 
was by itself, meaning that each extra material was a triangle, that by definition has
three edges, but only one edge was real, and the other two phantom edges 
were only connected to the mesh by the real edge.
So this is hard to explain but I know this is right just to remove triangles that are
only "Flush" to the mesh on only one side.
Real triangles have to be "Flush" on all three sides to the mesh.
If you have any questions please ask me, I will also try to show a picture to
make my explanation easier to understand.
## Post #82
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-06-02T19:03:29+00:00
- Post Title: Re: xenosaga 3 model??request

could you develop the "transversed" once ?
## Post #83
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-06-02T20:01:11+00:00
- Post Title: Re: xenosaga 3 model??request

Transversed once, I believe means that the edge is not shared by any other triangle.

The problem with this is that the current, or at least the model parser that I have the source for, doesn't attach any triangles to eachother and uses normals to determine the shading.
## Post #84
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-06-02T20:10:44+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from Satoh
>
> Transversed once, I believe means that the edge is not shared by any other triangle.

The problem with this is that the current, or at least the model parser that I have the source for, doesn't attach any triangles to eachother and uses normals to determine the shading.

Here are images to clarify:





In the first one that triangle is connected on all sides to the rest of the mesh.

In the second one the very narrow triangle has two sides that are not flush with the mesh, they are just sort of suspended in air.
## Post #85
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-06-02T20:44:21+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from Satoh
>
> Transversed once, I believe means that the edge is not shared by any other triangle.

The problem with this is that the current, or at least the model parser that I have the source for, doesn't attach any triangles to eachother and uses normals to determine the shading.
satoh > is it from my source on darkmatter or another one ?
## Post #86
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-06-02T20:58:43+00:00
- Post Title: Re: xenosaga 3 model??request

Yes. The models I got were grouped into objects, but the triangles weren't actually connected.

Also, some faces were inverted. Still pretty cool though.

EDIT: Yes, the darkmatter.de one.
## Post #87
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-06-03T21:49:23+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from Satoh
>
> Yes. The models I got were grouped into objects, but the triangles weren't actually connected.

Also, some faces were inverted. Still pretty cool though.

EDIT: Yes, the darkmatter.de one.

An easy way to cull the extra tristrip edges is to write a script that does the following:
Definitions: #T@= the @th vertex in the #th Tristrip

Remove any edge uTv/uT(v+1)  or uTv/uT(v+2)

if and only if there is only there is exactly just one edge combination consisting of uTv/uT(v+1)  or uTv/uT(v+2)
 in the entire set of edges #T@/#T(@+1) and #T@/#T(@+2) for all # and all @
## Post #88
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-04T08:37:45+00:00
- Post Title: Re: xenosaga 3 model??request

they are not extra tri-strip edges it is vertex points in the wrong positions.
## Post #89
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-06-04T10:28:04+00:00
- Post Title: Re: xenosaga 3 model??request

I don't know what you mean chrrox?  Why would the game have incorrect vertexes in its data??
## Post #90
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-06-04T15:32:05+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from FurryFan
>
> I don't know what you mean chrrox?  Why would the game have incorrect vertexes in its data??

It could be due to some type of pointer that just happens to have working information in its structure.

It could be that (as I suspect from examining the exported models) they are left over from the jump between body parts. Basically I'm quite certain they are not supposed to be connected faces. They appear only on mesh objects that contain the same Material group, and the often appear between the fingers or both hands and link the feet to the hands etc. etc.

I'm still convinced it's all part of the stripification process.
## Post #91
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-06-09T18:12:57+00:00
- Post Title: Re: xenosaga 3 model??request

So, I vaguely remember reading at some point that Xenosaga II's models were documented and extractable, is that true or am I imagining it?
## Post #92
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-06-10T01:49:35+00:00
- Post Title: Re: xenosaga 3 model??request

The contents of this post was deleted because of possible forum rules violation.
## Post #93
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-06-10T02:11:40+00:00
- Post Title: Re: xenosaga 3 model??request

Lol, sorry, I meant XS2. I know the basic status of XS3, I've been following it.

I read that some of the tools that "worked on Xenosaga 2" were what were originally used to get the models and such out of Xenosaga 3.

What I was asking is if those tools worked on the models from XS2. Also, does anyone have a copy or a mirror of the download for those tools, I can't seem to find them(As well there are some other models in XS3 I want to extract, namely ES's and enemies.)
EDIT: Ok I have the tools... I think... but I can't figure out how the hell CRC works...
## Post #94
- Username: shotgun12ga
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Apr 18, 2010 8:31 am
- Post datetime: 2010-06-16T03:40:55+00:00
- Post Title: Re: xenosaga 3 model??request

Hi all, i hate to ask for more but i have another request if anyone can do it. could i please get some more nude shion model pics with even more angles and with her beautiful green eyes open please. much thanks guys
## Post #95
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-06-16T04:13:54+00:00
- Post Title: Re: xenosaga 3 model??request

Ok, seriously, I have to know what you are doing with them if you ask that way.

I'm assuming you don't have the game or can't get PCSX2 to run? 

If it's just a save file thing you can easily download a PS2 save and (through use of a converter) add it to a PCSX2 virtual memory card and just load up the model viewer...

The model viewer is a hell of a lot more stable than the rest of the game is for emulation. Then it's a simple matter of changing a plain text entry in a savestate from "c3shionH02" to "c3shionH07" (I'm guessing on the 07, I forget exactly which number is that model.) in any hex editor.

If I'm slightly more motivated in a while or sometime tomorrow I'll grab some... I guess.

But really... what ARE you doin' with em?
## Post #96
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2010-06-16T15:52:57+00:00
- Post Title: Re: xenosaga 3 model??request

Maaaate, seriously...that is just bloody creepy.
## Post #97
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-06-16T19:38:40+00:00
- Post Title: Re: xenosaga 3 model??request

The contents of this post was deleted because of possible forum rules violation.
## Post #98
- Username: shotgun12ga
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Apr 18, 2010 8:31 am
- Post datetime: 2010-06-16T23:50:37+00:00
- Post Title: Re: xenosaga 3 model??request

hi and thanks, those are really nice but i was wanting some full body shots with her eyes open too if u dont mind, thanks and i will leave everyone alone for a while 
ps. i need them uncensored thanks

where can i see the crying shion animation?

ok i can reach the charecter viewer, can u upload your memory card with the save already fixed up please

ok i have made a little progress all i need is an edited save state with shion nude inside the charecter viewer and i should be ok (i cant figure out the hex editing) could u please upload it, thanks
## Post #99
- Username: shotgun12ga
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Apr 18, 2010 8:31 am
- Post datetime: 2010-06-19T05:22:50+00:00
- Post Title: Re: xenosaga 3 model??request

hi everyone, i have figured out how to hex edit the save state, to everyone that helped me i say thank you.
## Post #100
- Username: Novax
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 29, 2008 5:41 pm
- Post datetime: 2010-09-01T10:17:01+00:00
- Post Title: Re: xenosaga 3 model??request

I apologize for necroing this thread, but what has become of this game and the character viewer and models? Just seemed like everyone just vanished. Be interested if this got a revival.
## Post #101
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-09-01T19:02:28+00:00
- Post Title: Re: xenosaga 3 model??request

basically we can't get out the texture format nor the uv one actually and lot of data is unknown in the file so yup this time we vanished
## Post #102
- Username: Novax
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 29, 2008 5:41 pm
- Post datetime: 2010-09-02T08:34:49+00:00
- Post Title: Re: xenosaga 3 model??request

But can you get the mesh/model out in one piece. If so, can you please tell me your secret? I currently been using methods that end up breaking the long hair of kos-mos. I would like a way that doesn't do that.
## Post #103
- Username: Novax
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 29, 2008 5:41 pm
- Post datetime: 2010-09-30T16:13:00+00:00
- Post Title: Re: xenosaga 3 model??request

bumping again to revive this series. I've gotten kos-mos's model(s) through other means. I was only hoping someone had discovered a better method. I see that someone can easily extract the textures so they aren't miscolored in RGB values. Anywho, let me know how you are all doing.
## Post #104
- Username: shotgun12ga
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Apr 18, 2010 8:31 am
- Post datetime: 2010-11-04T18:49:44+00:00
- Post Title: Re: xenosaga 3 model??request

Sorry to bring this up again but was interested to know if anything new has happened or any progress has been made, and what became of the codebreaker code.
## Post #105
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2010-11-07T17:19:33+00:00
- Post Title: Re: xenosaga 3 model??request

From working on a few other ps2 games, i have read up on a few things, and have some more information that makes some of the previously unknown data make a bit more sense.  Will have to see what i can make of things now taking that into account.
## Post #106
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-11-09T10:50:24+00:00
- Post Title: Re: xenosaga 3 model??request

glad to see you are still working on it rev'
## Post #107
- Username: aramaki
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun May 23, 2010 5:47 am
- Post datetime: 2010-12-19T03:26:35+00:00
- Post Title: Re: xenosaga 3 model??request

i'd forgotten about this thread... i thought it was a dead end.  glad to see some progress is being made.  
i'm wondering, how much will be possible to modify?  i'm assuming model swapping is possible, but would it be possible to extract, edit (either just texture, or possibly wire frame) and then reinsert the model back in the iso?
## Post #108
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-01-04T18:46:36+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from chrrox
>
> you need to have 2 views of the exact same frame capture using 3d ripper dx.
the only way to do this is in the model viewer mode.
take 1 capture straight on then take one side profile snapshot.
then there is a max script you must run on the 2 files that will solve for the depth and it will make the image 3d again.
I can't remember the name of the script off the top oif my head if I can dig it up ill post it.

I surf by the net by 4 years and i never found this script or death link of this script, the true its this scripts doesnt exist bro.
## Post #109
- Username: Akumart
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 15, 2011 12:45 pm
- Post datetime: 2011-02-15T04:48:30+00:00
- Post Title: Re: xenosaga 3 model??request

Can anyone post images of Shion's First costume for Xeno 3 (The one where she was with Miyuki and Canaan) XD
## Post #110
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-09-05T01:59:10+00:00
- Post Title: Re: xenosaga 3 model??request

did anyone have success in converting the model with proper faces..
## Post #111
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-09-05T02:02:43+00:00
- Post Title: Re: xenosaga 3 model??request

Well in this forum they did manage to rip the models with emulator successfully 

[http://godsibb.net/forums/index.php?/to ... -download/](http://godsibb.net/forums/index.php?/topic/1264-xenosaga-models-import-and-download/)
## Post #112
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-09-05T02:06:41+00:00
- Post Title: Re: xenosaga 3 model??request

hmm, thats probably done using the 3dripperDX method I released there a couple of years ago..

what I'm trying to do is get direct model conversion from the files...
## Post #113
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-09-05T02:17:26+00:00
- Post Title: Re: xenosaga 3 model??request

I don't know about that, but that sure will be more nice than ripping with 3dvia , or 3d ripper.
## Post #114
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-09-05T03:31:32+00:00
- Post Title: Re: xenosaga 3 model??request

that person's rips are bad, I posted about the problems I had with it

> I inspected the Momo Swimsuit rip and found the following problems:
>
> 
>
> a.) Rip is stored in 3dmax format which also requires collada drivers (rips should have been outputed to wavefront OBJ)
>
> b.) Model was not in its neutral pose aka (Tpose)
>
> c.) Rip appears to have damaged texture coordinates (Your Rip) (Good Rip)
>
> d.) MeshSmooth doesnt work too well on tris models
## Post #115
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-09-05T03:49:41+00:00
- Post Title: Re: xenosaga 3 model??request

Yeah I  thought so, she said that she doesn't need it in t-pose since she says it's harder for her to put bones since the foot are too close to each other, so she just rips them in their poses.
## Post #116
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-05T04:18:33+00:00
- Post Title: Re: xenosaga 3 model??request

Thank you for reply, mariokart64n.

[This maxscript](http://www.fileserve.com/file/sKzr7cF/) is not complete and lost UV.
(I appreciate to the script author!)
And, there is no method of taking out the texture.

Though he seems to have succeeded..
[-his blog-](http://blogs.yahoo.co.jp/osaka_0705)

I asked a question to him.
He was said, "I did not want to teach to the beggar".  
After that, He deleted the post. 
[-way backed post-](http://megalodon.jp/2011-0720-0326-42/blogs.yahoo.co.jp/osaka_0705/60087913.html)
## Post #117
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-09-05T07:48:03+00:00
- Post Title: Re: xenosaga 3 model??request

thats the maxscript codeman made, it suffers from improper face import.

but thanks for finding a web backup of Osaka's blog. the image there explains why the UVs looked like they were scaled wrong....


the answer is that they are not scaled wrong.. actually they are correct for the texture that I don't have lol 

crappy, if only we knew how that Osaka guy read the faces properly, then we would have xenosaga models.
## Post #118
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-05T08:29:27+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from mariokart64n
>
> thats the maxscript codeman made, it suffers from improper face import.
That was it! Many Thanks, codeman!!

I think he used Textures Swizzler made himself.

And he wrote, he could convert model object, but couldn't export UV data yet.
Maybe He didn't succeed perhaps because the continued report doesn't exist.

I place my last glimmer of hope on you, mariokart64n!
(However, That I hope it doesn't become your load.)
## Post #119
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-09-05T12:41:46+00:00
- Post Title: Re: xenosaga 3 model??request

The mesh format is actual rather simple now that i have read up on vif tags during my KH2 plugin work.  i just still haven't gotten around to applying the code to this format yet (as well as many other ps2 games that use it....just about all of them listed at ps23dformat.wikispaces.com do).  Don't think i ever converted my code from the darkmatter forums into anything, but i will hopefully have a much better version with this new knowledge,....once i get to it.  *sigh* so much to do, so little time, heh.

Though i explained a little bit about the vif tags in another thread here if it will help someone in the meantime.
## Post #120
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-09-05T13:38:44+00:00
- Post Title: Re: xenosaga 3 model??request

so that thing I thought was an ID, is actually the face strip pattern?

01 01 00 01

thanks for the heads up, this is soo awesome!! ^,^
[viewtopic.php?p=52244#p52244](http://forum.xentax.com/viewtopic.php?p=52244#p52244)
## Post #121
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-09-05T16:28:44+00:00
- Post Title: Re: xenosaga 3 model??request

Well, they specify how the data in the unpack blocks:

```
## C0 ?? 7*

```

are handled.

The ordering and contents of the block are specific to each developer.  So you would have to determine that visually, as has already been done.  But even then there are times when the data will not be entirely complete until it is fully unpacked due to things like masking, where data can be partially written between multiple unpack blocks.

For formats that are nicely structured for us, a lot of this information can be glossed over, because in those cases even in the packed form, it still resembles the standard in order list of values we are used to.  Simply decipher the counts from the commands and process normally.  But if the developer decided to get more creative with their use of the commands, it can get far more interesting.

The ## ## 00 01 specifiers, basically tell how often to read and write elements within each unpack block.  So you can essentially read data and write it to memory one after the other, or every other line, etc.

The memory in the vu on the ps2 is aligned to 16-byte boundaries, and the unpack commands write this data out 16 bytes (four 32-bit values) at a time, using masking to specify which, if any, of the "x", "y", "z", or "w" data should be written each time.

This allows for either writing data consecutively one after the other, or interleaving the data between multiple unpack operations.

For example, lets say you have 10 vertices, normals, and uvs.

Using:

```

```


This basically says for every read of the data, perform a write to memory and advance to the next data to read, and address to write to.

You could write the vertices to address 0x0000, and they would appear one after the other, causing the normals to have to be written to address 0x00A0, and the uvs need to be written at 0x0140, to avoid overwriting previously written data.

But these commands can also be used to write the data interleaved in a way the the order is [vert1, norm1, uv1, vert2, norm2, uv2, ...] using:

```

```


Which would essentially cause the order of operations to now be: read, write, skip, skip, read, write, skip, skip, etc.  So for every read/write, it would then skip two memory locations (0x20 bytes), and perform the operations again.

This would cause the start addresses of the write operations to be different as well.  The vertices could still start at 0x0000, but the normals would now start at 0x0010, and the uvs at 0x0020.  Because of the skipping the space for the normals and uvs, would be untouched during the vertex unpacking, in the same manner when writing the normals, the uv and next vertex value would be skipped over, and so.

This can also be used for he inverse of writing more data than you have read, i.e. reading data and writing it multiple times, and various other combinations.

To top it all of if that wasn't deep enough, masking can change which values are even written in the first place, even being able to replace masked out values with constants in other registers.  So you could write to the "x" and "y" locations in one unpack command, masking the "z" and "w" so that they will be untouched, and use another unpack command with the masking reverse to write only to the "z" and "w" areas with completely different data.  Or the more common case of writing out the xyz position of a 3d vector, and masking the "w" location so that a constant value of 1.0 is written.

There are a lot of things possible with the ways this works, and unfortunately even with a way to unpack them the way the ps2 does, they way they are order and the data contained within the commands are completely up to the developer to choose for each game.  The values don't even have to be geometry related, you can pack the entire header of another self-contained format within these commands, where after unpacking you have a completely different format to parse.

Whew, sorry for the long description...while not xenosaga specific, its the main reason why there is still a little more work involved than simply unpacking the data in a lot of cases.  Will see if i can post something more useful, heh.
## Post #122
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-09-05T17:29:45+00:00
- Post Title: Re: xenosaga 3 model??request

wow thats very interesting...

okay soo basically before  importing the strip I have to read everything between two VIF command blocks ex. "01 01 00 01" .. I assume the command is closed by an empty space "00 00 00 00"

cause with each new VIF tag in between it'll add, or mask certain parts of my memory or the array I'm storing the face list to??

if that's right then the reason for the bad faces before was that we weren't taking in account of all the VIF tags before we read a new VIF command  "01 01 00 01"
## Post #123
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-09-05T18:34:28+00:00
- Post Title: Re: xenosaga 3 model??request

The separation for this for mat would be 00 00 00 17 which is the MSCNT command.  This is one of the commands that starts execution of microprograms on the VU processor.

Has been a while since i have looked at the format taking these things into account, but if i recall correctly there should be a header section, followed by a number of data sections, each full section starting with 01 01 00 01 and terminated by 00 00 00 17 commands (or a variant therof).

Will have to see how this all relates now that i know how it should work.  SHould be able to find more counts and data sizes hopefully, as i now know that they are usually specified in terms of 16-byte chunks instead of the number of bytes, so the sizes will often be the full size divided by 16, if specified in quad word count format as the ps2 calls it.
## Post #124
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-09-06T06:38:18+00:00
- Post Title: Re: xenosaga 3 model??request

I poked around in the emu and found that if this one byte was even, the face was to be draw, but if it was odd, then you had to skip it... really nutty cause the hide this in the exponent of the 32bit float O_O ??guess thats what you meant by bit masking?
## Post #125
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-06T07:30:12+00:00
- Post Title: Re: xenosaga 3 model??request

Hi, mariokart64n.
Could your tool convert *.wpn files?
I think it is same structure that *.chr files.

[-*.wpn samples at "\mdl\wpn\"-](http://www.fileserve.com/file/VH35V6H/)
## Post #126
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-09-06T08:29:47+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from porimac
>
> Hi, mariokart64n.
Could your tool convert *.wpn files?
I think it is same structure that *.chr files.

-*.wpn samples at "\mdl\wpn\"-
just change the name *.wpn to *.chr
## Post #127
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-06T11:51:18+00:00
- Post Title: Re: xenosaga 3 model??request

> just change the name *.wpn to *.chr
Oops, Sorry for my silly post.
I'm waiting for mario in feelings like a kid who looks forward to Santa Claus so.
## Post #128
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-09-06T20:49:39+00:00
- Post Title: Re: xenosaga 3 model??request

Apparently some were not happy that I did not supply more details on the findings. I just want to say that I was only hesitant because of the over exposure and abuse I've been seeing alot of ripped 3d models since the release of tools such as noesis and umodel. I'm sure most know of what I'm talking about.

anyway it was not my intention to withhold any information, I didn't post the script last night because its buggy as hell its far from release ready. reguardless I'm posting the script and the spec details in hope someone with more programing skills can take over the project.

here's the maxscript: [http://pastebin.com/Xt8jH2PF](http://pastebin.com/Xt8jH2PF)
the script was modified from a script that chrrox and codeman wrote last year (someone posted the same script above)

format specs..

the VIFtag info was already supply up top, and the PXY header is straight forward for any programmer hacker. so I'll only touch basis with the 2 problems that plagued the previous attempts
1. UVs
2. Faces


when vertex data is defined, its defined in two loops*count
the first loops defines the x,y,z of the position data and then the U of the texture coordinate.
the second loop contains the x,y,x of the vertex normal data, then the V of the texture coordinate.

its weird how they did that but pretty apparent when you look at it.

then you just generate for faces in a strip pattern, but you need a draw or don't draw flag to tell you when to restart the strip.

as I said last night they store this bit in the V of the texture coordinate
I just read the first byte of where the V float would be, then read the 1st bit... if the files even the bit should be 0 i think, if its an odd number the bits going to be 1.. using that I was able to proper draw the faces, with working UVs.

please forgive my sloppy interpretation of the format, i'm just a hobbyst hacker. please refer to the maxscript above if you want more details on how to read the geometry.
## Post #129
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-09-06T21:52:55+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from mariokart64n
>
> I've been seeing of ripped 3d models since the release of tools such as noesis and umodel. I'm sure most know of what I'm talking about.

Im kinda new and dont know.  What's been going on?
## Post #130
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-07T05:06:35+00:00
- Post Title: Re: xenosaga 3 model??request

Dear mariokart64n.
I can't tell you how thankful I am.
I would like to help you by something, But it seems that is difficult for me as long as it saw although..
## Post #131
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-09-07T20:56:26+00:00
- Post Title: Re: xenosaga 3 model??request

not that this matters much, but I fixed the face directions in the script above. thanks to revel8n for pointing out my mistake.. forgot to reset the direction on each new strip [fixed]
[http://pastebin.com/yFqzv6L5](http://pastebin.com/yFqzv6L5)
## Post #132
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-08T12:06:48+00:00
- Post Title: Re: xenosaga 3 model??request

Thanks, mario!! I got it!
## Post #133
- Username: pao com ovo
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-10T11:27:40+00:00
- Post Title: Re: xenosaga 3 model??request

Here is a xenosaga 3 fast import script for max.
Ill work on bones and weights next it does not look that hard to add.
[Xenosaga3(chrrox).rar](https://xentaxbackup.github.io/file/4702_Xenosaga3(chrrox).rar)
## Post #134
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-10T11:45:27+00:00
- Post Title: Re: xenosaga 3 model??request

> Ill work on bones and weights next it does not look that hard to add.
Thank you so much, chrrox!
You are truly awesome...
## Post #135
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-09-10T14:25:43+00:00
- Post Title: Re: xenosaga 3 model??request

Can someone upload kosmos textures from the 2 or 3 models from the game pls? I'll be gratefull
## Post #136
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-10T14:53:41+00:00
- Post Title: Re: xenosaga 3 model??request

The contents of this post was deleted because of possible forum rules violation.
## Post #137
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-09-12T01:43:55+00:00
- Post Title: Re: xenosaga 3 model??request

With some tweaking  it looks like Map files can be extracted in a similar fashion. :O
## Post #138
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-12T02:58:47+00:00
- Post Title: Re: xenosaga 3 model??request

the stages look compressed.
## Post #139
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-09-12T03:03:48+00:00
- Post Title: Re: xenosaga 3 model??request

Will this be supported by noesis once bones and weights are done?
## Post #140
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-09-12T03:37:47+00:00
- Post Title: Re: xenosaga 3 model??request

The contents of this post was deleted because of possible forum rules violation.
## Post #141
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-09-12T05:49:51+00:00
- Post Title: Re: xenosaga 3 model??request

I got the idea from YoungMark when he made the suggestion of renaming the files in question <.wpn> to .chr for the script~ So i tried doing so with the .map files ^___^;;;

this is what i came up with~

<i hid some polygons in order to show what i'm trying to focus on~>









it does have a basic shape and is resembling the bridge of the Elsa~ but it is butchered with the polygons everywhere and what not. ._.;;;

Although i am not sure if this is helpful or not... i just thought it was kinda cool XD!!
## Post #142
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-12T06:23:57+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from DOTAPRINCE
>
> 
Will this be supported by noesis once bones and weights are done?
chrrox said, "Ill work on bones and weights next it does not look that hard to add."
We cannot expect an instant result. Be patient.  

> Reply from maniacoloco
>
> 
does the second disc have the same models?
I think There model files is not much to choose between the disk 1/2.
## Post #143
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-09-12T11:01:28+00:00
- Post Title: Re: xenosaga 3 model??request

I was just asking for noesis support
## Post #144
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-12T14:43:22+00:00
- Post Title: Re: xenosaga 3 model??request

I think require find a way to extract bones by someone.  
Otherwise Noesis will not support.
## Post #145
- Username: Nathen41
- Rank: advanced
- Number of posts: 43
- Joined date: Sun Apr 18, 2010 3:35 pm
- Post datetime: 2011-09-14T05:01:17+00:00
- Post Title: Re: xenosaga 3 model??request

For Ripping large objects like the durandal and such~ reworking the textures can be a pain in the lower back. Soooooo i dont know if any of you know of this or not but XnView has the option to Batch swop the RGBs to which ever order you want~ the program is free~ 

[http://www.xnview.com/en/index.html](http://www.xnview.com/en/index.html) 

once installed just navigate to the textures, highlight them all, right click, batch processing, Select output folder/format, then click the top tab "transformations", Map > Swap component, RGB > BGR, then click the "Go" button at the very bottom left~ and there you go! ^.^/ i hope this helps
## Post #146
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-14T18:27:24+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from porimac
>
> I think require find a way to extract bones by someone.  
Otherwise Noesis will not support.
I don't think Noesis requires bones to import or export, for instance, OBJ doesn't even have bone capabilities and Noesis can easily open and export them fine.

It should be entirely possible to make a plugin that imports and exports models in their bind pose and treat them as solid objects. It should be possible because Xenosaga models actually -have- bindposes. Some models, particularly PSX models, don't have bindposes, hence why it is imperative to have bones for them. With Xenosaga it is not the case.

I originally planned on hacking together a plugin from the maxscript file, but....I can't make heads or tails of maxscript.. it isn't what I was expecting.

My point is, a xenosaga plugin should be completely possible for noesis, it can be revised once bones are understood.

Also, can I get a list of the tools available for Xenosaga stuff we know how to open, extract, export, whatever? In one place?

Obviously we can get textures somehow, and we can extract the models and such, but I've long since lost my tools, due to three computer breakdowns/migrations, and I need to know what new capabilities we have now.
## Post #147
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-15T20:19:49+00:00
- Post Title: Re: xenosaga 3 model??request

The contents of this post was deleted because of possible forum rules violation.
## Post #148
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-16T23:19:00+00:00
- Post Title: Re: xenosaga 3 model??request

Much appreciated. This extracts images, CHR files and such?

I assumed by now we had more tools for doing things.
## Post #149
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-17T00:30:00+00:00
- Post Title: Re: xenosaga 3 model??request

> This extracts images, CHR files and such?
It tool is extract some files from gamedisk.

CHR contains PXY, TXY, XHR files.
WPN contains PXY, TXY, XHR files.
MAP contains (compressed?)PXY, TXY, files. 
PXY => models, UVs. but cannot extract bones yet. Maybe work on by mariokart64n, chrrox.
TXY => Textures. can not quite convert. (I am confident that you can convert it.  )
XHR => ???
## Post #150
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-17T03:33:44+00:00
- Post Title: Re: xenosaga 3 model??request

Thank you for the information, porimac.

The PDF in the file you linked says to unpack X3.11 X3.12 and X3.13, but the PDF is explaining how to make a Japanese/English hack.

Are the models and textures in those files, or are they in X3.01, X3.02, X3.10, or some other file?

I'm following the instructions for now, but it is taking a very long time to unpack, and I'm not sure if it is finished yet... So far, I do not see the CHR/WPN/MAP files yet.

Thank you again, you have been very helpful.
## Post #151
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-17T04:23:57+00:00
- Post Title: Re: xenosaga 3 model??request

> I'm following the instructions for now, but it is taking a very long time to unpack, and I'm not sure if it is finished yet... So far, I do not see the CHR/WPN/MAP files yet.
The model and texture files including X3.01 and X3.02.
The X3.00 files are tables that lists the files in the packs.

How to extract
-------------------------------------------------------
Copy the X3.00, X3.01, X3.02 from gamedisk on you hard drive.
Open a command line
Type : copy /b X3.01 + X3.02 X30.big
       This will join the two files into a big file X30.big.
Type : xeno23lbae X3.00 Lba0.txt
       This decrypts the table into a usable format.
Type : xenounpack Lba0.txt X30.big
       This still takes a little while. It unpacks the pack to a folder UNPACKED using the decrypted table.
-------------------------------------------------------

the chr files is located in the 'UNPACKED\mdl' folder that was extracted.
## Post #152
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-17T04:57:29+00:00
- Post Title: Re: xenosaga 3 model??request

I see. That must be why my models won't load; I unpacked the wrong files.

What a waste of 3 hours =p

You have my utmost gratitude!
## Post #153
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-09-17T07:37:19+00:00
- Post Title: Re: xenosaga 3 model??request

The contents of this post was deleted because of possible forum rules violation.
## Post #154
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-17T09:41:31+00:00
- Post Title: Re: xenosaga 3 model??request

[XS1] the xtx(not compressed) contained in bin file looks the same as Xenossaga3 txy at least. 


'MagicCarpetCome'...is it a magicword?
## Post #155
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-17T13:58:24+00:00
- Post Title: Re: xenosaga 3 model??request

Xenosaga 3 contains a number of XTX files as well, a large number of them appear to be raw RGBA32 formatted data, they are in the KAO folder, and as one might expect from that name, they are faces; Portraits used during speech.

Am I correct in thinking there's no tool for decrypting TXY yet? I'm pretty bad at knowing what to do with a format when it isn't raw... I can tell there IS texture data in the XS3 models, but I don't have a clue what to do with it...

EDIT: Also certain models, c3momo01.CHR for instance, don't import to max properly... and instead appear as erroneous lines extending from the center, with no known length... and the odd polygon...
## Post #156
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-17T17:20:53+00:00
- Post Title: Re: xenosaga 3 model??request

> Xenosaga 3 contains a number of XTX files as well, a large number of them appear to be raw RGBA32 formatted data, they are in the KAO folder, and as one might expect from that name, they are faces; Portraits used during speech.
Yep. It was easy to convert.


> Am I correct in thinking there's no tool for decrypting TXY yet?
Right. the textures are swizzled altogether.
Therefore, we are looking for the decryption method. 
[The one Japanese guy](http://megalodon.jp/2011-0720-0326-42/blogs.yahoo.co.jp/osaka_0705/60087913.html) succeeded in conversion somewhile. 
However, his method was lost.
## Post #157
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-18T01:23:38+00:00
- Post Title: Re: xenosaga 3 model??request

the textures in xenosaga are the same formats used in this game
[viewtopic.php?f=18&t=2640](http://forum.xentax.com/viewtopic.php?f=18&t=2640)
just different headers.
## Post #158
- Username: pao com ovo
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-18T23:53:25+00:00
- Post Title: Re: xenosaga 3 model??request

Here is  a script to support low polly models in xenosaga also. i don't have any textures to test the uv's.
[Xenosaga3(chrrox).rar](https://xentaxbackup.github.io/file/4718_Xenosaga3(chrrox).rar)
## Post #159
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-19T01:51:20+00:00
- Post Title: Re: xenosaga 3 model??request

With the low def models there seems to be an issue with objects being placed incorrectly.
C3shion99 has her coat up around her head, and c3momo01 has her head inside her chest... Also the low def models are massively upscaled, and the high def models are massively downscaled.

Unfortunately I still can't figure out how to get textures, even with the link you provided about them, so I too was unable to test UV's.

However, as the low def models no longer force Max to have a fit and stop displaying things properly, I'd say it's certainly  something I'll keep on hand... as well as the previous version.

I was attempting to upload the models I had notable trouble with, in case my files are different somehow, but Xentax is having a fit.
## Post #160
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-09-19T18:28:57+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from chrrox
>
> the textures in xenosaga are the same formats used in this game
viewtopic.php?f=18&t=2640
just different headers.
Hmm, It is difficult for me...how can swizzle picture with that code? 
I regard my incompetence as deplorable.
## Post #161
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-20T03:20:18+00:00
- Post Title: Re: xenosaga 3 model??request

Well, for swizzles, I have no idea how to even implement the code that's in the other thread, I don't even know what language it's supposed to be. It looks like it may be C# but there are a few things I've never seen in code, like asterisks in the arguments for a function definition... So I couldn't add it to a noesis plugin if I tried. I'm still looking over the maxscript and trying to get my barings so I might transcribe it to noesis at some point, but I'm not there yet. Starting to get a vague grasp on the syntax though.

As for the KAO files I did write myself a plugin for them, and it uses data from the header to work, rather than assumed dimensions and such, so it should be extendable later for the few swizzled XTX's in the MNU folder and such.

I pasted the code for that plugin here:

[viewtopic.php?f=33&t=4582&p=59773#p59773](http://forum.xentax.com/viewtopic.php?f=33&t=4582&p=59773#p59773)

I realize everyone currently here probably has those decoded already, but for new arrivals, it may be useful, idunno... Also, as a note, it's the first plugin I've ever written that doesn't have any functional errors AND isn't horribly sloppy with hundreds of failed code snippets left in! Woo! I'm proud of my mediocre achievement!

I did notice while I was looking at the swizzled TXY's that they are in fact 8bpp. I discovered it using GGD though, so I don't know where in the headers that info is located, or what it looks like. I can confirm there are several 16x16 32bit palette squares that are positioned throughout the files, but are only apparent with the entire file is viewed at the right dimensions. The palettes seem to be proper colors all the way through, but are also partially swizzled, in that they may not be ordered correctly... (Twiddled? These terms are too arbitrary for me at the moment...) I discovered these looking at c3virhelm00.txy, which is floating naked in the NPC folder, as opposed to being part of a CHR archive.

Maybe this is useful info, maybe not, but I didn't see any references to it so I figured I'd let you guys know. I suck at this, but I'm trying.
## Post #162
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-09-27T01:02:16+00:00
- Post Title: Re: xenosaga 3 model??request

yay i'm soo happy revel8n was able to solve the bone ids, so we should have fully skinned meshes now.. well hopefully

BIG THANKS TO CHRROX, REVEL8N, and MRADULT

xenosagas been an old ps2 favorite, i'm really glad to be able to play with the models ^.^

anyway heres the scripts;


 Desktop.zip
(11.46 KiB) Downloaded 168 times



I'm also planning to write up the format spec on this, but I was wondering if xentax had some sort of like wiki I can toss that on?
## Post #163
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-27T02:48:27+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from mariokart64n
>
> 
I'm also planning to write up the format spec on this, but I was wondering if xentax had some sort of like wiki I can toss that on?

Why yes there is! 
[http://wiki.xentax.com/index.php/Game_F ... at_Central](http://wiki.xentax.com/index.php/Game_File_Format_Central)

I'm not sure if you require access rights to post to it however.

I wish I understood maxscript! I'd be trying to transcribe this into a Noesis plugin.

HOLYHELL! Does this work on textures too?? I saw that Abel pic in the Noesis thread! Why oh why do I have to be so busy right when this awesome stuff is happening and can't play with it!
## Post #164
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-09-27T03:45:45+00:00
- Post Title: Re: xenosaga 3 model??request

mradult posted a py script to convert the textures, its not apart of this script.

you can find that in his noesis topic
## Post #165
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-27T04:10:12+00:00
- Post Title: Re: xenosaga 3 model??request

I see, so it's not a fixed version of that script then, just a TXY that happens to work.

That particular script may not give you a proper texture all the time, so be aware....My fault for not supplying more files when he was looking over it... This pretty much leaves it to me to figure out how the script works and more importantly how it doesn't work, and try to fix it... but it's certainly better than the texture script that didn't work that we didn't have before to not view textures, so there is that.
## Post #166
- Username: sopyer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 06, 2011 11:42 pm
- Post datetime: 2011-11-06T15:55:51+00:00
- Post Title: Re: xenosaga 3 model??request

Hi guys, I would like to research xenosaga 3D model and texture formats, can you share all available information? Also how is possible to extract files from iso image? It seems a lot of links are broken and pieces scaterred all around a lot of places. I am novice to working with ps2 games, though in the past I have reverse engineered few archive formats. I am able to program in python and C/C++, though even information about data structures would be interesting and even preferred.

Thank you in advance.
## Post #167
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-11-19T12:34:41+00:00
- Post Title: Re: xenosaga 3 model??request

i thought the info was all in this tread.?

the extractor came from alucard.com?

but the author did not provide source, only comments about the structure using encryption. I wasn't able to devise my own dumper, so theres something weird going on
as for the model format, codeman did the core of the hacking, and he's posted his source somewhere here. then I finished off the format by figuring out the masking bit for face re-setting and bone weights. mr adult completed the xenosaga2 texture format in a seperate topic, and provided a python script compatible with his noesis application. I'm not sure if he looked at the xenosaga3 2d format, but that still needs to be cracked.

lastly xenosaga1 is compressed, revelation provided a hex script to decrypt I think? but I never got around to testing it. you need a certain program to run it. and I've since lost it 

Sorry the info is soo scattered.. the progress stretches over several years
## Post #168
- Username: sopyer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 06, 2011 11:42 pm
- Post datetime: 2011-11-22T11:47:26+00:00
- Post Title: Re: xenosaga 3 model??request

@mariokart64n The problem is many links no longer work. And info is pretty scattered across a thread and assumes a lot of upfront knowledge, which I lack. First of all I need to extract files to be able to proceed, but domain name you mentioned - alucard.com seems unrelated, possibly it was abandoned long time ago. So first question - how should I extract all those files?
## Post #169
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-11-22T23:58:12+00:00
- Post Title: Re: xenosaga 3 model??request

4th page, chrrox posts tools.. link looks valid?
[viewtopic.php?p=37200#p37200](http://forum.xentax.com/viewtopic.php?p=37200#p37200)
## Post #170
- Username: sopyer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 06, 2011 11:42 pm
- Post datetime: 2011-11-25T20:58:32+00:00
- Post Title: Re: xenosaga 3 model??request

@mariokart64n thanks it worked just fine. And using generated files I have even been able to understand archive format in general. Maybe will write my own extractor as an exercise. I'll try to figure now how to extract models now. Hope you or someone  else will help me if I stuck.
## Post #171
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-11-26T21:30:56+00:00
- Post Title: Re: xenosaga 3 model??request

glad to hear, if you have msn my contact info is in my xentax profile. I'll be glad to help out with the format... I was disappointed with no bone parenting, so didn't take it past that. since the textures and how to link them was over my head aswell.
## Post #172
- Username: gx9999dx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 20, 2010 7:42 am
- Post datetime: 2012-02-16T02:16:54+00:00
- Post Title: Re: xenosaga 3 model??request

Hi guys, could anybody re-upload all the tools required to rip the model from xeno3?

All the links seem broken.

Thank you very much!
## Post #173
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2012-03-21T07:04:01+00:00
- Post Title: Re: xenosaga 3 model??request

XTX resolve the problem by osaka_0705. 
[http://blogs.yahoo.co.jp/osaka_0705/64742600.html](http://blogs.yahoo.co.jp/osaka_0705/64742600.html)
[http://blogs.yahoo.co.jp/osaka_0705/64738434.html](http://blogs.yahoo.co.jp/osaka_0705/64738434.html)
## Post #174
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-03-28T19:02:10+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from youngmark
>
> XTX resolve the problem by osaka_0705. 
http://blogs.yahoo.co.jp/osaka_0705/64742600.html
http://blogs.yahoo.co.jp/osaka_0705/64738434.html

Lol I was gonna ask for that.

Can someone make a plugin for noesis with that info? I can provide examples of ep III.

See ya!
## Post #175
- Username: Novax
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 29, 2008 5:41 pm
- Post datetime: 2012-04-02T11:49:10+00:00
- Post Title: Re: xenosaga 3 model??request

Could someone explain what the link to the Japanese site does exactly? I would love to rip using this method, but don't understand a thing.
## Post #176
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-04-02T18:53:03+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from Novax
>
> Could someone explain what the link to the Japanese site does exactly? I would love to rip using this method, but don't understand a thing.

It explains the texture format.

The best thing I can do is to put a link with google translation, but the translation is not too accurate.

[http://translate.google.com.mx/translat ... 42600.html](http://translate.google.com.mx/translate?hl=es&sl=ja&tl=en&u=http%3A%2F%2Fblogs.yahoo.co.jp%2Fosaka_0705%2F64742600.html)

[http://translate.google.com.mx/translat ... 38434.html](http://translate.google.com.mx/translate?hl=es&sl=ja&tl=en&u=http%3A%2F%2Fblogs.yahoo.co.jp%2Fosaka_0705%2F64738434.html)
## Post #177
- Username: Novax
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 29, 2008 5:41 pm
- Post datetime: 2012-04-02T21:46:59+00:00
- Post Title: Re: xenosaga 3 model??request

That's a shame. I thought it was a way to extract the models easily
## Post #178
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-02T22:33:14+00:00
- Post Title: Re: xenosaga 3 model??request

he is just talking about how the images are swizzled and some info about the alpha channels in the images.
## Post #179
- Username: Novax
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 29, 2008 5:41 pm
- Post datetime: 2012-04-03T00:08:02+00:00
- Post Title: Re: xenosaga 3 model??request

Stil, would be nice to have an easy method to extract/rip the models. Only way I know is complicated and a pain to fix them even after that.
## Post #180
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-04-03T01:16:32+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from Novax
>
> Stil, would be nice to have an easy method to extract/rip the models. Only way I know is complicated and a pain to fix them even after that.

You can have the models with Mario script, at least it works with xenosaga 2 and 3. The problem comes with textures in xenosaga 3, the script that rich released only works with xenosaga 2.
## Post #181
- Username: Novax
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 29, 2008 5:41 pm
- Post datetime: 2012-04-03T13:12:49+00:00
- Post Title: Re: xenosaga 3 model??request

What script may this be? Does it rip the models easily along with their UV maps and perhaps textures? I apologize if I come off rudely, just trying to fully understand.
## Post #182
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-04-03T18:53:00+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from Novax
>
> What script may this be? Does it rip the models easily along with their UV maps and perhaps textures? I apologize if I come off rudely, just trying to fully understand.

Ok, check this:

[http://www.youtube.com/watch?v=sh2mdUBc ... LjQWzI0XU=](http://www.youtube.com/watch?v=sh2mdUBcMsI&feature=plcp&context=C48fec94VDvjVQa1PpcFOMmhzNlhRgVoRxr8bOssnOyVLjQWzI0XU=)
[http://www.youtube.com/watch?v=ebKQiztb ... _fDfMWNmI=](http://www.youtube.com/watch?v=ebKQiztbXqo&feature=plcp&context=C4a6b15cVDvjVQa1PpcFOMmhzNlhRgVs02FsGxT4PG0Y_fDfMWNmI=)

And this:

[http://godsibb.net/forums/index.php?/to ... __p__69487](http://godsibb.net/forums/index.php?/topic/1264-xenosaga-models-import-and-download/page__view__findpost__p__69487)

And this is the noesis python code plugin to get xenosaga 2 textures by mr adults:

```
def registerNoesisTypes():
   handle = noesis.register("Xenosaga TXY Image", ".txy")
   noesis.setHandlerTypeCheck(handle, txyCheckType)
   noesis.setHandlerLoadRGBA(handle, txyLoadRGBA)
   return 1

def txyGetImageCut(texPage, pageWidth, pageHeight, ofsX, ofsY, width, height):
   r = bytes()
   for i in range(0, pageHeight):
      imgOfs = ofsY*pageWidth + i*pageWidth + ofsX
      r += texPage[imgOfs:imgOfs+width]
   return r

def txyRetile8(pix, pixW, pixH):
   dst = bytearray(pixW*pixH)
   for y in range(0, pixH):
      for x in range(0, pixW):
         blockOfs = (y & ~15)*pixW + (x & ~15)*2
         sw = (((y+2)>>2) & 1) * 4
         ofsY = (((y & ~3)>>1) + (y & 1)) & 7
         colOfs = ofsY*pixW*2 + ((x+sw) & 7) * 4
         ofsX = ((y>>1) & 1) + ((x>>2) & 2)
         dst[blockOfs+colOfs+ofsX] = pix[y*pixW + x];
   return dst

class TXYFile:
   def __init__(self, reader):
      self.reader = reader

   def loadImageInfo(self):
      reader = self.reader
      if reader.dataSize <= 20:
         return 0
      id = reader.readInt()
      ver = reader.readInt()
      fsize = reader.readInt()
      if id != 0x797874 or ver != 1 or fsize > reader.dataSize:
         return 0
      reader.seek(16, NOESEEK_ABS)
      self.infoOfs = reader.readInt()
      if self.infoOfs <= 0 or self.infoOfs >= reader.dataSize:
         return 0
      reader.seek(self.infoOfs, NOESEEK_ABS)
      self.hx = reader.readInt()
      self.bd = reader.readInt()
      self.pageW = reader.readInt()
      self.pageH = reader.readInt()
      reader.seek(4, NOESEEK_REL)
      self.numSlices = reader.readInt()
      self.numBlocks = reader.readInt()
      if self.numSlices <= 0 or self.numBlocks <= 0:
         return 0
      reader.seek(4, NOESEEK_REL)
      self.slicesOfs = reader.tell()
      return 1

   def loadPage(self):
      reader = self.reader
      slices = bytes()
      slicesH = 0
      self.bitsPP = 8
      for i in range(0, self.numSlices):
         reader.seek(self.slicesOfs + i*32, NOESEEK_ABS)
         pixOfs = reader.readInt()
         rofs = reader.readInt()
         sliceW = reader.readInt() * 2
         sliceH = reader.readInt() * 2
         reader.seek(pixOfs+32, NOESEEK_ABS)
         imgSize = sliceW*sliceH if self.bitsPP >= 8 else (sliceW*sliceH)//2
         pix = reader.readBytes(imgSize)
         pix = rapi.imageUntwiddlePS2(pix, sliceW, sliceH, self.bitsPP)
         for j in range(0, sliceH):
            row = pix[j*sliceW:j*sliceW + sliceW]
            row += bytes([0])*(self.pageW-sliceW)
            slices += row
         slicesH += sliceH
      self.pageH = slicesH
      self.texPage = slices

   def getPaletteBlock(self, palX, palY):
      pal = bytearray(1024)
      idxCut = txyGetImageCut(self.texPage, self.pageW, self.pageH, palX, palY, 32, 32)
      return rapi.imageScaleRGBA32(txyRetile8(idxCut, 32, 32), (1.0, 1.0, 1.0, 2.0), 16, 16)

   def loadTextures(self, texList):
      reader = self.reader
      reader.seek(self.infoOfs+288, NOESEEK_ABS)
      texInfos = []
      for i in range(0, self.numBlocks):
         texInfo = {}
         texInfo["ofsa"] = reader.readInt()
         texInfo["na"] = reader.readInt()
         texInfo["width"] = reader.readInt()
         texInfo["height"] = reader.readInt()
         texInfo["ofsx"] = reader.readInt()
         texInfo["ofsy"] = reader.readInt()
         texInfo["ofsb"] = reader.readInt()
         reader.seek(4, NOESEEK_REL)
         texInfo["palx"] = reader.readInt()*2
         texInfo["paly"] = reader.readInt()*2
         reader.seek(24, NOESEEK_REL)
         texInfo["name"] = noeStrFromBytes(reader.readBytes(32))
         texInfos.append(texInfo)
      for texInfo in texInfos:
         pal = self.getPaletteBlock(texInfo["palx"], texInfo["paly"])
         idxCut = txyGetImageCut(self.texPage, self.pageW, self.pageH, texInfo["ofsx"], texInfo["ofsy"], texInfo["width"], texInfo["height"])
         pix = rapi.imageDecodeRawPal(idxCut, pal, texInfo["width"], texInfo["height"], self.bitsPP, "r8g8b8a8", noesis.DECODEFLAG_PS2SHIFT)
         texList.append(NoeTexture(texInfo["name"], texInfo["width"], texInfo["height"], pix, noesis.NOESISTEX_RGBA32))
         

def txyCheckType(data):
   txy = TXYFile(NoeBitStream(data))
   if txy.loadImageInfo() == 0:
      return 0
   return 1

def txyLoadRGBA(data, texList):
   txy = TXYFile(NoeBitStream(data))
   if txy.loadImageInfo() == 0:
      return 0

   txy.loadPage()
   txy.loadTextures(texList)
   return 1
```
 

And this is noesis:

[http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)

See ya
## Post #183
- Username: Novax
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 29, 2008 5:41 pm
- Post datetime: 2012-04-03T21:50:31+00:00
- Post Title: Re: xenosaga 3 model??request

Thank you very much. Wil double check download links when I get home. Currently browsing the internet on my droid.
## Post #184
- Username: Novax
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 29, 2008 5:41 pm
- Post datetime: 2012-04-04T13:27:41+00:00
- Post Title: Re: xenosaga 3 model??request

Only trouble I have now is that my .chr files export the model in parts and often oversizes certain ones. Now granted this data I have gotten long ago, so I will surely need to get a "fresh" copy of the files myself to double check this issue. If not, I'll post what I have to see what I did wrong. Other than that, keep on being amazing and helpful.
## Post #185
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-04-04T13:55:17+00:00
- Post Title: Re: xenosaga 3 model??request

Does anyone know how to extract *.chr?
## Post #186
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-04-04T14:59:07+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from dj082502
>
> Does anyone know how to extract *.chr?

Using Mario's script you don't need to extract anything but the txy containing the textures files. Just look for txy in hxd, select the block starting from it until the end and you'll get the file. The only matter here is to unzwissle the textures and aply a palette.

See ya.
## Post #187
- Username: richard99uk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 02, 2012 12:15 am
- Post datetime: 2012-05-01T16:29:29+00:00
- Post Title: Re: xenosaga 3 model??request

I was hoping someone could help me open/convert the .xtx files.

I noticed someone extracted the .xtx files from the KAO folder, but I couldn't find any mention of how to do it. I'm interested in extracting/converting the files, yajima/titleobj.xtx and yajima/titlebg2.bin.

Thanks very much in advance!
## Post #188
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2012-05-23T07:11:23+00:00
- Post Title: Re: xenosaga 3 model??request

The XTX in the KAO folder is a different format from all the rest of the XTXs. The KAO XTXs are raw 32bit RGBA images. There is only a header that gives info for the width and height and that's about it for the KAO folder.

Unfortunately that means the rest of the textures in this game are still mostly unconvertable.

(There are a few,--VERY few--, txy's that can be converted with the noesis plugin... I can think of 1... I think it was Wilhelm... but that's all...)
## Post #189
- Username: richard99uk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 02, 2012 12:15 am
- Post datetime: 2012-05-25T16:00:49+00:00
- Post Title: Re: xenosaga 3 model??request

I see. That's a shame. Thanks for letting me know Satoh.
## Post #190
- Username: karechan89
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 26, 2012 5:18 am
- Post datetime: 2012-05-25T21:33:16+00:00
- Post Title: Re: xenosaga 3 model??request

I wanted to ask if someone has idea how to make script for ep1. I don't care for textures and rest things, I mostly need only shape of characters and if there will be possible to convert to 3d max maps too then it would be haven for me. It would help me a lot with my projects when I done with Sakura animations I make right now and after I finish remake of Missing year, because then I will move to remaking Freaks and Xenosaga Drama cd as animations. I can make them slowly myself but it would take much more time.
I see on link that was posted in this topic that someone menage to export ep1 models... If it will be break a little then it's ok, it's always better to fix some things then start from nothing.

Anyway, one more question, is coding for ep3 maps are diffrent then ep2? Because gameplay maps/places from ep2 are exporting very good but I tryed to do the same with ep3 and no luck, is there anyway to fix it?  Well it's not so important as ep1 for me but there could be some usefull things there too.
## Post #191
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-05-27T05:18:43+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from karechan89
>
> I wanted to ask if someone has idea how to make script for ep1. I don't care for textures and rest things, I mostly need only shape of characters and if there will be possible to convert to 3d max maps too then it would be haven for me. It would help me a lot with my projects when I done with Sakura animations I make right now and after I finish remake of Missing year, because then I will move to remaking Freaks and Xenosaga Drama cd as animations. I can make them slowly myself but it would take much more time.
I see on link that was posted in this topic that someone menage to export ep1 models... If it will be break a little then it's ok, it's always better to fix some things then start from nothing.

Anyway, one more question, is coding for ep3 maps are diffrent then ep2? Because gameplay maps/places from ep2 are exporting very good but I tryed to do the same with ep3 and no luck, is there anyway to fix it?  Well it's not so important as ep1 for me but there could be some usefull things there too.

According to Mario, xenosaga I models are compressed so there's no way to convert them right now into something that most 3d programs can read unless someone figures out the compression method.
## Post #192
- Username: karechan89
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 26, 2012 5:18 am
- Post datetime: 2012-05-28T19:09:14+00:00
- Post Title: Re: xenosaga 3 model??request

Hmmm, with file format has ep1 character models and maps? Maybe I search more on japan sites or I ask on my University, I suck at programing but one of my classmate is good at this maybe he find some clue.

If it's not possible then I will try to hack  ep1 Reload character viewer to get to other models I need, but still that won't fix problem that I most need Maps files. Oh, well... Not all things goes easy.
## Post #193
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-08-22T00:58:37+00:00
- Post Title: Re: xenosaga 3 model??request

Can the textures be converted ?
## Post #194
- Username: UltimateSora
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Jun 24, 2011 2:56 am
- Post datetime: 2013-05-01T16:52:26+00:00
- Post Title: Re: xenosaga 3 model??request

Does anyone have the tools to get at the .chr files? I can't find the tools anywhere and this link that I suspect to be where the tools where hosted at is broken 
[http://godsibb.net/forums/index.php?/to ... __p__69487](http://godsibb.net/forums/index.php?/topic/1264-xenosaga-models-import-and-download/page__view__findpost__p__69487)

Thanks.
## Post #195
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-05-02T05:30:53+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from UltimateSora
>
> Does anyone have the tools to get at the .chr files? I can't find the tools anywhere and this link that I suspect to be where the tools where hosted at is broken 
http://godsibb.net/forums/index.php?/to ... __p__69487

Thanks.

Yeah, check my skydrive:

[https://skydrive.live.com/#cid=FFBE4E57 ... 49FCBE!177](https://skydrive.live.com/#cid=FFBE4E570949FCBE&id=FFBE4E570949FCBE!177)
## Post #196
- Username: UltimateSora
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Jun 24, 2011 2:56 am
- Post datetime: 2013-05-02T15:05:32+00:00
- Post Title: Re: xenosaga 3 model??request

Thanks a lot Darko!
## Post #197
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-05-03T18:26:33+00:00
- Post Title: Re: xenosaga 3 model??request

> Reply from UltimateSora
>
> Thanks a lot Darko!

No problem.
## Post #198
- Username: Famfrit211
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 19, 2019 12:50 pm
- Post datetime: 2019-02-19T04:55:05+00:00
- Post Title: Re: xenosaga 3 model??request

I'd like to have a 3D model of omega weltall as well as it's transformed id mode
## Post #199
- Username: maisayuriayu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 16, 2019 6:39 am
- Post datetime: 2019-06-15T22:42:03+00:00
- Post Title: Re: xenosaga 3 model??request

Does anyone have the file for xeno3trakit? I can't find mine anyway
## Post #200
- Username: Yggralith
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 24, 2018 3:54 am
- Post datetime: 2021-03-03T08:18:14+00:00
- Post Title: Re: xenosaga 3 model??request

> How to extract
>
> -------------------------------------------------------
>
> Copy the X3.00, X3.01, X3.02 from gamedisk on you hard drive.
>
> Open a command line
>
> Type : copy /b X3.01 + X3.02 X30.big
>
> This will join the two files into a big file X30.big.
>
> Type : xeno23lbae X3.00 Lba0.txt
>
> This decrypts the table into a usable format.
>
> Type : xenounpack Lba0.txt X30.big
>
> This still takes a little while. It unpacks the pack to a folder UNPACKED using the decrypted table.
>
> -------------------------------------------------------

What is this referring to again? I can swear I had downloaded something from this thread and used this to unpack the game, but I cannot find it again for the life of me. Xenounpack? I can't remember.

EDIT: Nevermind I found it.
