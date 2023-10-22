## Post #1
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-08-25T06:45:59+00:00
- Post Title: demon's souls FLV file

Hello everyone! I would like to start a topic like that of dark soul flv but the center demons' souls. I would have interest in some models and would like to import them in 3d studio max.
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-08-25T07:06:32+00:00
- Post Title: demon's souls FLV file

Maxscript for Demon's Souls models, not finished but you will get meshes+weights only bones will be twisted for some models


[Demon's_Souls.7z](https://xentaxbackup.github.io/file/7724_Demon's_Souls.7z)
## Post #3
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-08-25T09:56:20+00:00
- Post Title: demon's souls FLV file

> Reply from zaramot
>
> Maxscript for Demon's Souls models, not finished but you will get meshes+weights only bones will be twisted for some models

thank you very much for the script! but you can also have the model with the texture?
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-08-25T10:13:16+00:00
- Post Title: demon's souls FLV file

Textures are in .TPF containers, the are straight .dds files. You can extract them with any HexEditor their names/offsets and size are visible there. I'll write Noesis script if will have time or maybe someone write it first xD
## Post #5
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-08-25T11:43:47+00:00
- Post Title: demon's souls FLV file

well, well .... but now is also another issue that are the weapons! are in a format different from the characters!
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-08-25T12:26:50+00:00
- Post Title: demon's souls FLV file

Different format? All weapons+armor parts are in .flver format and imports fine!
[wep.jpg](https://xentaxbackup.github.io/file/7732_wep.jpg)
## Post #7
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-08-25T16:52:16+00:00
- Post Title: demon's souls FLV file

> Reply from zaramot
>
> Different format? All weapons+armor parts are in .flver format and imports fine!


and where to find them? apart from the characters, can not find them in that size!
## Post #8
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-08-26T00:50:12+00:00
- Post Title: demon's souls FLV file

probably in 'parts' if the folder structure is the same.

If you need textures you can prob modify Rick's TPF unpacker from his Dark souls tools to work with the 'older' Demon's Souls TPFs.

> Reply from zaramot
>
> Textures are in .TPF containers, the are straight .dds files. You can extract them with any HexEditor their names/offsets and size are visible there. I'll write Noesis script if will have time or maybe someone write it first xD
Or Texturefinder can probably help you

Gonna try and dump my disc and see what I can do.
## Post #9
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-08-26T00:51:05+00:00
- Post Title: demon's souls FLV file

whoops, double post
## Post #10
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-08-26T05:41:31+00:00
- Post Title: demon's souls FLV file

> Reply from TehDave
>
> probably in 'parts' if the folder structure is the same.

If you need textures you can prob modify Rick's TPF unpacker from his Dark souls tools to work with the 'older' Demon's Souls TPFs.
zaramot wrote:Textures are in .TPF containers, the are straight .dds files. You can extract them with any HexEditor their names/offsets and size are visible there. I'll write Noesis script if will have time or maybe someone write it first xD
Or Texturefinder can probably help you

Gonna try and dump my disc and see what I can do.

if you can do it for me okay! tries to put to work immediately! and for weapons you're right is in parts but are in a different format that I can not read!
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-08-26T05:55:07+00:00
- Post Title: demon's souls FLV file

Ah, here's quickbms script to extract files from .partsbnd containers - you will get models and textures in .flver/.tpf
[Dark_Souls_DCX.7z](https://xentaxbackup.github.io/file/7736_Dark_Souls_DCX.7z)
## Post #12
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-08-26T07:05:24+00:00
- Post Title: demon's souls FLV file

I used your script but when the amount there is nothing! only two bone!
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-08-26T07:17:20+00:00
- Post Title: demon's souls FLV file

You did something wrong I guess, attach here model you tried or just write the name of it. I'll try it from my side. Maybe I posted first version of the script, not latest xD
## Post #14
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-08-26T08:02:06+00:00
- Post Title: demon's souls FLV file

yeah, I was just about to ask about the partsbnd in demon's

Just need textures now, Texturefinder can see them but holy shit is it a pain to do this manually. We really need a script for the DeS format TPFs.

edit: didn't work with the partsbnd.dcx but it did work with the partsbnd. Odd.
## Post #15
- Username: TehDave
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-08-26T14:10:33+00:00
- Post Title: demon's souls FLV file

This will let you view the .TPF textures in Noesis for this game.

Someone requested in another thread so I figured I'd post it here too!
[fmt_DemonSouls_TPF.zip](https://xentaxbackup.github.io/file/7739_fmt_DemonSouls_TPF.zip)
## Post #16
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2014-08-27T10:56:33+00:00
- Post Title: Re: demon's souls FLV file

> Reply from Gh0stBlade
>
> This will let you view the .TPF textures in Noesis for this game.

Someone requested in another thread so I figured I'd post it here too!

I get this error when trying to view .tpf textures in Noesis:

---------------------------
Noesis Python Error
---------------------------
Traceback (most recent call last):
  File "D:\Program Files (x86)\Mod Tools\noesis\plugins\python\fmt_dark_souls_tpf.py", line 34, in noepyLoadRGBA
    TpfName = bs.readString()
  File "D:\Program Files (x86)\Mod Tools\noesis\plugins\python\inc_noesis.py", line 152, in readString
    return noesis.bsReadString(self.h)
UnicodeDecodeError: 'utf8' codec can't decode byte 0x80 in position 0: invalid start byte
## Post #17
- Username: joqqy
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-08-27T14:26:32+00:00
- Post Title: Re: demon's souls FLV file

> Reply from joqqy
>
> Gh0stBlade wrote:This will let you view the .TPF textures in Noesis for this game.

Someone requested in another thread so I figured I'd post it here too!

That's what happens when you only get one sample. Just drop me a PM with the one you have problems with and I'll update the script. It was programmed to handle the single file I was sent. I did not have any other files to try.

Cheers.

Edit: Just looking at the error message it's saying the error is with the script:

fmt_dark_souls_tpf.py

This is not my python script it's loading so that indicates there is a collision. You must delete the fmt_dark_souls_tpf.py or rename it to something else so it doesn't collide with:

fmt_DemonSouls_TPF.py

Probably should work.
## Post #18
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2014-08-27T17:37:57+00:00
- Post Title: Re: demon's souls FLV file

> Reply from Gh0stBlade
>
> joqqy wrote:Gh0stBlade wrote:This will let you view the .TPF textures in Noesis for this game.

Someone requested in another thread so I figured I'd post it here too!

Edit: Just looking at the error message it's saying the error is with the script:

fmt_dark_souls_tpf.py

This is not my python script it's loading so that indicates there is a collision. You must delete the fmt_dark_souls_tpf.py or rename it to something else so it doesn't collide with:

fmt_DemonSouls_TPF.py

Probably should work.

Many Thanks, that did the trick, works fine now.

Was not paying attention in the error message that the dark souls .tpf script was colliding with your updated one. But that was indeed the problem.

Best Regards
joq
## Post #19
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-08-29T10:54:00+00:00
- Post Title: Re: demon's souls FLV file

PSN took fucking forever to download this shit, but I've gone through most of the files already. More pics coming soon-ish.
## Post #20
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-08-29T13:04:38+00:00
- Post Title: Re: demon's souls FLV file

> Reply from TehDave
>
> 


PSN took fucking forever to download this shit, but I've gone through most of the files already. More pics coming soon-ish.

excuse me throw the texture of the armor? fails to take the diffuse and specular!
## Post #21
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-08-30T00:52:36+00:00
- Post Title: Re: demon's souls FLV file

There's a noesis script on the last page that lets you export the textures.
## Post #22
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-08-31T06:47:32+00:00
- Post Title: Re: demon's souls FLV file

> Reply from TehDave
>
> There's a noesis script on the last page that lets you export the textures.

I have already used that script but I just read the normal armor!
## Post #23
- Username: nameless32
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-09-05T02:43:08+00:00
- Post Title: Re: demon's souls FLV file

Updated script..  
[fmt_DemonSouls_TPF_1_1.zip](https://xentaxbackup.github.io/file/7774_fmt_DemonSouls_TPF_1_1.zip)
## Post #24
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-09-06T06:07:07+00:00
- Post Title: Re: demon's souls FLV file

> Reply from Gh0stBlade
>
> Updated script..
I tried the updated script, but it seems that the diffusive and specular texture stops are situated not just in that folder! is there a way to know which texture using a model in 3d studio max?

and in any case there is a problem with the script of the models. unable to import the characters but not the objects as weapons!
## Post #25
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-09-18T07:46:43+00:00
- Post Title: Re: demon's souls FLV file

as far as I'm aware the script doesn't grab the material assignments, unlike dark souls though most of the textures are descriptively named.

Any news on updating the script to output proper bone names and fix some of the improper bone placement on certain meshes? And any chance this script might possibly support Dark Souls 1 and 2 as well?
## Post #26
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-09-18T11:20:39+00:00
- Post Title: Re: demon's souls FLV file

Bone names yes, bone position/transformation for some meshes - no. I stuck with bone matrix, since I'm not very interested in these games, I'm not planning to return to them. Script is here, info about .flver too - I'm sure someone will continue work on this format. As for Dark Souls 1,2 I have scripts for them too, but they share same issues like Demon's Souls.
Dibe91, which characters models doesn't work for you? Send me them in PM, if you want
## Post #27
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-09-19T10:29:08+00:00
- Post Title: Re: demon's souls FLV file

Do you mind posting the scripts for the other two games? Currently neither Dark Souls have a import script for their models and I know weights and bones for their meshes have been on people's wishlist for a while. 

I also had a thought about animations, if the script eventually can assign the actual bone names, the animations should finally be usable outside of Havok's SDK. The SDK has no problem reading and playing back the HKX files since it can see the skeleton, and converting them to gamebryo .KF works, but since there's no skeleton with proper bone names to bind to, they can be imported and edited.

I realize you can probably just rename the helpers to the actual bone names by reading them in Havok SDK but that's pretty tedious to do by hand.

EDIT: I almost forgot about the bug I was going to report with the current Demon's Souls script, as far as everything in the chr directory goes, they import fine with no issues outside of the messed up bone rotations for some, but certain meshes, namely stuff from parts and certain level geometry don't import properly (missing entire elements, like the Dark Silver set worn by Garl Vinland, the helmet doesn't import properly, and meshes I found that possibly belong to the cut 6th archstone maps).

I'm still looking through the stuff I've extracted to see if there are any more specific examples of models that don't import properly, and I'll post samples of them here when I find them since I'm not sure if it's just certain meshes or something like what happened with Dark Souls where some models used different vert types that meant an import method for one model might not work other kinds of models
## Post #28
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-09-25T13:52:11+00:00
- Post Title: Re: demon's souls FLV file

> Reply from zaramot
>
> Bone names yes, bone position/transformation for some meshes - no. I stuck with bone matrix, since I'm not very interested in these games, I'm not planning to return to them. Script is here, info about .flver too - I'm sure someone will continue work on this format. As for Dark Souls 1,2 I have scripts for them too, but they share same issues like Demon's Souls.
Dibe91, which characters models doesn't work for you? Send me them in PM, if you want

the characters reads them fine, but if I try to import a weapon alone, nothing happens
## Post #29
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-10-22T00:48:33+00:00
- Post Title: Re: demon's souls FLV file

I can confirm this too, I finally got around to trying the actual weapon models and they don't import at all. I think you might have posted an  older version of your script then it seems, since nothing out of the weapons folder seems to work but it does for you.
## Post #30
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-10-22T07:40:18+00:00
- Post Title: Re: demon's souls FLV file

Yup guys, my bad. Try this one, should work fine! Let me know if there will be something wrong
[Demon's_Souls_Weapons.7z](https://xentaxbackup.github.io/file/7975_Demon's_Souls_Weapons.7z)
## Post #31
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-10-24T21:03:05+00:00
- Post Title: Re: demon's souls FLV file

> Reply from zaramot
>
> Yup guys, my bad. Try this one, should work fine! Let me know if there will be something wrong

I did a test, and now it works like a dream! thank you very much! if you can, adjust better to the script of the characters.
## Post #32
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2014-10-29T10:11:00+00:00
- Post Title: Re: demon's souls FLV file

Definitely agree with the above, bone names at the least would help piece together the armor sets immensely as the dummy names are not consistent at all between imports. 

I'm still compiling examples of non-working meshes (ones that return 'failed!' in the script listener or are missing geometry on import) out of the parts and map folders, I think just about everything else works fine barring the bone rotation (which should be easy to fix manually)
## Post #33
- Username: illincrux
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 16, 2010 11:46 pm
- Post datetime: 2015-01-11T12:59:14+00:00
- Post Title: Re: demon's souls FLV file

> Reply from zaramot
>
> Yup guys, my bad. Try this one, should work fine! Let me know if there will be something wrong

Greetings,

For whatever reason the maxscripts are not working in 3DSM2015:

```
"Bone Start @ 0xa0000080L"
-- Error occurred in readBElong(); filename: D:\Utilities\temp\Demon's_Souls\Demon's_Souls.ms; position: 433; line: 11
--  Frame:
--   fstream: <BinStream:D:\Documents\Projects\Lord\HD_F_9710.flver>
--   called in a loop; filename: D:\Utilities\temp\Demon's_Souls\Demon's_Souls.ms; position: 2355; line: 98
--  Frame:
--   BPos: 2684354700L
--   BoneNameOff: undefined
--   BoneName: undefined
--   a: 1
-- Error occurred during fileIn in "D:\Utilities\temp\Demon's_Souls\Demon's_Souls.ms"; line number: 11
>> MAXScript FileIn Exception:
-- Unable to convert: undefined to type: Integer64 <<
```


Are there any converters out there that support UVs other than this script?
## Post #34
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-01-20T15:31:37+00:00
- Post Title: Re: demon's souls FLV file

> Reply from illincrux
>
> zaramot wrote:Yup guys, my bad. Try this one, should work fine! Let me know if there will be something wrong

Greetings,

For whatever reason the maxscripts are not working in 3DSM2015:
Code: Select all"1615134720"
"Bone Start @ 0xa0000080L"
-- Error occurred in readBElong(); filename: D:\Utilities\temp\Demon's_Souls\Demon's_Souls.ms; position: 433; line: 11
--  Frame:
--   fstream: <BinStream:D:\Documents\Projects\Lord\HD_F_9710.flver>
--   called in a loop; filename: D:\Utilities\temp\Demon's_Souls\Demon's_Souls.ms; position: 2355; line: 98
--  Frame:
--   BPos: 2684354700L
--   BoneNameOff: undefined
--   BoneName: undefined
--   a: 1
-- Error occurred during fileIn in "D:\Utilities\temp\Demon's_Souls\Demon's_Souls.ms"; line number: 11
>> MAXScript FileIn Exception:
-- Unable to convert: undefined to type: Integer64 <<

Are there any converters out there that support UVs other than this script?
just get an older version of max
## Post #35
- Username: ricodago
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 05, 2015 2:07 pm
- Post datetime: 2015-08-10T06:47:58+00:00
- Post Title: Re: demon's souls FLV file

hi! i'd like to import the obj models too but the UVs seem a bit off. I tried both the MAXScript files posted here. For example o1000 or o1010 are two of the archstones models, the mesh seems ok but the UVs have missing parts and feel similar to what they should be to map the texture but once applied are quite off.
## Post #36
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-08-10T11:45:07+00:00
- Post Title: Re: demon's souls FLV file

looks unfortunately this script still has problems. think that exchanges the bones of the skeleton! unfortunately it does not seem to have time to fix it and do not know when he will correct it.
## Post #37
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-08-10T14:42:42+00:00
- Post Title: Re: demon's souls FLV file

Yup, sorry guys I completely lost interest in this game. So, anyone who's is willing to finish importer, please be my guest! Recently, I don't have much time for reversing 3d formats, so going to spend it for games which I really like.
## Post #38
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-08-11T12:01:40+00:00
- Post Title: Re: demon's souls FLV file

> Reply from zaramot
>
> Yup, sorry guys I completely lost interest in this game. So, anyone who's is willing to finish importer, please be my guest! Recently, I don't have much time for reversing 3d formats, so going to spend it for games which I really like.

ok sorry if I insist but you just make the script for dark souls? I just need this .... then you're free!
## Post #39
- Username: mrsmallbee
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 08, 2017 11:19 am
- Post datetime: 2017-02-09T13:11:42+00:00
- Post Title: Re: demon's souls FLV file

how do you extract demon's souls resource?
## Post #40
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-07-03T19:26:14+00:00
- Post Title: Re: demon's souls FLV file

Someone have filenames list for Dark Souls 2 and Demon's souls?
## Post #41
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-07-04T06:01:18+00:00
- Post Title: Re: demon's souls FLV file

I do not know if you mean the names and characters of the characters, but this is that of demon souls:[https://docs.google.com/spreadsheets/d/ ... edit#gid=0](https://docs.google.com/spreadsheets/d/1WcBkVyyWzW6DzDk61GbcmSE1l91CC2KB6k0ZbzRS1Uk/edit#gid=0)
## Post #42
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-07-06T13:47:19+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dibe91
>
> I do not know if you mean the names and characters of the characters, but this is that of demon souls:https://docs.google.com/spreadsheets/d/ ... edit#gid=0
Oh, yes - this is what I need!   
Great thanks for you!

P.S. Do you have similar for armor?
## Post #43
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-07-06T17:05:24+00:00
- Post Title: Re: demon's souls FLV file

> Reply from TokiChan
>
> dibe91 wrote:I do not know if you mean the names and characters of the characters, but this is that of demon souls:https://docs.google.com/spreadsheets/d/ ... edit#gid=0
Oh, yes - this is what I need!   
Great thanks for you!

P.S. Do you have similar for armor?

Unfortunately I have nothing of the kind at least that I know. But is trying to do something to get the models with the original skeleton? If you would like to know if you're making progress
## Post #44
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-07-06T21:36:24+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dibe91
>
> TokiChan wrote:dibe91 wrote:I do not know if you mean the names and characters of the characters, but this is that of demon souls:https://docs.google.com/spreadsheets/d/ ... edit#gid=0
Oh, yes - this is what I need!   
Great thanks for you!

P.S. Do you have similar for armor?

Unfortunately I have nothing of the kind at least that I know. But is trying to do something to get the models with the original skeleton? If you would like to know if you're making progress

Yes, I get armors with original bones. For some it need fix twisting or remake weight, but in general is good. [http://tokami-fuko.deviantart.com/art/O ... -680216174](http://tokami-fuko.deviantart.com/art/Ostrava-of-Boletaria-DemS-plate-armor-680216174)
Ok, thanks for reply!
[Ashampoo_Snap_2017.07.07_00h37m40s_001_.png](https://xentaxbackup.github.io/file/13082_Ashampoo_Snap_2017.07.07_00h37m40s_001_.png)
## Post #45
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-07-07T05:13:01+00:00
- Post Title: Re: demon's souls FLV file

I'm more interested in monsters
## Post #46
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-07-08T13:02:46+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dibe91
>
> I'm more interested in monsters
Yes, I almost done with Stormbeasts and Double winged hawks, they need fix bones, can get more others
And I final Dragon God and Imperial spy with original bones (with dragon was hard find and replace all bones for wings, huh)
Do u need someone?
[drgod.jpg](https://xentaxbackup.github.io/file/13087_drgod.jpg)
## Post #47
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-07-09T06:53:14+00:00
- Post Title: Re: demon's souls FLV file

To tell the truth, i would need all the templates ..... i would use it to a friend of mine who wanna use them to make us videos on youtube
## Post #48
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-07-10T22:57:00+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dibe91
>
> To tell the truth, i would need all the templates ..... i would use it to a friend of mine who wanna use them to make us videos on youtube
Ok, I hope get all in future 
All I'll upload in Deviantart. Or try send the blocks without conversions and fixes, if u need right now
## Post #49
- Username: WarlordSieck
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 15, 2017 7:02 am
- Post datetime: 2017-07-16T22:51:37+00:00
- Post Title: Re: demon's souls FLV file

Hey guys, sorry to further resurrect an old thread but could someone that is an expert on ripping models and textures from Demon's Souls please either 1) rip and send a couple models with textures to me which include: Armor Spider Boss model, textures and, if possible, animations (going to attempt to make him into a boss/companion for Skyrim), Garl Vinland's Dark Silver set (with shield) with models and textures, and the fluted armor set, (with long sword and knights shield) with models and textures.

   OR you could 2). Provide me with the proper knowledge and software to rip the needed models, textures and animations myself. I have the intent of making/converting these two armor sets into armor sets for Skyrim.

Sorry if this sounds like a lot but I don't where else to go to look for this kind of information. 

Thanks, in advance!
## Post #50
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-07-24T14:09:51+00:00
- Post Title: Re: demon's souls FLV file

> Reply from WarlordSieck
>
> Hey guys, sorry to further resurrect an old thread but could someone that is an expert on ripping models and textures from Demon's Souls please either 1) rip and send a couple models with textures to me which include: Armor Spider Boss model, textures and, if possible, animations (going to attempt to make him into a boss/companion for Skyrim), Garl Vinland's Dark Silver set (with shield) with models and textures, and the fluted armor set, (with long sword and knights shield) with models and textures.

   OR you could 2). Provide me with the proper knowledge and software to rip the needed models, textures and animations myself. I have the intent of making/converting these two armor sets into armor sets for Skyrim.

Sorry if this sounds like a lot but I don't where else to go to look for this kind of information. 

Thanks, in advance!
I can send you my founded parts folder - u can use quick BMS with script from this topic (if no found, I'll send too)
I don't know whatnumber of new sets, but planport some to Skyrim too
## Post #51
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-08-15T18:45:03+00:00
- Post Title: Re: demon's souls FLV file

So,here are opened Chr folder (enemy/boses/characters) from my DemS. SOme already converted and almost all unpack textures.
[https://drive.google.com/open?id=0B25vR ... XRHcDhnd1k](https://drive.google.com/open?id=0B25vRFsoP3MqdEhuQXRHcDhnd1k)
Next is Parts folder (slow internet)
## Post #52
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-08-18T11:50:58+00:00
- Post Title: Re: demon's souls FLV file

Parts folder - not fully unpacked
(armor, clothes, weapons, shields)
[https://drive.google.com/open?id=0B25vR ... 0xPRUVQVUU](https://drive.google.com/open?id=0B25vRFsoP3MqUXdzS0xPRUVQVUU)
## Post #53
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-08-18T16:57:16+00:00
- Post Title: Re: demon's souls FLV file

But is there a chance to have the models of demon's souls with the correct skeleton? Now I no longer know who to ask
## Post #54
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-08-18T18:13:32+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dibe91
>
> But is there a chance to have the models of demon's souls with the correct skeleton? Now I no longer know who to ask
Some of them have correct skeleton - snakes example
I no know a way, I fix bones position in PMD editor (just because I use them in PMD/MMD and XNAlara, 3dsmaxis so slow for me)
## Post #55
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-08-18T18:27:05+00:00
- Post Title: Re: demon's souls FLV file

> Reply from TokiChan
>
> dibe91 wrote:But is there a chance to have the models of demon's souls with the correct skeleton? Now I no longer know who to ask
Some of them have correct skeleton - snakes example
I no know a way, I fix bones position in PMD editor (just because I use them in PMD/MMD and XNAlara, 3dsmaxis so slow for me)

thanks!
## Post #56
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-08-22T21:05:11+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dibe91
>
> 
thanks!
Welcome
## Post #57
- Username: MannyGames
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 15, 2018 10:15 pm
- Post datetime: 2018-04-15T14:56:24+00:00
- Post Title: Re: demon's souls FLV file

Hi do you guys know anywhere where I could get a flver file import for Noesis? Thanks.
## Post #58
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-04-30T13:59:55+00:00
- Post Title: Re: demon's souls FLV file

> Reply from MannyGames
>
> Hi do you guys know anywhere where I could get a flver file import for Noesis? Thanks.

For Demon's souls that no exist. Only textures TPF plugin for noesis. Models can be imported only with 3ds max scripts.
For ds1 flver importing you can find here [https://forum.xentax.com/viewtopic.php?f=16&t=7876](https://forum.xentax.com/viewtopic.php?f=16&t=7876)
## Post #59
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-10-02T22:02:16+00:00
- Post Title: Re: demon's souls FLV file

Hi,its probably too naive to ask but could somebody please fix script or make new one for noesis for map models? They work but it only extract's lightmap uv's and i need actual uv's of model. Also material support would be cool too but uv's are main thing.

Here is example map files: [https://mega.nz/#F!glEAECBC!4NRDPaknzYtl9Ouf6akU7Q](https://mega.nz/#F!glEAECBC!4NRDPaknzYtl9Ouf6akU7Q)

I hope someone could help,there is no other way i know to extract map meshes.
## Post #60
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-03T06:37:13+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dropoff
>
> there is no other way i know to extract map meshes.



m0000b0-flver-WordUV.jpg (206.96 KiB) Viewed 107 times


(stuck to WordUV again after having tried HF_UV)
## Post #61
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-10-04T05:00:46+00:00
- Post Title: Re: demon's souls FLV file

> Reply from shakotay2
>
> dropoff wrote:there is no other way i know to extract map meshes.m0000b0-flver.jpg
Thanks,but its probably gonna take one eternity to import all map models with hex2obj.
## Post #62
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-04T09:41:02+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dropoff
>
> Thanks,but its probably gonna take one eternity to import all map models with hex2obj.You didn't get the idea - it's not intended to use hex2obj for such; it's just a helper tool to get a clues.

To understand the format. After having created ONE submesh of the format you usually start to write a script or use the Make_obj project.

But I guess you have to wait until someone does this for you.
Good luck.
## Post #63
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-10-04T10:54:57+00:00
- Post Title: Re: demon's souls FLV file

> Reply from shakotay2
>
> dropoff wrote:Thanks,but its probably gonna take one eternity to import all map models with hex2obj.You didn't get the idea - it's not intended to use hex2obj for such; it's just a helper tool to get a clues.

To understand the format. After having created ONE submesh of the format you usually start to write a script or use the Make_obj project.

But I guess you have to wait until someone does this for you.
Good luck.
Yeah,idk how to do it unfortunately.
## Post #64
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-10-07T19:00:40+00:00
- Post Title: Re: demon's souls FLV file

I can even load map models on correct coordinates now but need correct uvs
## Post #65
- Username: Bazza
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 31, 2019 1:15 pm
- Post datetime: 2019-01-31T05:46:26+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dropoff
>
> I can even load map models on correct coordinates now but need correct uvs
Have you had any luck with the map extraction?

Also, good to see so much attention on this gem of a game!
## Post #66
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-01-31T11:14:24+00:00
- Post Title: Re: demon's souls FLV file

> Reply from Bazza
>
> dropoff wrote:I can even load map models on correct coordinates now but need correct uvs

Have you had any luck with the map extraction?

Also, good to see so much attention on this gem of a game!
Yes, i have small tool based on library for souls games files.

P.S. i will probably post it here when i would have motivation to finish it.
## Post #67
- Username: Bazza
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 31, 2019 1:15 pm
- Post datetime: 2019-01-31T13:09:57+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dropoff
>
> Bazza wrote:dropoff wrote:I can even load map models on correct coordinates now but need correct uvs

Have you had any luck with the map extraction?

Also, good to see so much attention on this gem of a game!
Yes, i have small tool based on library for souls games files.

P.S. i will probably post it here when i would have motivation to finish it.
Cool!

I want to do a HD remake of the Nexus, like in the PS3 background theme as a screensaver.
## Post #68
- Username: Bazza
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 31, 2019 1:15 pm
- Post datetime: 2019-02-05T03:47:09+00:00
- Post Title: Re: demon's souls FLV file

I found the penetrator knight as well, his arena would also be great for a HD remake shot!

Gotta say though, the original texture resolution leaves a lot to be desired.  I get that it's on the PS3 as a near-launch title, and practices then weren't what they ended up with at the end of the lifecycle, but it's 100% the limiting factor here 



pen_test_scene.jpg (77.48 KiB) Viewed 265 times
## Post #69
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-02-09T19:52:57+00:00
- Post Title: Re: demon's souls FLV file

There's been progress on the map meshes? That's amazing news.

Do not forget that the DeS meshes come out mirrored by the way.
## Post #70
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-09T21:12:29+00:00
- Post Title: Re: demon's souls FLV file

> Reply from Portugalotaku
>
> There's been progress on the map meshes?Dunno about people's motivation so guess you've to wait if you don't try it for yourself.



m0000b0_3SMs.jpg (149.88 KiB) Viewed 249 times


(uvs need some thresholding I guess)
## Post #71
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-02-09T23:16:23+00:00
- Post Title: Re: demon's souls FLV file

I did try for myself, 2 years ago, but did not get very far.
[latria.png](https://xentaxbackup.github.io/file/15693_latria.png)
## Post #72
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-10T07:02:43+00:00
- Post Title: Re: demon's souls FLV file

> Reply from Portugalotaku
>
> I did try for myself, 2 years ago, but did not get very far.That's a matter of motivation. Most people in this forum want things to be done by someone else.
You did try it for yourself.   Great! Why not continue it?

I'd suggest to learn/understand maxscript (since you seemed to use 3dsmax).

Maxscript is the most powerful and a rather simple approach for getting 3D models imho.
There's a hurdle for beginners (as always) but in the end it's a matter of motivation.

(Sadly I don't have a working installation of 3dsmax: I tend to use good software for years and don't like to install new student versions frequently.)

btw: it would be rather simple (basic understanding of 'C' required, though) to use my Make_obj project for getting those maps.

Even simpler is the use of hex2obj of course;
here's five H2O files for m0000b0.flver:

0x1200 813
Vb1
32 24
0x1860 257
121110
0x0 255

0x3880 867
Vb1
32 24
0x3F60 273
121310
0x0 255

0x6180 318
Vb1
36 24
0x6400 169
121310
0x0 255

0x7BE0 359
Vb1
36 24
0x7F20 150
121310
0x0 255

0x9440 4160
Vb1
32 24
0xB4C0 2404
121310
0x0 255

-------------------------------------------

m3100b0.flver



m3100b0.png (86.29 KiB) Viewed 225 times


(WordUVs look as if they were the better choice.)
## Post #73
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-02-10T10:56:23+00:00
- Post Title: Re: demon's souls FLV file

I stopped last time from a combination of lack of time and not wishing to bother people further. I am currently busy with other projects as well, I just happened to notice the updates on this thread while browsing and was surprised that progress had been made.

I appreciate the offer, but I do not have the time to learn those right now with how many things I have to work on.

Do tell me something though; these UVs for the world meshes you showed, they are correct?
## Post #74
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-10T11:19:17+00:00
- Post Title: Re: demon's souls FLV file

> Reply from Portugalotaku
>
> Do tell me something though; these UVs for the world meshes you showed, they are correct?Put a texture onto the mesh and you'll see. (As I wrote a threshold has to be applied to uv data in some cases but I'm too busy for such.)
## Post #75
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-02-10T11:43:09+00:00
- Post Title: Re: demon's souls FLV file

Here is tool for converting map flvers to obj, with all materials and correct uvs (most of them), still have problem with some models that dont have lightmap uvs i believe.
Made using soulsformats c# library made by TKGP. [https://github.com/JKAnderson/SoulsFormats](https://github.com/JKAnderson/SoulsFormats)

Usage: run tool and put path to folder with flvers you want to convert.
[DeS_flver2obj.rar](https://xentaxbackup.github.io/file/15697_DeS_flver2obj.rar)
## Post #76
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-10T12:10:50+00:00
- Post Title: Re: demon's souls FLV file

cool!  
Here's a python script (blender versions 2.5x and greater) for multi obj import:

```
import bpy

# http://blender.stackexchange.com/questions/5064/batch-import-wavefront-obj
# put the location to the folder where the objs are located here in this fashion
# this line will only work on windows ie C:\objects
#path_to_obj_dir = os.path.join('C:\\', 'objects')
path_to_obj_dir = os.path.join('X:\\', 'path_to_flver.obj')

# get list of all files in directory
file_list = sorted(os.listdir(path_to_obj_dir))

# get a list of files ending in 'obj'
obj_list = [item for item in file_list if item[-3:] == 'obj']

# loop through the strings in obj_list and add the files to the scene
for item in obj_list:
    path_to_file = os.path.join(path_to_obj_dir, item)
    bpy.ops.import_scene.obj(filepath = path_to_file)
```
replace 'X' with your drive letter and path_to_flver.obj with your .obj path.
You'll need \\ (instead of single \) for each sub directory.
## Post #77
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-02-10T14:47:43+00:00
- Post Title: Re: demon's souls FLV file

Cool, also btw, map models usually placed at right position after import, they misplaced only in tutorial level which is m08.
## Post #78
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-02-10T19:41:22+00:00
- Post Title: Re: demon's souls FLV file

All DeS models come out mirrored for me, I assume that is the problem you are having?
## Post #79
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-02-10T23:45:55+00:00
- Post Title: Re: demon's souls FLV file

> Reply from Portugalotaku
>
> All DeS models come out mirrored for me, I assume that is the problem you are having?
Hm it should be ok, tool mirrors them by x when converting. And no, its not a problem at all.
## Post #80
- Username: Bazza
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 31, 2019 1:15 pm
- Post datetime: 2019-02-14T07:03:21+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dropoff
>
> Here is tool for converting map flvers to obj, with all materials and correct uvs (most of them), still have problem with some models that dont have lightmap uvs i believe.
Made using soulsformats c# library made by TKGP. https://github.com/JKAnderson/SoulsFormats

Usage: run tool and put path to folder with flvers you want to convert.

This is amazing!

It gets the models to OBJ pretty much instantly.  Doesn't get textures as far as I can tell though.

Is it supposed to close after one action though?  success or fail, the next key pressed closes the app?
## Post #81
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-02-14T08:37:44+00:00
- Post Title: Re: demon's souls FLV file

> Reply from Bazza
>
> dropoff wrote:Here is tool for converting map flvers to obj, with all materials and correct uvs (most of them), still have problem with some models that dont have lightmap uvs i believe.
Made using soulsformats c# library made by TKGP. https://github.com/JKAnderson/SoulsFormats

Usage: run tool and put path to folder with flvers you want to convert.

This is amazing!

It gets the models to OBJ pretty much instantly.  Doesn't get textures as far as I can tell though.

Is it supposed to close after one action though?  success or fail, the next key pressed closes the app?
You need to extract textures by yourself, it only does models. Also idk, never tried to press key while it works, it will say when conversion done.
## Post #82
- Username: Bazza
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 31, 2019 1:15 pm
- Post datetime: 2019-02-15T00:46:42+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dropoff
>
> 
You need to extract textures by yourself, it only does models. Also idk, never tried to press key while it works, it will say when conversion done.
After it's done I mean.  Success or fail, once it's completed one folder, it closes as soon as you press anything.

Wasn't sure if it's a bug, or if you just re-open the app to do the next folder.

EDIT:

I'm having a lot of trouble with the 'SoulsFormats' project; the enums  in the script BinaryReaderEx.cs are coming up with "Constraint cannot be special class 'Enum'" and the build fails.  Is there some setup guide or similar for opening/building/importing this?
## Post #83
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-02-15T08:32:57+00:00
- Post Title: Re: demon's souls FLV file

> Reply from Bazza
>
> dropoff wrote:
You need to extract textures by yourself, it only does models. Also idk, never tried to press key while it works, it will say when conversion done.
After it's done I mean.  Success or fail, once it's completed one folder, it closes as soon as you press anything.

Wasn't sure if it's a bug, or if you just re-open the app to do the next folder.

EDIT:

I'm having a lot of trouble with the 'SoulsFormats' project; the enums  in the script BinaryReaderEx.cs are coming up with "Constraint cannot be special class 'Enum'" and the build fails.  Is there some setup guide or similar for opening/building/importing this?
It only works with 1 folder, so subfolders doesnt work and yeah after its done you need to run it again for other folder. Also you can ask author of soulsformats (TKGP) about it in souls modding discord server: [https://discord.gg/mT2JJjx](https://discord.gg/mT2JJjx)
## Post #84
- Username: Bazza
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 31, 2019 1:15 pm
- Post datetime: 2019-02-25T06:59:29+00:00
- Post Title: Re: demon's souls FLV file

Quick thanks here to the lads who've been helping both here and on the discord.

I've got the nexus in-engine, and have been rebuilding all the FX and lighting as I go along; candles, messages, bloodstains, etc....

May thine work help the world be mended    



the real demons souls starts here small.jpg (82.97 KiB) Viewed 145 times
## Post #85
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-04-05T09:34:49+00:00
- Post Title: Re: demon's souls FLV file

> Reply from Bazza ↑Mon Feb 25, 2019 2:59 pm at Mon Feb 25, 2019 2:59 pm
>
> 
Quick thanks here to the lads who've been helping both here and on the discord.

I've got the nexus in-engine, and have been rebuilding all the FX and lighting as I go along; candles, messages, bloodstains, etc....

May thine work help the world be mended    

the real demons souls starts here small.jpg

So cool!
Can u send me stages that you get? I no have luck with my comp for dems maps.
Without fx and lights - I'll use it in keyshot
## Post #86
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-04-05T16:26:58+00:00
- Post Title: Re: demon's souls FLV file

> Reply from TokiChan ↑Fri Apr 05, 2019 5:34 pm at Fri Apr 05, 2019 5:34 pm
>
> 
Bazza wrote: ↑Mon Feb 25, 2019 2:59 pm
Quick thanks here to the lads who've been helping both here and on the discord.

I've got the nexus in-engine, and have been rebuilding all the FX and lighting as I go along; candles, messages, bloodstains, etc....

May thine work help the world be mended    

the real demons souls starts here small.jpg


So cool!
Can u send me stages that you get? I no have luck with my comp for dems maps.
Without fx and lights - I'll use it in keyshot
Just import map flvers
## Post #87
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-04-08T06:38:34+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dropoff ↑Sat Apr 06, 2019 12:26 am at Sat Apr 06, 2019 12:26 am
>
> 
TokiChan wrote: ↑Fri Apr 05, 2019 5:34 pm
Bazza wrote: ↑Mon Feb 25, 2019 2:59 pm
Quick thanks here to the lads who've been helping both here and on the discord.

I've got the nexus in-engine, and have been rebuilding all the FX and lighting as I go along; candles, messages, bloodstains, etc....

May thine work help the world be mended    

the real demons souls starts here small.jpg


So cool!
Can u send me stages that you get? I no have luck with my comp for dems maps.
Without fx and lights - I'll use it in keyshot

Just import map flvers

All +100500 files with map fragments? And then put textures in all one by one? I'll dead.
## Post #88
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-04-08T16:28:59+00:00
- Post Title: Re: demon's souls FLV file

> Reply from TokiChan ↑Mon Apr 08, 2019 2:38 pm at Mon Apr 08, 2019 2:38 pm
>
> 
dropoff wrote: ↑Sat Apr 06, 2019 12:26 am
TokiChan wrote: ↑Fri Apr 05, 2019 5:34 pm


So cool!
Can u send me stages that you get? I no have luck with my comp for dems maps.
Without fx and lights - I'll use it in keyshot

Just import map flvers


All +100500 files with map fragments? And then put textures in all one by one? I'll dead.
But like with tool you dont need to apply all by hands, like all materials applied, you just need to set path to textures in 3ds max after import, idk how to do it in blender though.
## Post #89
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-06-04T15:52:16+00:00
- Post Title: Re: demon's souls FLV file

> Reply from dropoff ↑Tue Apr 09, 2019 12:28 am at Tue Apr 09, 2019 12:28 am
>
> 
TokiChan wrote: ↑Mon Apr 08, 2019 2:38 pm
dropoff wrote: ↑Sat Apr 06, 2019 12:26 am

Just import map flvers


All +100500 files with map fragments? And then put textures in all one by one? I'll dead.

But like with tool you dont need to apply all by hands, like all materials applied, you just need to set path to textures in 3ds max after import, idk how to do it in blender though.

How exactly did you import the maps with correct coordinates by the way? your converter is awesome but way too much stuff comes out of place for some maps.
## Post #90
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-06-06T14:55:09+00:00
- Post Title: Re: demon's souls FLV file

> Reply from Portugalotaku ↑Tue Jun 04, 2019 11:52 pm at Tue Jun 04, 2019 11:52 pm
>
> 
dropoff wrote: ↑Tue Apr 09, 2019 12:28 am
TokiChan wrote: ↑Mon Apr 08, 2019 2:38 pm


All +100500 files with map fragments? And then put textures in all one by one? I'll dead.

But like with tool you dont need to apply all by hands, like all materials applied, you just need to set path to textures in 3ds max after import, idk how to do it in blender though.


How exactly did you import the maps with correct coordinates by the way? your converter is awesome but way too much stuff comes out of place for some maps.
I just got coordinates from msb with msb editor and put into text file, then wrote simple max script to place models on them.
## Post #91
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2019-06-06T17:59:58+00:00
- Post Title: Re: demon's souls FLV file

Could you share that script?
## Post #92
- Username: LilSassy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 10, 2020 1:54 am
- Post datetime: 2020-12-09T18:53:49+00:00
- Post Title: Re: demon's souls FLV file

Nevermind, figured it out!
## Post #93
- Username: ZFPInTheAir
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 24, 2020 2:27 am
- Post datetime: 2021-09-11T20:30:13+00:00
- Post Title: Re: demon's souls FLV file

so im trying to get the warpstones or whatever they are called, and i have no idea what they are called

also cant get the textures to work with the Noesis scipt
## Post #94
- Username: BugzBunnysGhost
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 15, 2021 9:17 pm
- Post datetime: 2021-12-15T13:45:57+00:00
- Post Title: Re: demon's souls FLV file

hi i do not have 3ds max and im trying to unpack the .partsbnd.dcx file for the dragon bone smasher i would like to extract the model so i can make a mod for monster hunter world. this is my first time making a mod and i cant find a program that works. can someone point me in the right direction, or if they possibly have the model and texture files for the dragon bone smasher i would be really grateful.
## Post #95
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-07-19T13:43:56+00:00
- Post Title: Re: demon's souls FLV file

Hi, dudes!
Any process with Demon's souls remake?
