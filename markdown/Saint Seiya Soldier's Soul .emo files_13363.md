## Post #1
- Username: Watcher
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2015 3:43 pm
- Post datetime: 2015-09-25T02:45:41+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

hello everyone,recently I tried modding this game's .emo(model) file.the sf4 explorer worked partially,but when I tried to turn off character's sub model(cape and helmet),the model still appeared,only became black,like texture missing.the picture is in the attachment.

update:
now this game is released on pc,and I discovered why those black still showed in game.
because these .emo files have some "edge" in them,if you want to turn off a part of model,you need to change two places(01 to 00),the part and "edge".one is the part,another is "edge".if you only turn off the part,the black shadow won't disappear.
[screenshot1.png](https://xentaxbackup.github.io/file/9780_screenshot1.png)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-25T07:20:39+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

> Reply from Watcher
>
> hello everyone,recently I tried modding this game's .emo(model) file.the sf4 explorer worked partially,but when I tried to turn off character's sub model(cape and helmet),the model still appeared,only became black,like texture missing.How about telling what you did do exactly?

Having a look at an excerpt of an exported obj file (from ATN_02.emo, body_skins) I'm not surprised it didn't work:

v -0.000000 -0.000000 80741939242581992000000.000000 
v 0.000000 -27132918918488785000.000000 -269377.843750 
v -7605811712.000000 -0.000000 845592330240.000000 
v -0.000000 -0.000000 0.000000 
v 19125317687478838000000000000000.000000 -147406.968750 67860363779850465000000000000000000000.000000 
v -1.#QNAN0 192340413120512.000000 2843676087547574700000000000000000.000000

(Which version of the SF4explorer did you use? Last one seems to be v.37b ?)
## Post #3
- Username: Watcher
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2015 3:43 pm
- Post datetime: 2015-09-25T08:15:22+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

> Reply from shakotay2
>
> Watcher wrote:hello everyone,recently I tried modding this game's .emo(model) file.the sf4 explorer worked partially,but when I tried to turn off character's sub model(cape and helmet),the model still appeared,only became black,like texture missing.How about telling what you did do exactly?

Having a look at an excerpt of an exported obj file (from ATN_02.emo, body_skins) I'm not surprised it didn't work:

v -0.000000 -0.000000 80741939242581992000000.000000 
v 0.000000 -27132918918488785000.000000 -269377.843750 
v -7605811712.000000 -0.000000 845592330240.000000 
v -0.000000 -0.000000 0.000000 
v 19125317687478838000000000000000.000000 -147406.968750 67860363779850465000000000000000000000.000000 
v -1.#QNAN0 192340413120512.000000 2843676087547574700000000000000000.000000

(Which version of the SF4explorer did you use? Last one seems to be v.37b ?)

yeah,0.37b with big endian read mode.i just used the toggle visibility option,and sub models just turned black.i know this program is old and can't work properly,but I discovered the toggle on/off option just modify one byte,like 01 to 00.so I really don't know why it became this.
the models are in resource.cpk/chara,which need to use cpktools to extract.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-25T08:41:29+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

> Reply from Watcher
>
> the models are in resource.cpk/chara,which need to use cpktools to extract.I don't owe the game but as long as the obj export doesn't work for a model there's no chance that the toggeling will work, imho.

Because an unproper obj export means the SF4explorer doesn't recognize the emo file correctly
(it shows 22 EMG sections for ATN_02.emo but [EDGE] [EDGE] [EDGE]... for example might indicate that there's a problem).

There's a 'C' source available iirc so if you're a coder you could try to trace the problem.
(I don't have the time for such.)
## Post #5
- Username: Watcher
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2015 3:43 pm
- Post datetime: 2015-09-25T08:49:33+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

> Reply from shakotay2
>
> Watcher wrote:the models are in resource.cpk/chara,which need to use cpktools to extract.I don't owe the game but as long the obj export doesn't work for a model there's no chance that the toggeling will work.

Because an unproper obj export means the SF4explorer doesn't recognize the emo file correctly.

There's a 'C' source available iirc so if you're a coder you could try to trace the problem.
(I don't have the time for such.)
ok,I see.but actually the toggeling just changed one byte in this game's emo file,like sf4.they must update it.too bad I know nothing about models,however this game will release on pc soon,so I guess I will wait for a working tool.thanks for you help!
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-25T09:08:52+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

> Reply from Watcher
>
> so I guess I will wait for a working tool.most preferred option of most users  

Looking at the emo it seems to be a solvable problem. Just analyze the complete emo file creating objs from all submeshes then try to find out where the changed byte to be placed in the emo file.

Using hex2obj [view link in my sig]:



ATN_02_face.JPG (79.54 KiB) Viewed 658 times



btw: if I had a Street Fighter 4 sample maybe I could tell more
## Post #7
- Username: Watcher
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2015 3:43 pm
- Post datetime: 2015-09-25T09:21:21+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

> Reply from shakotay2
>
> most preferred option of most users
 
[https://mega.nz/#!Q8clUCqA!PqJl83cpKmmx ... 7Mjn2xkwEQ](https://mega.nz/#!Q8clUCqA!PqJl83cpKmmx1c6LePPtAVHr2NUzl1nsR7Mjn2xkwEQ)
here are some sf4 files.
## Post #8
- Username: Watcher
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2015 3:43 pm
- Post datetime: 2015-09-25T09:23:56+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

> Reply from Watcher
>
> shakotay2 wrote:most preferred option of most users  
 
https://mega.nz/#!Q8clUCqA!PqJl83cpKmmx ... 7Mjn2xkwEQ
here are some sf4 files.
by the way,I thought the toggle opinion did work partially.the helmet's middle part indeed disappeared.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-25T11:13:45+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

hmm, that's strange - piecemonteeSF4explorerV0.37b seems to affect the correct byte when switching off the body_skin in ANT_02.emo.

You might check this for your character emo file.



SF4_switching_body_OFF.JPG (168.15 KiB) Viewed 646 times



For ANT_02.emo you could try setting the byte at 0x153C4 to 00 (instead of the one at 0x153C7)
to see whether it will make a difference (just a wild guess).

But it might be a word counter (big endian for Saint Seiya, little endian for SF4) so the game will probably crash then.
## Post #10
- Username: Watcher
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2015 3:43 pm
- Post datetime: 2015-09-25T11:21:46+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

> Reply from shakotay2
>
> hmm, that's strange - piecemonteeSF4explorerV0.37b seems to affect the correct byte when switching off the body_skin in ANT_02.emo.

You might check this for your character emo file.
SF4_switching_body_OFF.JPG

For ANT_02.emo you could try setting the byte at 0x153C4 to 00 (instead of the one at 0x153C7)
to see whether it will make a difference (just a wild guess).
yeah,this is exactly I did for hld_00.emo.the address should be correct,but the problem is the sub model not complete disappeared.
## Post #11
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-09-26T14:22:23+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

ummm interesting in this game, is possible know from where you got game? possible got link to download?
## Post #12
- Username: Watcher
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2015 3:43 pm
- Post datetime: 2015-09-26T14:58:09+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

> Reply from CriticalError
>
> ummm interesting in this game, is possible know from where you got game? possible got link to download?
well,I downloaded this game from internet.however you need a cfw ps3(4.75+ system) to play it.pc edition will come out soon.about the download link,I send you a message,check it if you're interested.
## Post #13
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-09-26T16:14:25+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

ok many thanks for the links, anyway I got more faster downloads  anyway about your samples, here we go, 2 models of EMo you provide, no upload more so well here there are.
## Post #14
- Username: Watcher
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2015 3:43 pm
- Post datetime: 2015-09-26T16:21:10+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

> Reply from CriticalError
>
> ok many thanks for the links, anyway I got more faster downloads  anyway about your samples, here we go, 2 models of EMo you provide, no upload more so well here there are.

well,hope you can figure it out soon.  if you need more samples,just let me know.
## Post #15
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-09-26T19:01:12+00:00
- Post Title: Saint Seiya Soldier's Soul .emo files

ok after trying figure it, really can't, so maybe this would be useful for someone, here is maxscript for another game use same format, after try load model got this error.

Unable to convert: undefined to type: Integer64

and stop in this line of script.

short = bit.swapBytes short 2 1

This is file structure of SF4.

> SF4_FILE_STRUCT(EMOHeader,        ((char)(tag)(4))
>
>         ((unsigned short)(unknown1))
>
>         ((unsigned short)(headerSize))
>
>         ((unsigned short)(unknown2))
>
>         ((unsigned short)(unknown3))
>
>         ((unsigned short)(unknown4))
>
>         ((unsigned short)(unknown5))
>
>         ((unsigned long)(skeletonAddress))
>
>     )
>
>     SF4_FILE_STRUCT(EMOSkelettonHeader,
>
>         ((unsigned short)(nodeCount))
>
>         ((unsigned short)(unknown3))
>
>         ((unsigned long)(unknown4))//small number
>
>         ((unsigned long)(skeletonStartOffset))
>
>         ((unsigned long)(skeletonNameAddressOffset))
>
>         ((unsigned long)(unknown5))//0
>
>         ((unsigned long)(unknown6))//0
>
>         ((unsigned long)(unknown7))//address for bunch of FF's
>
>         ((unsigned long)(matrixOffset))
>
>     )
>
>     SF4_FILE_STRUCT(EMOSkelettonNodeTemp,
>
>         ((unsigned short)(parent))//FFFF if root
>
>         ((unsigned short)(id))
>
>         ((unsigned short)(child2))//FFFF if none
>
>         ((unsigned short)(child3))//FFFF if none
>
>         ((unsigned long)(child4))//FFFF if none
>
>         ((unsigned long)(unknown4))//0
>
>         ((float)(matrix)(16))
>
>     )
>
>     SF4_FILE_STRUCT(EMOSkelettonNode,
>
>         ((unsigned short)(parent))//FFFF if root
>
>         ((unsigned short)(number))
>
>         //((unsigned short)(unknown2))//FFFF
>
>         //((unsigned short)(unknown1))//FFFF
>
>         //((unsigned long)(unknown3))//FFFF
>
>         //((unsigned long)(unknown4))//0
>
>         ((float)(matrix)(16))
>
>     )
[emo.7z](https://xentaxbackup.github.io/file/9791_emo.7z)
## Post #16
- Username: Watcher
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2015 3:43 pm
- Post datetime: 2015-09-27T01:28:23+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

> Reply from CriticalError
>
> ok after trying figure it, really can't, so maybe this would be useful for someone, here is maxscript for another game use same format, after try load model got this error.

Unable to convert: undefined to type: Integer64

and stop in this line of script.

short = bit.swapBytes short 2 1

This is file structure of SF4.
 SF4_FILE_STRUCT(EMOHeader,        ((char)(tag)(4))
        ((unsigned short)(unknown1))
        ((unsigned short)(headerSize))
        ((unsigned short)(unknown2))
        ((unsigned short)(unknown3))
        ((unsigned short)(unknown4))
        ((unsigned short)(unknown5))
        ((unsigned long)(skeletonAddress))
    )
    SF4_FILE_STRUCT(EMOSkelettonHeader,
        ((unsigned short)(nodeCount))
        ((unsigned short)(unknown3))
        ((unsigned long)(unknown4))//small number
        ((unsigned long)(skeletonStartOffset))
        ((unsigned long)(skeletonNameAddressOffset))
        ((unsigned long)(unknown5))//0
        ((unsigned long)(unknown6))//0
        ((unsigned long)(unknown7))//address for bunch of FF's
        ((unsigned long)(matrixOffset))
    )
    SF4_FILE_STRUCT(EMOSkelettonNodeTemp,
        ((unsigned short)(parent))//FFFF if root
        ((unsigned short)(id))
        ((unsigned short)(child2))//FFFF if none
        ((unsigned short)(child3))//FFFF if none
        ((unsigned long)(child4))//FFFF if none
        ((unsigned long)(unknown4))//0
        ((float)(matrix)(16))
    )
    SF4_FILE_STRUCT(EMOSkelettonNode,
        ((unsigned short)(parent))//FFFF if root
        ((unsigned short)(number))
        //((unsigned short)(unknown2))//FFFF
        //((unsigned short)(unknown1))//FFFF
        //((unsigned long)(unknown3))//FFFF
        //((unsigned long)(unknown4))//0
        ((float)(matrix)(16))
    )
I see.this game must use a updated version of emo.so old script won't work at all.anyway thanks for your help.I hope someone else can solve this problem.
## Post #17
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-09-30T14:09:38+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

Hi
For Blender 249 users:
Here is a blender importer for PS3 Saint Seiya Brave Soldier and  it works with samples from Saint Seiya Soldier's Soul .
It works only with installed Blender old version 249 and use installed Python version 266.
Unpack zip ,double click Blender249.blend , in Blender Text Window press alt+p and select:
1.file with *.emb - color and normal textures
2.file with *.emo - model with vertex weights and bones
[Blender249[SaintSeiyaBraveSoldier][PS3][emo][emb][2015-02-24].zip](https://xentaxbackup.github.io/file/9808_Blender249[SaintSeiyaBraveSoldier][PS3][emo][emb][2015-02-24].zip)
## Post #18
- Username: Watcher
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2015 3:43 pm
- Post datetime: 2015-09-30T14:23:01+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

> Reply from Szkaradek123
>
> Hi
For Blender 249 users:
Here is a blender importer for PS3 Saint Seiya Brave Soldier and  it works with samples from Saint Seiya Soldier's Soul .
It works only with installed Blender old version 249 and use installed Python version 266.
Unpack zip ,double click Blender249.blend , in Blender Text Window press alt+p and select:
1.file with *.emb - color and normal textures
2.file with *.emo - model with vertex weights and bones
wow,another importer from the mighty Szkaradek123!thank you very much,friend!
do you have a clue on those black models in the picture?those should be invisible.

edit:yeah,this importer can import the model file,but when I selected a .emb file,it did nothing.this is strange.
## Post #19
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-09-30T17:54:28+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

> Reply from Szkaradek123
>
> Hi
For Blender 249 users:
Here is a blender importer for PS3 Saint Seiya Brave Soldier and  it works with samples from Saint Seiya Soldier's Soul .
It works only with installed Blender old version 249 and use installed Python version 266.
Unpack zip ,double click Blender249.blend , in Blender Text Window press alt+p and select:
1.file with *.emb - color and normal textures
2.file with *.emo - model with vertex weights and bones

Thanks, a little question, can you check naruto shippuden ultimate ninja storm files and dreamy theater files??, or maybe I'm asking for too much.
## Post #20
- Username: Watcher
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2015 3:43 pm
- Post datetime: 2015-11-26T13:49:23+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

thread updated.
## Post #21
- Username: cherry8989
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 19, 2014 4:38 am
- Post datetime: 2015-11-29T23:30:06+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

Hi good afternoon, you could correct the MaxScript "EMO" to get the 3D modeling.
## Post #22
- Username: SBlank
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 02, 2015 6:41 am
- Post datetime: 2015-12-01T22:52:51+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

Hi and thanks for the info.
I'm not into modding at all, my interest only lies in getting the models so I have had some success in using ninjaripper. The trouble is that it captures only the character you're playing along with the whole scene so there's a lot of cleaning up to do if you're only interested in the armors (like I am). Hope it helps someone.
## Post #23
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-12-02T01:50:41+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

> Reply from SBlank
>
> Hi and thanks for the info.
I'm not into modding at all, my interest only lies in getting the models so I have had some success in using ninjaripper. The trouble is that it captures only the character you're playing along with the whole scene so there's a lot of cleaning up to do if you're only interested in the armors (like I am). Hope it helps someone.

Download ps3 version of ss:ss and use the script.
## Post #24
- Username: SBlank
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 02, 2015 6:41 am
- Post datetime: 2015-12-02T17:48:26+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

> Reply from Darko
>
> SBlank wrote:Hi and thanks for the info.
I'm not into modding at all, my interest only lies in getting the models so I have had some success in using ninjaripper. The trouble is that it captures only the character you're playing along with the whole scene so there's a lot of cleaning up to do if you're only interested in the armors (like I am). Hope it helps someone.

Download ps3 version of ss:ss and use the script.

I'll give it a try, thanks again.
## Post #25
- Username: Hseeker
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 04, 2015 2:33 am
- Post datetime: 2015-12-03T18:37:32+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

Hey first time poster here.
If been trying to open these .emo files with succes (kinda) but cant seem to locate the Saint seiya Odin robe anywhere.(only Seiya model if found is in the DSE folder but those are just his stander armor sets)

Is there anyone kind enough to send me the Odin model as a .obj so i can edit them in blender.
## Post #26
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-12-03T19:56:45+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

> Reply from Hseeker
>
> Hey first time poster here.
If been trying to open these .emo files with succes (kinda) but cant seem to locate the Saint seiya Odin robe anywhere.(only Seiya model if found is in the DSE folder but those are just his stander armor sets)

Is there anyone kind enough to send me the Odin model as a .obj so i can edit them in blender.
I can send you the odin robe in fbx format.
## Post #27
- Username: JulioCabral
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Nov 28, 2015 7:14 am
- Post datetime: 2015-12-06T00:11:02+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

Hello, thanks for the information and the scripts. I manage to extract the models with no problems but, what about the textures? Anyone knows a way to extract the textures? Thanks in advance.
## Post #28
- Username: wansoft
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 09, 2012 5:31 am
- Post datetime: 2015-12-09T02:14:37+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

> Reply from JulioCabral
>
> Hello, thanks for the information and the scripts. I manage to extract the models with no problems but, what about the textures? Anyone knows a way to extract the textures? Thanks in advance.

I can extract textures, one by one, using sf4explorer and loading EMB files from PC version. But i'm trying extract Stages, when i use Blender to get stage, i get too much garbage.... some solution for import levels to 3ds Max ?
## Post #29
- Username: heavenseeker666
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 21, 2016 6:41 am
- Post datetime: 2016-07-21T00:44:25+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

can some body help me with this problem please?  I'm trying to run a script to imprt saint seiya models to blender but still giving me this error. i don't know what it means. can someome helpe out ? Thanks
[problem.png](https://xentaxbackup.github.io/file/11306_problem.png)
## Post #30
- Username: GoFeR
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 06, 2012 3:27 am
- Post datetime: 2017-03-06T14:24:52+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

> Reply from heavenseeker666
>
> can some body help me with this problem please?  I'm trying to run a script to imprt saint seiya models to blender but still giving me this error. i don't know what it means. can someome helpe out ? Thanks

Did you fix it? i have the same problem
## Post #31
- Username: megreznofrederich
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 27, 2017 9:20 am
- Post datetime: 2017-11-28T15:12:14+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

guys, i`m new. blender 249 won`t detect my ptyhon 2.6 installed. how or where should i decompresse it?
## Post #32
- Username: megreznofrederich
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 27, 2017 9:20 am
- Post datetime: 2017-11-28T15:47:42+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

aamm how do i put this...?
is there anything that works with the pc version?, i'va already extracted the models from the cpk fil with quickbms (thanks)
but can`t make the script work on blender, it pops out things like ¨ilegal characters in file name¨ (wich is wrong, because filenames have_ or 00 or 0, etc, but no slashes or commas nor dots) so...my question would be if there's any script that make it work, doesnt have to be a blender thing, i have iclone 6,5, xchange pipeline and 3ds max.
## Post #33
- Username: saidbou
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 24, 2019 6:48 am
- Post datetime: 2019-01-23T23:01:30+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

> Reply from GoFeR
>
> heavenseeker666 wrote:can some body help me with this problem please?  I'm trying to run a script to imprt saint seiya models to blender but still giving me this error. i don't know what it means. can someome helpe out ? Thanks

Did you fix it? i have the same problem

Me too, getting the same problem...
## Post #34
- Username: jeas86
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 09, 2020 1:12 pm
- Post datetime: 2020-10-19T02:04:19+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

Hola! a todos desafortunadamente no pude obtener los archivos de texturas nunca encontré la versión de blender ni el Python que necesitaba verifique con el que posteo el usuario Szkaradek123 pero no me funciona me sale error al hacer alt + p con el script nunca me salió la opción de importar solo me decía error y nunca me daba la opción de importar solo de abrir y no me creaba nada, buscando en paginas logre obtener las herramientas para la extracción de los modelos pero los archivos .emb donde están las texturas, los extraje pero me los extrae en formato .bin luego de una incesante búsqueda me los extrajo en formato . dds y probé muchas demasiadas  herramientas para descomprimirlos y no lo pude lograr espero si alguien puede encontrar la forma de extraer las texturas de los personajes continúe dando info en este hilo y si alguien necesita los modelos puede responder a este hilo con su correo y los cambiaria por las texturas,  gracias por la info dure 2 a 3 semanas trasnochando para intentar conseguir las texturas y aun se me hace muy difícil y no lo he logrado, agradecería si alguien tiene el Python y el blender adecuado o el script por favor lo postee nuevamente o si alguien hace un tutorial estaría completamente agradecido   ?
## Post #35
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-10-19T13:29:01+00:00
- Post Title: Re: Saint Seiya Soldier's Soul .emo files

You can use this [tool](https://mega.nz/file/Oss33bbT#1dyPoQXwloRt_vXbuY1hRvV4sHzUfIEH-VEX4QRkvQQ) to convert the emo to fbx and extracting the textures from the emb, it was made by eternity for the Soldiers' Soul modding community. It's a drag and drop tool.
