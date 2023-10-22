## Post #1
- Username: zaramot
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-01T09:45:43+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

Here is a version1 of a noesis script to import these models.
what is done
1.Geometry import
2.Uv sets assigned
3.textures are loaded but not assigned.
4.material creation and assignment
what is left.
2.reading in the model skeleton
3.assign bones and weights to the model.

DOA5 BMS

```
open FDSE "trial.lnk" 0
open FDSE "archive_order.bin" 1
goto 0x8 1
get files long 1
goto 0x24 1
savepos offset 1
for i = 0 < files
goto offset 1
get noff long 1
get arcnum long 1
get id long 1
savepos offset 1
goto noff 1
get name string 1
putarray 0 i name
next i
getarray name 0 0
putarray 0 files name
goto 0xC
get files long
get unk01 longlong
get unk02 longlong
for i = 0 < files
get offset longlong
get zsize longlong
get size longlong
get arc longlong
set id i
math id + 1
getarray name 0 id
if zsize == size
log name offset size
else
clog name offset zsize size
endif
next i

```


[fmt_DOA5_NG3_tmc1.4.rar](https://xentaxbackup.github.io/file/5482_fmt_DOA5_NG3_tmc1.4.rar)
## Post #2
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2012-05-01T09:51:18+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

Thanks! Is this for ps3 or xbox? I noticed NG3 is for both consoles.
## Post #3
- Username: synce
- Rank: n00b
- Number of posts: 12
- Joined date: Tue May 01, 2012 2:26 pm
- Post datetime: 2012-05-01T10:37:50+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

Pretty cool. I take it this only works for characters since I get this error with stages?
## Post #4
- Username: qq99q1
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Aug 01, 2011 2:51 pm
- Post datetime: 2012-05-01T10:43:31+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

The game is not

> No download links are allowed
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-01T11:31:46+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

ill look at the stages I have a feeling the textures are a different structure should not be to hard to fix.
## Post #6
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-05-01T17:35:38+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

Chrrox -- This is the best news I'll get all week most likely. You don't know how happy this makes me. For whatever reason, Ryu Hayabusa and the Ninja Gaiden series is a favorite for me. I hope knowing the joy you bring to people like me brings you satisfaction for the work you do. Big thanks.
## Post #7
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-05-01T19:41:26+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

Thanks chrrox

Just 2 issues:

1st.- some normal textures are no correctly extracted (I think it has to do with image seizes).
2nd.- I'm having problems when I try to load NG3's models.

[](http://imageshack.us/photo/my-images/806/tmcs.jpg/)

Uploaded with [ImageShack.us](http://imageshack.us)

See ya
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-01T20:14:19+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

i need specifics to help.
also i have updated the script in the first post to fix some image size issues.
stages in doa5 now load.
## Post #9
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-05-01T20:31:48+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

> Reply from chrrox
>
> i need specifics to help.
also i have updated the script in the first post to fix some image size issues.
stages in doa5 now load.

Ok, about the normal bumps:

[](http://imageshack.us/photo/my-images/9/htmbodynrmvlh2pp1.jpg/)

Uploaded with [ImageShack.us](http://imageshack.us)
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-01T20:45:31+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

that is how the normal map is. the normal maps are useless anyway in doa games they are just auto generated and contain no detail. i don't even know why they put them in the game.
what model are you loading in ng3.
## Post #11
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-05-01T20:53:16+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

chrrox -- I'm getting the same error message as Dark0. I've renamed the .gmd files to .tmc. I've tried with the files in r_ryu_a, r_aya_a. and r_ryu_e. 

EDIT: I've tried with several more and it's the same error each time.
## Post #12
- Username: synce
- Rank: n00b
- Number of posts: 12
- Joined date: Tue May 01, 2012 2:26 pm
- Post datetime: 2012-05-01T21:54:08+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

Stages extract perfectly now, thanks! 

I'm still very new to the world of modeling and animation, will 3DS Max's included tutorials teach me how to get a headless gray Ayane looking like OP screenshot or are there some additional tricks I need to know?
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-01T22:28:27+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

ok script 1.2 is uploaded let me know if anything breaks but ng3 models should load now.
## Post #14
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-05-01T23:14:51+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

The new version seems to work very well! I'm also getting normal maps just fine.

I'm still getting error messages with some models. It's the same error message as before, but the error is in line 60 or 69 instead of 66.
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-01T23:36:02+00:00
- Post Title: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis script.

what models give errors i need names.
## Post #16
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-05-02T01:09:39+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> ok script 1.2 is uploaded let me know if anything breaks but ng3 models should load now.

Thanks Chrrox again.

Just, what model is that??
## Post #17
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-05-02T01:20:22+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Darko -- That model is labeled C_MOM_A in the game files. 

Chrrox --E_BNI_A returns the error for line 69. E_CMF_A and E_LOA_A return the error for line 60. I'll get back to you with more specifics as I encounter them.
## Post #18
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-02T21:36:07+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Ok 1.3 should import all models found a good check to do i think let me know.
## Post #19
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-05-02T22:22:39+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> Ok 1.3 should import all models found a good check to do i think let me know.

Still getting the same error messages unfortunately. It seems to only affect three models though. Here is a pic:
## Post #20
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-05-02T22:59:10+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thanks again chrrox 

Just one question: what's the difference between NG3 models and NGS2 models??
## Post #21
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-02T23:06:21+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

it works fine for me make sure you updated your script and reloaded the plugins.
there is probably a lot different i am not really sure tho.
## Post #22
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2012-05-05T02:23:53+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

What script is are you guys using to extract files from NG3 .LNKs with correct names? When I try to use the BMS script from this topic [viewtopic.php?f=10&t=8589](http://forum.xentax.com/viewtopic.php?f=10&t=8589), I get an error.

I was definitely able to get it to work on the DOA5 alpha.
## Post #23
- Username: Chimera
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 24, 2011 11:31 pm
- Post datetime: 2012-05-05T07:32:03+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

hello, I downloaded the sample file the user Darko posted in another thread, it is renamed to .bin so i renamed it back to .lnk. Windows recognizes it as a shortcut file, I ignored this and I continued extracting with quickbms, but quickbms shows this error

Error: invalid datatype longlong at line 22 

any solutions for this ? ( I think quickbms didn't recognize the trial.lnk file )
## Post #24
- Username: Chimera
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-05T12:37:24+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

2 things you must rip the game from your own disc also your quickbms version is to old update it.
## Post #25
- Username: terios
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 14, 2010 10:24 am
- Post datetime: 2012-05-05T15:55:56+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I always walk away from your threads very impressed. Kudos on the awesome work. I do have a question though, you mention that textures are loaded but not assigned. Is it possible to manually assign them somehow in Noesis or did you have to export the model and textures and then put them together in Maya, per your screenshot in the OP? Thanks again!
## Post #26
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-05-05T18:05:14+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from terios
>
> I always walk away from your threads very impressed. Kudos on the awesome work. I do have a question though, you mention that textures are loaded but not assigned. Is it possible to manually assign them somehow in Noesis or did you have to export the model and textures and then put them together in Maya, per your screenshot in the OP? Thanks again!

Yep, it's possible to do that in data viewer.
## Post #27
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2012-05-06T18:27:30+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I still can't seem to get the BMS script to extract my common.lnk files from my disc.

When I use this code

```
open FDSE "trial.lnk" 0
open FDSE "archive_order.bin" 1
goto 0x8 1
get files long 1
goto 0x24 1
savepos offset 1
for i = 0 < files
goto offset 1
get noff long 1
get arcnum long 1
get id long 1
savepos offset 1
goto noff 1
get name string 1
putarray 0 id name
next i
goto 0xC
get files long
get unk01 longlong
get unk02 longlong
for i = 0 < files
get offset longlong
get zsize longlong
get size longlong
get arc longlong
getarray name 0 i
if zsize == size
log name offset size
else
clog name offset zsize size
endif
next i
```


I receive this error:

-error in src\file.h line 178: myfopen()
Error: no such file or directory.

I have the most current Quickbms, Any Advice?
## Post #28
- Username: Seyiji
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Sep 20, 2011 11:37 pm
- Post datetime: 2012-05-07T03:54:51+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Alexis
>
> I still can't seem to get the BMS script to extract my common.lnk files from my disc.

When I use this code
Code: Select allendian BIG
open FDSE "trial.lnk" 0
open FDSE "archive_order.bin" 1
goto 0x8 1
get files long 1
goto 0x24 1
savepos offset 1
for i = 0 < files
goto offset 1
get noff long 1
get arcnum long 1
get id long 1
savepos offset 1
goto noff 1
get name string 1
putarray 0 id name
next i
goto 0xC
get files long
get unk01 longlong
get unk02 longlong
for i = 0 < files
get offset longlong
get zsize longlong
get size longlong
get arc longlong
getarray name 0 i
if zsize == size
log name offset size
else
clog name offset zsize size
endif
next i

I receive this error:

-error in src\file.h line 178: myfopen()
Error: no such file or directory.

I have the most current Quickbms, Any Advice?You said your file is named common.lnk when the script expects the file to be named trial.lnk
## Post #29
- Username: zaramot
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-05-07T10:02:08+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

if your extracting ng3 this guy made an unpacker
[http://rghost.ru/37543470](http://rghost.ru/37543470)
## Post #30
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-05-09T11:53:13+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thank you very much "chrrox", you are Great.
## Post #31
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-05-16T02:26:19+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Lol The forum was offline for a day and half.

Anyways, is there any unpdate in the plugin chrrox??



See ya
## Post #32
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-06-01T06:29:56+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

anyone getting this error when trying to view the models:
## Post #33
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-06-01T14:00:59+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from inspiredgurl
>
> anyone getting this error when trying to view the models:


[img]http://img543.imageshack.us/img543/6057/messagex.png[/img

[img]http://img812.imageshack.us/img812/655/noesiserror.png[/img
rename TTGL to TMCL?
## Post #34
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-06-01T18:16:06+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rexil
>
> inspiredgurl wrote:anyone getting this error when trying to view the models:


[img]http://img543.imageshack.us/img543/6057/messagex.png[/img

[img]http://img812.imageshack.us/img812/655/noesiserror.png[/img
rename TTGL to TMCL?

i'm always missing something lol. thnx it works now.
## Post #35
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-02T13:43:44+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Materials are now set up in noesis in the 1.4 script.
also no need to rename files in ng3 folders.
## Post #36
- Username: Darko
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-03T01:25:13+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

here is a test build that works on most meshes to position the mesh pieces in the correct spots.

[fmt_DOA5_NG3_tmc1.4.1.rar](https://xentaxbackup.github.io/file/5483_fmt_DOA5_NG3_tmc1.4.1.rar)
## Post #37
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-06-03T03:33:33+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Awesome   

Thanks chrrox
## Post #38
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2012-06-03T11:06:57+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

nice work  thx u chrrox^^
## Post #39
- Username: urke1000
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jun 08, 2012 6:50 am
- Post datetime: 2012-06-08T03:05:22+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

First of all, big thanks for the script, however I'm a noob who only wants to load models in Noesis.

I have extracted the models with the bms script (DOA 5 alpha demo), put the noesis python script in plugins/python folder, and whenever I try to open .tmc file (e.g. located ....\CHARACTER\AYANE\COSTUME\COS_001\AYANE_COS_001.TMC) I get file could not be previewed error. I have python installed, noesis shows ng3/doa5 type in the list (plugin is accepted it seems)... What am I doing wrong?
## Post #40
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-08T16:43:25+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

what script did you use.
## Post #41
- Username: urke1000
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jun 08, 2012 6:50 am
- Post datetime: 2012-06-08T17:41:09+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I used this bms script (when a prompt for renaming/whatever comes, I hit R, and it apparently finishes correctly), but when time comes to actually open any of the character tmc's in noesis - can't be previewed and nothing more... If you're asking about the python script, it's your newest one, can't be a problem there. (of yeah, the quickbms application itself is also up to date, I think - v0.5.13)

> endian BIG
>
> open FDSE "trial.lnk" 0
>
> open FDSE "archive_order.bin" 1
>
> goto 0x8 1
>
> get files long 1
>
> goto 0x24 1
>
> savepos offset 1
>
> for i = 0 < files
>
> goto offset 1
>
> get noff long 1
>
> get arcnum long 1
>
> get id long 1
>
> savepos offset 1
>
> goto noff 1
>
> get name string 1
>
> putarray 0 i name
>
> next i
>
> getarray name 0 0
>
> putarray 0 files name
>
> goto 0xC
>
> get files long
>
> get unk01 longlong
>
> get unk02 longlong
>
> for i = 0 < files
>
> get offset longlong
>
> get zsize longlong
>
> get size longlong
>
> get arc longlong
>
> set id i
>
> math id + 1
>
> getarray name 0 id
>
> if zsize == size
>
> log name offset size
>
> else
>
> clog name offset zsize size
>
> endif
>
> next i
## Post #42
- Username: urke1000
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-08T17:50:47+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

use command prompt with quickbms.

c:\quickbms.exe c:\ng3.bms c:\trial.lnk c:\New-Folder

then try to open the models.
## Post #43
- Username: urke1000
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jun 08, 2012 6:50 am
- Post datetime: 2012-06-08T19:39:35+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

OK, that worked! Thank you again! New problem: I apparently don't know how to load more than one model at the same time, I miss head (and also seen that face and hair is separated too), only model that loads as a whole is Ryu, but I guess that's because of his design.
Even when I load face, there are some strange things, like part of Hitomi's face missing (only on one side), Ayane has no eyes (or they are transparent I don't really know), screenshots: (So is there a way to load everything at once: body, face (aka head), hair?)

Come to think of it, by looking this thread, NG3 models are all in one piece, are they? Is it possible that DOA5 is different in that regard (body is kept in costumes folder and in equipment there are folders for head & hair separate models (oh and one model for wet hair too)
EDIT: but that Ayane in the OP is DOA5? So no way to piece it together in noesis?
## Post #44
- Username: terios
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 14, 2010 10:24 am
- Post datetime: 2012-06-10T06:10:11+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> here is a test build that works on most meshes to position the mesh pieces in the correct spots.
FYI, this build broke support for loading DOA5's stages. This is the error I get now:
## Post #45
- Username: urke1000
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jun 08, 2012 6:50 am
- Post datetime: 2012-06-10T20:37:41+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Any chance for ps3 version ng3 models to load, I always get this when trying  to open them:
## Post #46
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-10T21:16:51+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from urke1000
>
> Any chance for ps3 version ng3 models to load, I always get this when trying  to open them:

ps3 files will never be supported.
## Post #47
- Username: THESIERRAMAN
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Jun 06, 2012 4:31 am
- Post datetime: 2012-06-11T17:27:13+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

HELLO GUYS IM THE SIERRA MAN, AND  IM NEW IN THE FORUM. I WOULD LIKE TO LEARN HOW TO EXTRACT ALL THE MODELS OF NINJA GAIDEN 3. I READED YOUR POST GUYS AND I SAW SOMETHING CALLED "NOESIS" BUT I DONT KNOW WHERE IT IS FOR DOWNLOAD? AND ¿¿¿NEED I KNOW HOW TO PROGRAMM IN PYTHON???, SOMEONE CAN HELP ME.
## Post #48
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-06-11T18:34:20+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

From below link you can download Neosis

[http://oasis.xentax.com/index.php?content=downloads](http://oasis.xentax.com/index.php?content=downloads)
## Post #49
- Username: THESIERRAMAN
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Jun 06, 2012 4:31 am
- Post datetime: 2012-06-14T19:44:49+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

HELLO GUYS!!!

I HAVE A SITUATION FOR RESOLVE

I have NINJA GAIDEN SIGMA 2 FOR PS3 in my pc (not original), and i would like to extract the models, music and scenarios, and im trying to open the archives, but i dont know how.

Can someone tell me what program I need for open these archives (ps3 archives) and extract the models for 3ds max studio 2010 please???

THANKS FOR YOUR ATTENTION. 

PD: THANKS "blackfoxeye"
## Post #50
- Username: Tommy345
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 16, 2012 5:02 pm
- Post datetime: 2012-06-16T09:12:37+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

blackfoxeye
thanks for the link!
## Post #51
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2012-07-18T14:54:46+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

does this script work for Ninja Gaiden Sigma 2 gmd files? how different are the models between ninja gaiden sigma 2 and ninja gaiden 3 models?

I am still hoping rachel's model could be extracted someday.
## Post #52
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-07-18T22:11:43+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from MuffinMan123
>
> does this script work for Ninja Gaiden Sigma 2 gmd files? how different are the models between ninja gaiden sigma 2 and ninja gaiden 3 models?

I am still hoping rachel's model could be extracted someday.

No, It doesn't work on those files.
## Post #53
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-07-20T01:53:10+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> MuffinMan123 wrote:does this script work for Ninja Gaiden Sigma 2 gmd files? how different are the models between ninja gaiden sigma 2 and ninja gaiden 3 models?

I am still hoping rachel's model could be extracted someday.

No, It doesn't work on those files.

Furthermore, why do you need to work with the Sigma models? There is a noesis plugin for NG2 that works perfectly and Rachel's model is easily accessible.
## Post #54
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2012-07-20T04:39:06+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from dragbody
>
> There is a noesis plugin for NG2 that works perfectly and Rachel's model is easily accessible.

NG2 does not have Rachel, you would know if you played the game.
Rachel only appeared in Ninja Gaiden 1, Sigma 1, and Sigma 2.
Read my post again, I am looking for reading Sigma 2 format.

Only Rachel's Ninja Gaiden 1 model is easily accessible, but the design is almost 10 years old.
## Post #55
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-07-20T17:05:00+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from MuffinMan123
>
> 
NG2 does not have Rachel, you would know if you played the game.
Rachel only appeared in Ninja Gaiden 1, Sigma 1, and Sigma 2.
Read my post again, I am looking for reading Sigma 2 format.

Only Rachel's Ninja Gaiden 1 model is easily accessible, but the design is almost 10 years old.

Ahhh, I was confusing Rachel with Sonia. How can you access NG1 models? I've got them unpacked, but I don't know how to convert them.
## Post #56
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2012-07-21T07:13:55+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I found someone ripped it and put it online. I got the 3dmax format and xnalara version both from xnalara forum, but it's almost 10 years old and it looks pretty bad compare to the updated sigma 1&2 counterparts.
## Post #57
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2012-07-21T22:11:29+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I guess we will have to wait for this if we still want to get updated rachel...
[http://the-magicbox.com/1205/game120509c.shtml](http://the-magicbox.com/1205/game120509c.shtml)
## Post #58
- Username: sandman420
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 25, 2012 5:23 am
- Post datetime: 2012-07-24T21:29:18+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Does anyone have a reader for this that works on iMac?
## Post #59
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2012-08-15T17:10:36+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

can you replace textures to mod? I can make all girls nude!
## Post #60
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-21T08:08:54+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Well the game was "released" and it seems the bms script works. The thing is I'm getting ascii characters weird nameds in the extracted files and try to indentify them in a hex program is gonna be a pain in the ass.
## Post #61
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-09-21T17:01:44+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

i can confirm what darko said.

i have tried to extract files from the final version of chara_common.lnk /.bin the result is one directory of files like:
"BU1E7@1S100C@H1A1]]233723D1U1QRF1410N10{S75131I"
"BS873@1S100@C]H]623G1EN12PQ31098N10{R821I"
"BR1E7@1S100C@H1A1]]233723D1U1QRF1410N10{S75131I"

etc.

would be awesome if someone could adapt the script to the final version of DoA 5.

i can upload files if needed but only via pm
## Post #62
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-21T22:13:57+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I'm leaving this here:
Well suppousedly  We can't upload game files, but anyways I don't think this is of some real use. If there's a problem feel free to delete the link or I can do it.
## Post #63
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-21T22:31:09+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

best way to get the models for now is to dump the ram of a jtag unit with the model you want on screen.
if someone sends me a ram dump ill look at making a bms to extract the models from it.
## Post #64
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-21T22:38:16+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> best way to get the models for now is to dump the ram of a jtag unit with the model you want on screen.
if someone sends me a ram dump ill look at making a bms to extract the models from it.

Lol Thanks for the response, but what about the files you get with the first script, are they usefull??
## Post #65
- Username: Itze
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-21T22:53:28+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

nope they completely changed their archive format and model format.


Edit.
I found a way to get the model files grouped togather so we can extract a complete model but they are doing something i did not even think was allowed.
they are using the ps3 edge sdk on the 360 port.
and they are using the bit level compression it offers for the face data.
## Post #66
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2012-09-22T00:56:56+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> nope they completely changed their archive format and model format.


Edit.
I found a way to get the model files grouped togather so we can extract a complete model but they are doing something i did not even think was allowed.
they are using the ps3 edge sdk on the 360 port.
and they are using the bit level compression it offers for the face data.

Does using PS Edge make extraction impossible? (Forgive my ignorance, It seems many PS3 model formats have yet to be cracked)
## Post #67
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-22T01:25:21+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

no it is not impossible it is being worked on.
## Post #68
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-09-22T08:10:56+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

@chrrox i have a jtag and i could make a ramdump but im not interested in getting the models on pc...

im more interested in extracting and reinjecting the textures to the game... if you know what i mean
## Post #69
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-22T11:01:59+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

sure send me the ram dump and tell me what chars are on screen.
## Post #70
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-09-23T08:45:55+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Umm... How open .bin files?
## Post #71
- Username: terios
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 14, 2010 10:24 am
- Post datetime: 2012-09-23T09:23:32+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> nope they completely changed their archive format and model format.
I don't believe they changed the archive format "completely." The old QuickBMS script does indeed properly extract the files. The actual contents aren't scrambled once extracted, just the file names except for "archivename.order," which seems to be the key in unscrambling these properly[.](http://home.comcast.net/~doa6/doa5_jannlee_cos01.png)
## Post #72
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-09-23T09:57:05+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

chrrox is working on it, give it some time
## Post #73
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-09-23T14:25:37+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Why in Noesis models have automatically matched textures but in 3ds max I have to add them manually? Is there any way to load them automatically?
## Post #74
- Username: JayK
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-23T16:10:44+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

team ninja has been defeated. I will have the files extracted with names in no time.
just working on how to xor with the xor key except when the value in the file is 00.

if anyone wants the xor key here it is.

> Except as expressly authorized, it is strictly prohibited to reproduce, distribute, exhibit or modify this software and any of its contents, including audio and visual contents. By way of example, to capture, copy or download any of the contents in this software, including audio and visual contents, onto any hardware or other software source media for any purpose, by the Internet or any other source, is strictly prohibited. Reversed engineering, decompiling or disassembly of this software is also strictly prohibited.
## Post #75
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-09-23T16:44:40+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

lol thats the key they xor the files with? haha good work   

i hope my files were helpful and you achieve your goal soon
## Post #76
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-09-23T18:03:37+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Good news, that key is quite humourous, what is your general workflow to finding out xor keys? some of the skill you guys have really amazes me, I hope one day I can learn enough and hopefully become as good at this.
## Post #77
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-09-23T20:22:07+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Kamillho
>
> Why in Noesis models have automatically matched textures but in 3ds max I have to add them manually? Is there any way to load them automatically?

help?
## Post #78
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-23T21:33:53+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> Good news, that key is quite humourous, what is your general workflow to finding out xor keys? some of the skill you guys have really amazes me, I hope one day I can learn enough and hopefully become as good at this.

If you look for a key that generates lots of 0xFF you may see some components of the words. There are programs to find large xor keys but they really don't work with video game data since 0 bytes usually come in pairs of four and aligned to a dword boundary, something these programs don't consider. A lot of these programs just check for key that generates maximum 0 bytes which is why ninja skipped 0's. But it should work also by checking FFs.

Amazing Chris could find it with those 0 holes in the file though.
## Post #79
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-09-23T21:57:31+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thank you! That's very useful advice, I appreciate it
## Post #80
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-23T22:33:42+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Kamillho
>
> Why in Noesis models have automatically matched textures but in 3ds max I have to add them manually? Is there any way to load them automatically?

mmm... As far as I know, It only exports the meshes with the name of diffuse textures. I don't know if using the material option  "-objmtl" for .obj is usefull in this case.

See ya
## Post #81
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-24T10:31:32+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

and also lol at "Reversed engineering" kind of an odd term
## Post #82
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-09-24T13:17:36+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

so any news already? can't wait to start modding
## Post #83
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-09-24T19:26:54+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Itze
>
> so any news already? can't wait to start modding

yeah me to
## Post #84
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-24T19:35:13+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> so any news already? can't wait to start modding 
>
> yeah me to

Same thing here
## Post #85
- Username: JayK
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-25T23:34:11+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Just need to finish calculating the texture size then it should be good to go guys.
the extractor i make might not be the fastest bms script but you only need to extract the files once so.
## Post #86
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-09-25T23:39:17+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

omg coooooool chrrox!!!
## Post #87
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-09-25T23:41:54+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

omg! are you using windows 8 chrrox or is it just a skin for w7?
## Post #88
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-26T06:27:47+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I cant wait chrrox!  Is it possible to add bone support? Just asking lol, its not needed, just wondering
## Post #89
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-09-26T10:12:53+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Awesome! 
Will it be possible to inject again with quickbms injection mode or is more work required?
## Post #90
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-26T11:20:12+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

a repacker will need to be made to reinject the files back into the game.
I am experimenting with this with a few people.
## Post #91
- Username: zaykho
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-26T23:30:10+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

very very close just working on calculating the tx3d textures (animated normal maps) and ill have a new script that should work.
anyone good with image format reversing who wants to look just ask lol.
## Post #92
- Username: terios
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 14, 2010 10:24 am
- Post datetime: 2012-09-26T23:41:54+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Does what you have work on the all models? I know I was asking about some models that were giving me issue with the currently available tools. Awesome work, as always.
## Post #93
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-26T23:46:58+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Excellent chrrox !!!

I just need to buy the game now  

PS: What is the best version for 3d rip ?  the XBOX 360 ? the PS3 ? or it's the same for all ?
## Post #94
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-27T00:06:23+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> Excellent chrrox !!!

I just need to buy the game now  

PS: What is the best version for 3d rip ?  the XBOX 360 ? the PS3 ? or it's the same for all ?

360 version, at least that's what he always says.

See ya
## Post #95
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-27T01:06:03+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Ok !! thank you again Darko !!

;p
## Post #96
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-09-27T03:11:01+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Excellent work chrrox   
i hope you!!
## Post #97
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-27T07:18:01+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

chrrox your amazing!  Cant wait to get my hands on the models.
BTW, which file are they in? I have chara_common.bin but thats small, im guessing its the chara_common.ink file? And will stages be supported?
## Post #98
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-09-27T09:59:32+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

And what about NG3? Will be any possibility to extract models with bones from game?
## Post #99
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-09-28T18:04:49+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> very very close just working on calculating the tx3d textures (animated normal maps) and ill have a new script that should work.
anyone good with image format reversing who wants to look just ask lol.

Thank you very much chrrox, you are awesome 
Eagerly waiting for the new script.
## Post #100
- Username: terios
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 14, 2010 10:24 am
- Post datetime: 2012-09-28T22:29:52+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from terios
>
> .
Was hoping someone would've noticed this little thing.
## Post #101
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-29T12:16:34+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thank's Chrrox.

Testing now  :p
## Post #102
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-29T12:30:07+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Very thanks Chroxx!
## Post #103
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-09-29T12:35:57+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

omg great works!!
thx relese
## Post #104
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-09-29T13:25:40+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Are the faces separated?
## Post #105
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-09-29T16:03:29+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

this is bug?


debug log..
-------------------------
Detected file type: Dead Or Alive 5
[['TX2D', 480, 52, 184], ['TX2D', 532, 52, 208], ['TX2D', 584, 52, 232], ['TX2D', 636, 52, 255], ['TX2D', 688, 52, 283], ['TX2D', 740, 52, 310], ['TX2D', 792, 52, 337], ['TX3D', 844, 52, 359], ['TX2D', 896, 52, 393], ['TX2D', 948, 52, 416], ['TX2D', 1000, 52, 440]]
0
0
0
3
3
3
3
0
2
2
3
[[[0, 2761657, 0], [12, 2761104, 196608], [16, 1712262, 65536], [20, 1712774, 131072], [24, 2892639, 327680]], [[0, 2761657, 0], [12, 2761104, 196608], [16, 1712262, 65536], [20, 1712774, 131072], [24, 1712992, 327680]], [[0, 2761657, 0], [12, 2761104, 196608], [16, 1712262, 65536], [20, 1712774, 131072], [24, 1712519, 393216], [28, 1712992, 327680], [36, 2892639, 327936]], [[0, 2761657, 0], [12, 2761104, 196608], [16, 1712262, 65536], [20, 1712774, 131072], [24, 1712519, 393216], [28, 1712992, 327680], [36, 1712992, 327936]]]
[[0, 10840, 4860, 28], [1, 3795, 1678, 32], [2, 5820, 3121, 40], [3, 13006, 5853, 44]]
[[[0, 2761657, 0], [12, 2761104, 196608], [16, 1712262, 65536], [20, 1712774, 131072], [24, 1712519, 393216], [28, 1712992, 327680], [36, 2892639, 327936]]]
[[4, 124, 60, 40]]
Generating normals for 3708 vertices...
Generating normals for 442 vertices...
Generating normals for 1236 vertices...
Generating normals for 318 vertices...
Generating normals for 2803 vertices...
Generating normals for 5853 vertices...
Generating normals for 1152 vertices...
Generating normals for 60 vertices...
-------------------------
## Post #106
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-29T16:11:10+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

mmm... I don't know if I'm doing this correctly but I'm getting this:



Problems with textures or sometimes Noesis craches.

See ya.
## Post #107
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-29T16:21:13+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Yeah something in the script python is incorrect.
## Post #108
- Username: sophist82
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-29T16:22:40+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

looks like something is wrong i got no problems here.
i used these 2 files
2R151@1S100A@S1]]J3372K52CQRE1410N10{S75131G = AYANE_COS_001.TMC
BR161@1S100B@S1]]2J372K42E1QRE1100N10{S65131G = AYANE_COS_001.TMCL


mabee it got corrupted on upload try this one.
[Model List 002.zip](https://xentaxbackup.github.io/file/5853_Model List 002.zip)

[doa5_360.zip](https://xentaxbackup.github.io/file/5852_doa5_360.zip)
## Post #109
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-29T16:32:16+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> mabee it got corrupted on upload try this one.
>
> 
>
> 
>
> Attachments:
>
> Model List 002.zip [3.15 KiB]
>
> 
>
> Downloaded 3 times
>
> doa5_360.zip [3.39 KiB]
>
> 
>
> Downloaded 6 times

Thank's Chrrox it's work good with this one.

I have just something weird with the eyes.


[](http://www.hostingpics.net/viewer.php?id=840511Sanstitre2.jpg)
## Post #110
- Username: zaykho
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-29T16:35:00+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

its just transparency settings.
also this script does not position mesh pieces if they are out of position still working on stuff.
## Post #111
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-29T16:40:04+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Well yes, I have just exported to Milkshape 3D and it work good. :p

I thought the eye are disappeared since the "transparency button" have disappeared too.

In milkshape 3d, choosing "Depth sorted by triangles" correct this  

PS: Just to know, does anybody will work on the Bone & Animation ? I know I ask a lot, but I know a lot of people will be happy to have this.
## Post #112
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-29T16:41:09+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

The reason for my error was that I didn't have the TMCL file in the along with the TMC file. Resulting in python looking for something that did not exist anyways it works fine =)
## Post #113
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-29T16:58:46+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Hi again !

I have another question, what is the "default" format of the texture on DOA5, .dds, .tga ?

Since my Noesis export all texture in .PNG, and I don't think this is the "default" format, right ?

It must be .DDS no ?

(I say this because I got no texture face)
## Post #114
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-29T17:09:19+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> Hi again !

I have another question, what is the "default" format of the texture on DOA5, .dds, .tga ?

Since my Noesis export all texture in .PNG, and I don't think this is the "default" format, right ?

It must be .DDS no ?

(I say this because I got no texture face)

Yeah its dds its shown in the python extraction script.
## Post #115
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-29T17:15:25+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Yeah its dds its shown in the python extraction script.

Strange since I can't get the .DDS, for me, the only way to get all textures it's to check the .jpg export.  :/

I have downloaded the latest NOESIS version and nothing change. :/
## Post #116
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-29T17:16:32+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

noesis does not export to dds just use tga it should work fine.
## Post #117
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-29T17:25:30+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> noesis does not export to dds just use tga it should work fine.

Ok Thank's, but it's strange since I have exported all DOAX2 models in .obj + .dds.
the "default" setting of Noesis always export in .dds, but not here.

So for now I must export all .tga, then convert to .dds, then convert to .png, because webgl work only with .png.
And the .png extracted from noesis are bugged.....
## Post #118
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-29T19:00:25+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> noesis does not export to dds just use tga it should work fine.

Ok Thank's, but it's strange since I have exported all DOAX2 models in .obj + .dds.
the "default" setting of Noesis always export in .dds, but not here.

So for now I must export all .tga, then convert to .dds, then convert to .png, because webgl work only with .png.
And the .png extracted from noesis are bugged.....

Huh?? Export to tga and then convert to png with whatever program you want.

See ya.
## Post #119
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2012-09-29T20:39:44+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I'm confused... Did you compile two different model lists? 

I ask because one list is labeled 002, and in some of the screens posted there is a 001
## Post #120
- Username: sophist82
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 21, 2012 11:39 pm
- Post datetime: 2012-09-29T20:42:00+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I am already feeling happy with the models, but would be much better with bones/joint bind in it. 
Will it be hard to have those??
## Post #121
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-29T21:20:10+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Alexis
>
> I'm confused... Did you compile two different model lists? 

I ask because one list is labeled 002, and in some of the screens posted there is a 001
One list is updated. so 002 is a updated list.
## Post #122
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-29T21:25:43+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Who i can extract files chara_common.bin from DOA5?

Or where are the script for quickbm for extract this?
## Post #123
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-29T21:40:15+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

its in the game archive section
[viewtopic.php?f=10&t=9685](http://forum.xentax.com/viewtopic.php?f=10&t=9685)
[Model List 003.zip](https://xentaxbackup.github.io/file/5854_Model List 003.zip)
## Post #124
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-29T22:53:16+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thanks chrox!

Now i have many files .dec, what i must have do now?
## Post #125
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-29T23:24:46+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I wrote a python script to rename the files using charrox version 3 of the model files.

I had to make some corrections to what charrox gave me, in the mapping dictionary.

for one he didn't fill out Lisas files and I checked and couldn't figure out if the first set was TMC or TMCL so I went with his pattern of thought and the first set of Lisa costumes will be TMC and the second set are TMCL, as well I ran into the issue with hyabusa boss cos or what ever I choose TMC first then TMCL.

The python script works like this.
in command prompt
doa5file-rename.py -s C:\absolute\path\to\decrypted\files\ -d C:\abolute\path\to\existing\folder\ -b C:\absolute\path\to\doa5-name-dictionary-v3.txt

make sure the -d path actually exists!!

Notice that the path names for -d and -s end with a \ its required.
and ensure to find the dictionary add the file extension.
Note:This will copy and rename the files to another destination. Also if you must rerun it again delete the destination folder create another destination folder to replace it, otherwise python buggs out, Why the bugs? I am new to python =) I am a c/c++ developer =P

So I can't seem to attach downloads so
copy and paste the source code and put it in a .py file and run it from command line.

To add to your dictionary

it goes

crazysymbolsthatmakenosensetoanyone = KASUMI_COS_2.TMC
crazysymbolsthatmakenosensetoanyone = KASUMI_COS_2.TMCL

and so on ensure that there are file extensions or it will bug out my example dictionary is below along with the source.


```
Dead Or Alive 5 File Mapping Renamer. 1.0
Usage: 
Type the following into the windows cmd as administrator.
Using the absolute path to the src and dest.
doa5file-rename.py -s C:\\Location\\to\\decrypted\\char\\bin\\lnk\\files.dec -d C:\\Location\\to\\place\\where\\files\\are\\renamed\\and\\placed\\for\\TMC\\and\\TMCL\\ -b C:\\Location\\To\\where\\dictionary\\is\\dictionary.txt
Ensure that all path names end with a \\ except for the path to the dictionary. And ensure that there exists a path to the destination.
otherwise the script may bug out I am not a python developer just yet :P
"""
import sys
import getopt
import os
import shutil
def getListOfFiles(srcDir):
    strListOfFiles = os.listdir(srcDir)
    #for strFile in strListOfFiles:
        #print strFile
    return strListOfFiles

def ensureDirectoryExists(desDir):
    print desDir
    desDirPossibility = os.path.dirname(desDir)
    print desDirPossibility
    if not os.path.exists(desDirPossibility):
        option = raw_input("Create Directory? y/n ")
        if option == "y":
            os.makedirs(desDirPossibility)
        else:
            print "Directory does not exist"
            sys.exit(0)
def contains(string,checkedElements):
    for c in checkedElements:
        if c in string:
            return 1
        else:
            return 0
        
def searchAndMatch(strListOfFiles,strListOfDictFiles,strPathToSrc,strPathToDest):
    # if a match was found then copy and and rename
    for filename in strListOfFiles:
        # Check dictionary if it contains that value
        if filename in strListOfDictFiles:
            copyAndRename(strPathToSrc,strPathToDest,filename,strListOfDictFiles[filename])
    return

def copyAndRename(strPathToSrc,strPathToDest,filename,strNewName):
    #debug
    print strPathToSrc+filename
    print strPathToDest+filename
    print strPathToDest+strNewName

    shutil.copy((strPathToSrc+filename),(strPathToDest+filename))
    os.rename((strPathToDest+filename),(strPathToDest+strNewName))
    return

def parseDictionary(pathToDicSymbolsToCharacterFileName):
    fileObj = open(pathToDicSymbolsToCharacterFileName)
    dicSymToCharFileName = {}
    for line in fileObj:
        if not line == '\n':
            if contains(line,'-'):
                listOfKeyValue = line.split('-',1)    
                dicSymToCharFileName[listOfKeyValue[0].strip()+".dec"] = listOfKeyValue[1].strip()
            if contains(line,'='):
                listOfKeyValue = line.split('=',1)
                dicSymToCharFileName[listOfKeyValue[0].strip()+".dec"] = listOfKeyValue[1].strip()
    return dicSymToCharFileName

def RenameProcess(strSrc,strDest,dicPath):
    ensureDirectoryExists(strDest)
    dictSymToCharFileName = parseDictionary(dicPath)
    fileList = getListOfFiles(strSrc)
    searchAndMatch(fileList,dictSymToCharFileName,strSrc,strDest)
    
    return
def main(argv):
    # parse command line options
    dest = ''
    src = ''
    dicPath = ''
    
    try:
        opts,args = getopt.getopt(argv,"b:s:d:h",["help","src=","dest=","dic="])
    except:
        print __doc__
    for opt,arg in opts:
        if opt in ('-h','--help'):
            print __doc__
        elif opt in ('-d','--dest'):
            print "Destination"
            dest = arg
        elif opt in ('-s','--src'):
            print "Source"
            src = arg
            #getListOfFiles(arg)
        elif opt in ('-b','--dic'):
            print "Get Dictonary"
            dictPath = arg
            #parseDictionary(arg)
    RenameProcess(src,dest,dictPath)
    
if __name__ == "__main__":
    # Call the main function with the everything after the 1 offset, the first argument is the script name
    # and we don't want that.
    main(sys.argv[1:])


```


```
2411J8_J91]]4H515A146]20OI161CMEI221L{O4 = AKIRA_FACE.TMC

2R11K@1S100B@M31]]4K424B83QK1B100COHK22100N{QG15 = AKIRA_HAIR_001.TMC

2R115@1S100A@L]]3J44724BI1A1PQ510J1N10{R7216 = AKIRA_COS_001.TMC
2S115@1S100A@L]]3J44724BI1A1PQ510J1N10{R7216 = AKIRA_COS_002.TMC

BR116@1S100B@L]]33J4723DJ1A13PQ310K1N10{R7216 = AKIRA_COS_001.TMCL
BS116@1S100B@L]]33J4723DJ1A13PQ310K1N10{R7216 = AKIRA_COS_002.TMCL

241SK31V1T1B_21B1]]J814C145]20N1R61E2EM1K3N{QK = ALPHA152_FACE.TMC
2R1SL@1T10051W141D@2100]]L323CO1B4SB100D2HN1L321O{RS1L = ALHA152_HAIR_001.TMC
2R1S6@1T10051W141C@21]]K33924CN1A1RS510N1P10{T721J = ALPHA152_COS_001.TMC
Ayane
241IJ9_91P1]]]1JB15C146K1633PDN81CG1J3HN126{P81716 = AYANE_BOSS_FACE.TMC

2R1JK@1S100C@21S1]]61L424M1D23RE1DP00IH1L321IP128{R81S1917 = AYANE_BOSS_HAIR_001.TMC

2R1J6@1S100B@S1]]61K44013L1DQRF1G1510GO10002{286131I11 = AYANE_BOSS_COS_001.TMC

2410J8_81P1]]H914A1I563]30PDM81CI29{O004 = AYANE_FACE.TMC

2R15K@1S100B@21S1]]K3L343D94RE1DO00FK221A{Q41R16 = AYANE_HAIR_001.TMC

2R151@1S100A@S1]]J3372K52CQRE1410N10{S75131G = AYANE_COS_001.TMC
2S151@1S100A@S1]]J3372K52CQRE1410N10{S75131G = AYANE_COS_002.TMC
2T151@1S100A@S1]]J3372K52CQRE1410N10{S75131G = AYANE_COS_003.TMC
2U151@1S100A@S1]]J3372K52CQRE1410N10{S75131G = AYANE_COS_004.TMC
2V151@1S100A@S1]]J3372K52CQRE1410N10{S75131G = AYANE_COS_005.TMC
2W151@1S100A@S1]]J3372K52CQRE1410N10{S75131G = AYANE_COS_006.TMC

BR161@1S100B@S1]]2J372K42E1QRE1100N10{S65131G = AYANE_COS_001.TMCL
BS161@1S100B@S1]]2J372K42E1QRE1100N10{S65131G = AYANE_COS_002.TMCL
BT161@1S100B@S1]]2J372K42E1QRE1100N10{S65131G = AYANE_COS_003.TMCL
BU161@1S100B@S1]]2J372K42E1QRE1100N10{S65131G = AYANE_COS_004.TMCL
BV161@1S100B@S1]]2J372K42E1QRE1100N10{S65131G = AYANE_COS_005.TMCL
BW161@1S100B@S1]]2J372K42E1QRE1100N10{S65131G = AYANE_COS_006.TMCL


241IJ9_9181]]HA14B145]20OCMBH2FA12L{O4 = BASS_FACE.TMC

200IJ@1R100B@313181]]J323B63PA1BNFI221F212M{PQ1W16 = BASS_HAIR_001_A.TMC

2R1JK@1S100C@2191]]K323C83QD1COGJ221G212N{QR15 = BASS_HAIR_001.TMC

2R1J6@1S100B@91]]J33724CPQ310DE1N103{27210 = BASS_COS_001.TMC


2J1E69_F181]]333]2451BS11PD1410C1L10P1B1{2771G41 = BAYMAN_COS_TEST.TMC

241DJ9_91F191]]3A14B145]20OS1DM8C2I3G{O614 = BAYMAN_FACE.TMC

2R1EK@1S100C@21I1A1]]3323C83QD1U1DO3H2K321H{Q61R15 = BAYMAN_HAIR_001.TMC

2R1E6@1S100B@H1A1]]333724CU1QRF1510N10{S75131I = BAYMAN_COS_001.TMC
2S1E6@1S100B@H1A1]]333724CU1QRF1510N10{S75131I = BAYMAN_COS_002.TMC
2T1E6@1S100B@H1A1]]333724CU1QRF1510N10{S75131I = BAYMAN_COS_003.TMC
2U1E6@1S100B@H1A1]]333724CU1QRF1510N10{S75131I = BAYMAN_COS_004.TMC
2V1E6@1S100B@H1A1]]333724CU1QRF1510N10{S75131I = BAYMAN_COS_005.TMC

BR1E7@1S100C@H1A1]]233723D1U1QRF1410N10{S75131I = BAYMAN_COS_001.TMCL
BS1E7@1S100C@H1A1]]233723D1U1QRF1410N10{S75131I = BAYMAN_COS_002.TMCL
BT1E7@1S100C@H1A1]]233723D1U1QRF1410N10{S75131I = BAYMAN_COS_003.TMCL
BU1E7@1S100C@H1A1]]233723D1U1QRF1410N10{S75131I = BAYMAN_COS_004.TMCL
BV1E7@1S100C@H1A1]]233723D1U1QRF1410N10{S75131I = BAYMAN_COS_005.TMCL

2414J8_81J1]]HA1400B145]20OCMBH2G1L{OJ = BRAD_FACE.TMC

2R14K@1S100B@M131]]K3B134C93Q00COGJ2H131N{QG1K = BRAD_HAIR_001.TMC

2R145@1S100A@L1]]J3372B15CPQ310F1N10{R721I = BRAD_COS_001.TMC
2S145@1S100A@L1]]J3372B15CPQ310F1N10{R721I = BRAD_COS_002.TMC
2T145@1S100A@L1]]J3372B15CPQ310F1N10{R721I = BRAD_COS_003.TMC
2U145@1S100A@L1]]J3372B15CPQ310F1N10{R721I = BRAD_COS_004.TMC
2V145@1S100A@L1]]J3372B15CPQ310F1N10{R721I = BRAD_COS_005.TMC

BR156@1S100B@L1]]2J372B14E1PQ000G1N10{R621I = BRAD_COS_001.TMCL
BS156@1S100B@L1]]2J372B14E1PQ000G1N10{R621I = BRAD_COS_002.TMCL
BT156@1S100B@L1]]2J372B14E1PQ000G1N10{R621I = BRAD_COS_003.TMCL
BU156@1S100B@L1]]2J372B14E1PQ000G1N10{R621I = BRAD_COS_004.TMCL
BV156@1S100B@L1]]2J372B14E1PQ000G1N10{R621I = BRAD_COS_005.TMCL


2410J_981E61]1]91D643]3000B1ON11MC82D131LO1{P7 = CHRISTIE_FACE.TMC

2R15K@1S100@C10H]1]G433C8431A1QD1P12OFA2C13100NQ1{R617 = CHRISTIE_HAIR_001.TMC
2004J@1R100@B3121G]1]F433B6431A1PB1O12NEA2C13100MP1{Q61W18 = CHRISTIE_HAIR_001_A.TMC

2R151@1S100@BG]1]160F52B10P1O11Q310A161N10Q1{0600F = CHRISTIE_COS_001.TMC
2S151@1S100@BG]1]160F52B10P1O11Q310A161N10Q1{0600F = CHRISTIE_COS_002.TMC
2T151@1S100@BG]1]160F52B10P1O11Q310A161N10Q1{0600F = CHRISTIE_COS_003.TMC
2U151@1S100@BG]1]160F52B10P1O11Q310A161N10Q1{0600F = CHRISTIE_COS_004.TMC
2V151@1S100@BG]1]160F52B10P1O11Q310A161N10Q1{0600F = CHRISTIE_COS_005.TMC
2W151@1S100@BG]1]160F52B10P1O11Q310A161N10Q1{0600F = CHRISTIE_COS_006.TMC

BR161@1S100@C]1]I262G42D10P1O122Q310A161N10Q1{0800F = CHRISTIE_COS_001.TMCL
BS161@1S100@C]1]I262G42D10P1O122Q310A161N10Q1{0800F = CHRISTIE_COS_002.TMCL
BT161@1S100@C]1]I262G42D10P1O122Q310A161N10Q1{0800F = CHRISTIE_COS_003.TMCL
BU161@1S100@C]1]I262G42D10P1O122Q310A161N10Q1{0800F = CHRISTIE_COS_004.TMCL
BV161@1S100@C]1]I262G42D10P1O122Q310A161N10Q1{0800F = CHRISTIE_COS_005.TMCL
BW161@1S100@C]1]I262G42D10P1O122Q310A161N10Q1{0800F = CHRISTIE_COS_006.TMCL




241J1_981E61]812]52]20H1OC1AL0H101LL{3N7 = ELIOT_FACE.TMC

2R1K1@1S100@C10H]1]32A73J1QC1F1CN0J10100NN{3PQ18 = ELIOT_HAIR_001.TMC

2RK63@1S100@CH]]62443BJ1B1CQ510I1M100{R07212 = ELIOT_COS_001.TMC


24KK3_A91F21]91C15]]2J1736DDLE10H02{EN28 = GENFU_FACE.TMC

2RL2L@1S100@D10I]F13]L153D93DB1CNH10J0115{KP2Q1A = GENFU_HAIR_001.TMC

2RL63@1S100@CH]]624F1K165DQEE1410M10{RK82318 = GENFU_COS_001.TMC


24IJ3_A91P131@1H51]B14]B163363P0NDF1I3GN12NE1{P00716 = HAYATE_BOSS_FACE.TMC

241J0_981P131F71]9925]4]3563P6MCH2L00{O004 = HAYATE_FACE.TMC

2R5K3@1S100@C10S110I]93]3C9462RB17OEJ221N21{Q00R16 = HAYATE_HAIR_001.TMC

2R512@1S100@BS121H]]72Q52C654R510N10E1{S70021F = HAYATE_COS_001.TMC
2S512@1S100@BS121H]]72Q52C654R510N10E1{S70021F = HAYATE_COS_002.TMC
2T512@1S100@BS121H]]72Q52C654R510N10E1{S70021F = HAYATE_COS_003.TMC
2U512@1S100@BS121H]]72Q52C654R510N10E1{S70021F = HAYATE_COS_004.TMC

BR612@1S100@CS121]I]72Q42E6534R310N10E1{S70021F = HAYATE_COS_001.TMCL
BS612@1S100@CS121]I]72Q42E6534R310N10E1{S70021F = HAYATE_COS_002.TMCL
BT612@1S100@CS121]I]72Q42E6534R310N10E1{S70021F = HAYATE_COS_003.TMCL
BU612@1S100@CS121]I]72Q42E6534R310N10E1{S70021F = HAYATE_COS_004.TMCL

240J2_9F912F31]9161G16]]2573OC1DL000I0E{NF = HELENA_FACE.TMC

2R0K2@1S100@CI212I]00J13]C9362QB1G1EN000K011D{PQ18 = HELENA_HAIR_001.TMC
2S0K2@1S100@CI212I]00J13]C9362QB1G1EN000K011D{PQ18 = HELENA_HAIR_002.TMC

2R052@1S100@BH1H]]72461J1C76C1PQ00610M10{R621G = HELENA_COS_001.TMC
2S052@1S100@BH1H]]72461J1C76C1PQ00610M10{R621G = HELENA_COS_002.TMC
2T052@1S100@BH1H]]72461J1C76C1PQ00610M10{R621G = HELENA_COS_003.TMC
2U052@1S100@BH1H]]72461J1C76C1PQ00610M10{R621G = HELENA_COS_004.TMC
2V052@1S100@BH1H]]72461J1C76C1PQ00610M10{R621G = HELENA_COS_005.TMC

BR062@1S100@CH1]I]72361B1D763C1PQ00410M10{R621G = HELENA_COS_001.TMCL
BS062@1S100@CH1]I]72361B1D763C1PQ00410M10{R621G = HELENA_COS_002.TMCL
BT062@1S100@CH1]I]72361B1D763C1PQ00410M10{R621G = HELENA_COS_003.TMCL
BU062@1S100@CH1]I]72361B1D763C1PQ00410M10{R621G = HELENA_COS_004.TMCL
BV062@1S100@CH1]I]72361B1D763C1PQ00410M10{R621G = HELENA_COS_005.TMCL


248J3_A91E21]914]]20524O813BLL1D41E3L{41N0 = HITOMI_FACE.TMC

2R9K3@1S100@D10H]2]B73525Q91103BNN1H41F321N{00PQ11 = HITOMI_HAIR_001.TMC

2R963@1S100@CG]]624B544612PQM131810210{F1R5211 = HITOMI_COS_001.TMC


241J0_981B1E71]962F16]5]36O84J1EL00B1AJ23{N4 = JANNLEE_FACE.TMC

2R5K3@1S100@C10E1H]AI14]4DA4QC194L1FN0031AL2213{PQ16 = JANNLEE_HAIR_001.TMC

20411@1R100@A31C1F]]4295H13B76I1OP00E1710L10{Q721W1C = JANNLEE_COS_001_A.TMC
20411@1R100@A31C1F]]4295H13B76I1OP00E1710L10{Q721_1C = JANNLEE_COS_005_A.TMC

2R512@1S100@BD1G]]7285I13C76J1PQ00F1710M10{R721B = JANNLEE_COS_001.TMC
2S512@1S100@BD1G]]7285I13C76J1PQ00F1710M10{R721B = JANNLEE_COS_002.TMC
2T512@1S100@BD1G]]7285I13C76J1PQ00F1710M10{R721B = JANNLEE_COS_003.TMC
2U512@1S100@BD1G]]7285I13C76J1PQ00F1710M10{R721B = JANNLEE_COS_004.TMC
2V512@1S100@BD1G]]7285I13C76J1PQ00F1710M10{R721B = JANNLEE_COS_005.TMC

BR612@1S100@CE1]H]7284B13D763J1PQ00F1510M10{R721B = JANNLEE_COS_001.TMCL
BS612@1S100@CE1]H]7284B13D763J1PQ00F1510M10{R721B = JANNLEE_COS_002.TMCL
BT612@1S100@CE1]H]7284B13D763J1PQ00F1510M10{R721B = JANNLEE_COS_003.TMCL
BU612@1S100@CE1]H]7284B13D763J1PQ00F1510M10{R721B = JANNLEE_COS_004.TMCL
BV612@1S100@CE1]H]7284B13D763J1PQ00F1510M10{R721B = JANNLEE_COS_005.TMCL


248J3_A91C1E31]A14]]203O264CL61DE2A1K{NP17 = KASUMI_FACE.TMC

2R9K3@1S100@D10F1H]2]C834QA1375CN71HF22131M{PR1R16 = KASUMI_HAIR_001.TMC

24IJ3_A91D1@1G41]B14]520O4164CM61DF1I3GM1D13M{O41811 = KASUMI_BOSS_FACE.TMC

2RJ63@1S100@CF141H]]013C2144PQ10F1710FN10E1103{282100L11 = KASUMI_BOSS_COS_001.TMC
2SJ63@1S100@CF141H]]013C2144PQ10F1710FN10E1103{282100L11 = KASUMI_BOSS_COS_002.TMC

BRJ73@1S100@DG141]I]012E21444PQ10G1410FN10E1103{282100M11 = KASUMI_BOSS_COS_001.TMCL
BSJ73@1S100@DG141]I]012E21444PQ10G1410FN10E1103{282100M11 = KASUMI_BOSS_COS_002.TMCL

2R963@1S100@CE1G]]724C2154PQ10610MC121{R72100H = KASUMI_COS_001.TMC

24EJ3_A91F21]914]]20O63C1CLDNK1002J441M{O0 = KOKORO_FACE.TMC

2RFK3@1S100@D10I]2]B73Q9174C1CNGPM1002L44131O{Q715 = KOKORO_HAIR_001.TMC

2RF63@1S100@CH]]624B54B1PQPL100810331000{R7211 - KOKORO_COS_001.TMC
2SF63@1S100@CH]]624B54B1PQPL100810331000{R7211 - KOKORO_COS_002.TMC
2TF63@1S100@CH]]624B54B1PQPL100810331000{R7211 - KOKORO_COS_003.TMC
2UF63@1S100@CH]]624B54B1PQPL100810331000{R7211 - KOKORO_COS_004.TMC
2VF63@1S100@CH]]624B54B1PQPL100810331000{R7211 - KOKORO_COS_005.TMC
2WF63@1S100@CH]]624B54B1PQPL100810331000{R7211 - KOKORO_COS_006.TMC

BRF73@1S100@D]I]623D54B14PQPM100510331000{R7211 - KOKORO_COS_001.TMCL
BSF73@1S100@D]I]623D54B14PQPM100510331000{R7211 - KOKORO_COS_002.TMCL
BTF73@1S100@D]I]623D54B14PQPM100510331000{R7211 - KOKORO_COS_003.TMCL
BUF73@1S100@D]I]623D54B14PQPM100510331000{R7211 - KOKORO_COS_004.TMCL
BVF73@1S100@D]I]623D54B14PQPM100510331000{R7211 - KOKORO_COS_005.TMCL
BWF73@1S100@D]I]623D54B14PQPM100510331000{R7211 - KOKORO_COS_006.TMCL


240J2_9K912F31]914]]20OJ174DMEI221L{OE = LISA_FACE.TMC

2A0J2_AKA1F13031]2]A1]30OJ1818561DMHJ221B1L{O061 = LISA_FACE_MASK.TMC
2R0K2@1S100@CN212I]2]B83QA1L185DOHK22100N{QR1B = LISA_HAIR_001.TMC

2R052@1S100@BM1H]]724BJ165PQ610J1N10{9721F = LISA_COS_001.TMC
2S052@1S100@BM1H]]724BJ165PQ610J1N10{9721F = LISA_COS_002.TMC
2T052@1S100@BM1H]]724BJ165PQ610J1N10{9721F = LISA_COS_003.TMC
2U052@1S100@BM1H]]724BJ165PQ610J1N10{9721F = LISA_COS_004.TMC
2V052@1S100@BM1H]]724BJ165PQ610J1N10{9721F = LISA_COS_005.TMC
2W052@1S100@BM1H]]724BJ165PQ610J1N10{9721F = LISA_COS_006.TMC
2X052@1S100@BM1H]]724BJ165PQ610J1N10{9721F = LISA_COS_007.TMC

BR062@1S100@CM1]I]723DC1265PQ510J1N10{9721F = LISA_COS_001.TMCL
BS062@1S100@CM1]I]723DC1265PQ510J1N10{9721F = LISA_COS_002.TMCL
BT062@1S100@CM1]I]723DC1265PQ510J1N10{9721F = LISA_COS_003.TMCL
BU062@1S100@CM1]I]723DC1265PQ510J1N10{9721F = LISA_COS_004.TMCL
BV062@1S100@CM1]I]723DC1265PQ510J1N10{9721F = LISA_COS_005.TMCL
BW062@1S100@CM1]I]723DC1265PQ510J1N10{9721F = LISA_COS_006.TMCL
BX062@1S100@CM1]I]723DC1265PQ510J1N10{9721F = LISA_COS_007.TMCL


246J3_99100E21]91F15]]2F1I16C1OA7ELC11908{NI = LEIFANG_FACE.TMC

2R7K3@1S100@C10C1H]I13]H1K1FB5I1QE1B5GN005A2218{PQ1L = LEIFANG_HAIR_001.TMC

2R763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_001.TMC
2S763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_002.TMC
2T763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_003.TMC
2U763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_004.TMC
2V763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_005.TMC
2W763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_006.TMC
2X763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_007.TMC
2Y763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_008.TMC

BR873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_001.TMCL
BS873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_002.TMCL
BT873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_003.TMCL
BU873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_004.TMCL
BV873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_005.TMCL
BW873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_006.TMCL
BX873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_007.TMCL
BY873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_008.TMCL


240J2_9D912E31]914]]2031OG1DL97E01K{ND = MILA_FACE.TMC

2R0K2@1S100@CG212H]2]B8341QA1I1DNA8H0100M{PQ1A = MILA_HAIR_001.TMC
2S0K2@1S100@CG212H]2]B8341QA1I1DNA8H0100M{PQ1A = MILA_HAIR_002.TMC
200J0@1R100@B3F2313G]2]A7341PA1H1CMA8G0100L{OP1W1B = MILA_HAIR_001_A.TMC
230J2_9D91813@1F51]H14]D163041OH1FLA7A1H22B{N411 = MILA_FACE_BAND.TMC

BR0K2@1S100@D7212]I1]C8300QA15I1DNA8H0100M{PQ1A = MILA_HAIR_001.TMCL
BS0K2@1S100@D7212]I1]C8300QA15I1DNA8H0100M{PQ1A = MILA_HAIR_002.TMCL
B00J0@1R100@C362313]H1]B7300PA15H1CMA8G0100L{OP1W1B = MILA_HAIR_001_A.TMCL
B40J2_A591713@141]GH12]D163041O2H1FLA7A1H22B{N411 = MILA_FACE_BAND.TMCL

2R052@1S100@BF1G]]724B21G1PQ87710M10{R821F = MILA_COS_001.TMC
2S052@1S100@BF1G]]724B21G1PQ87710M10{R821F = MILA_COS_002.TMC
2T052@1S100@BF1G]]724B21G1PQ87710M10{R821F = MILA_COS_003.TMC
2U052@1S100@BF1G]]724B21G1PQ87710M10{R821F = MILA_COS_004.TMC
2V052@1S100@BF1G]]724B21G1PQ87710M10{R821F = MILA_COS_005.TMC
2W052@1S100@BF1G]]724B21G1PQ87710M10{R821F = MILA_COS_006.TMC
2Y052@1S100@BF1G]]724B21G1PQ87710M10{R821F = MILA_COS_008.TMC

BR062@1S100@C71]H]723C212G1PQ87610M10{R821F = MILA_COS_001.TMCL
BS062@1S100@C71]H]723C212G1PQ87610M10{R821F = MILA_COS_002.TMCL
BT062@1S100@C71]H]723C212G1PQ87610M10{R821F = MILA_COS_003.TMCL
BU062@1S100@C71]H]723C212G1PQ87610M10{R821F = MILA_COS_004.TMCL
BV062@1S100@C71]H]723C212G1PQ87610M10{R821F = MILA_COS_005.TMCL
BW062@1S100@C71]H]723C212G1PQ87610M10{R821F = MILA_COS_006.TMCL
BY062@1S100@C71]H]723C212G1PQ87610M10{R821F = MILA_COS_008.TMCL


248J3_A91H1F31]A14]]204O2C8C97D4K{N5 = PAI_FACE.TMC

2R9K3@1S100@DK212I]2]C839Q210C9GA7E421M{PQ11 = PAI_HAIR_001.TMC

2R963@1S100@CJ1H]]724C91PQ41087N10{R821H = PAI_COS_001.TMC


246J3_991E21]914]]2E11M1ODME62B8L{OI = RIG_FACE.TMC

2R763@1S100@BG]]624F1CN1PQ41098N10{R821I = RIG_COS_001.TMC

2SDK3@1S100@DC1861]3]B1930QC1N0GI2A7MP{2Q71E = RTM_FACE_002
2XDK3@1S100@DC1861]3]B1930QC1N0GI2A7MP{2Q71E = RTM_FACE_007

2RD63@1S100@C7]]624AP1Q031076M10P{2R721A = RTM_COS_001.TMC
2RD63@121S1@C7]]724AP1Q031076M10P{2R721A = RTM_COS_011.TMC
2SD63@1S100@C7]]624AP1Q031076M10P{2R721A = RTM_COS_002.TMC
2TD63@1S100@C7]]624AP1Q031076M10P{2R721A = RTM_COS_003.TMC
2UD63@1S100@C7]]624AP1Q031076M10P{2R721A = RTM_COS_004.TMC
2VD63@1S100@C7]]624AP1Q031076M10P{2R721A = RTM_COS_005.TMC
2WD63@1S100@C7]]624AP1Q031076M10P{2R721A = RTM_COS_006.TMC
2XD63@1S100@C7]]624AP1Q031076M10P{2R721A = RTM_COS_007.TMC

BRD73@1S100@D]8]623C1P1Q021076M10P{2R721A = RTM_COS_001.TMCL
BRD73@121S1@D]8]723C1P1Q021076M10P{2R721A = RTM_COS_011.TMCL
BSD73@1S100@D]8]623C1P1Q021076M10P{2R721A = RTM_COS_002.TMCL
BTD73@1S100@D]8]623C1P1Q021076M10P{2R721A = RTM_COS_003.TMCL
BUD73@1S100@D]8]623C1P1Q021076M10P{2R721A = RTM_COS_004.TMCL
BVD73@1S100@D]8]623C1P1Q021076M10P{2R721A = RTM_COS_005.TMCL
BWD73@1S100@D]8]623C1P1Q021076M10P{2R721A = RTM_COS_006.TMCL
BXD73@1S100@D]8]623C1P1Q021076M10P{2R721A = RTM_COS_007.TMCL


240J2_9KP1A141441G00]A13]]2052PDNEI251M{PJ1E10 = HAYABUSA_FACE.TMC

2RJ63@1S100@CS121815161I]]424C54QRF1610941O10003{27617141101 = HAYABUSA_BOSS_COS_001.TMC
BRJ73@1S100@DS121815161]J]423E543QRG1410941O10003{27617141101 = HAYABUSA_BOSS_COS_001.TMCL

2R052@1S100@BMS131361I]]924C54QR51021O10{B6H171411 = HAYABUSA_COS_001.TMC
2S052@1S100@BMS131361I]]924C54QR51021O10{B6H171411 = HAYABUSA_COS_002.TMC
2T052@1S100@BMS131361I]]924C54QR51021O10{B6H171411 = HAYABUSA_COS_003.TMC
2U052@1S100@BMS131361I]]924C54QR51021O10{B6H171411 = HAYABUSA_COS_004.TMC

BR062@1S100@CMS131361]J]923E543QR31021O10{B6I171411 = HAYABUSA_COS_001.TMCL
BS062@1S100@CMS131361]J]923E543QR31021O10{B6I171411 = HAYABUSA_COS_002.TMCL
BT062@1S100@CMS131361]J]923E543QR31021O10{B6I171411 = HAYABUSA_COS_003.TMCL
BU062@1S100@CMS131361]J]923E543QR31021O10{B6I171411 = HAYABUSA_COS_004.TMCL


247J3_481J1K1G41]A14]]2401ODNEI261A8M{PH = SARAH_FACE

2R8K3@1S100@6M121N1J]2]9CA44Q21DPHK20021B8O{RG1G = SARAH_HAIR_001.TMC

2R863@1S100@6L1M1I]]8249C2PQ4104187O10{6821D = SARAH_COS_001.TMC

240J2_9F912F31]914]]20B1O0LH1E01CB8{ND = TINA_FACE.TMC

2R0K2@1S100@CI212I]2]B83B1QB11NJ1H0100CC9{PQ1A = TINA_HAIR_001.TMC
2S0K2@1S100@CI212I]2]B83B1QB11NJ1H0100CC9{PQ1A = TINA_HAIR_002.TMC
200J0@1R100@B3H2313H]2]A73A1PB11MI1G0100CC9{OP1W1B = TINA_HAIR_001_A.TMC

BR0K2@1S100@DI212]J1]D83B1QB162NK1I0100CCA{PQ18 = TINA_HAIR_001.TMCL
BS0K2@1S100@DI212]J1]D83B1QB162NK1I0100CCA{PQ18 = TINA_HAIR_002.TMCL

2R052@1S100@BH1H]]724BP10QI1410M1098{R721F = TINA_COS_001.TMC
2S052@1S100@BH1H]]724BP10QI1410M1098{R721F = TINA_COS_002.TMC
2T052@1S100@BH1H]]724BP10QI1410M1098{R721F = TINA_COS_003.TMC
2U052@1S100@BH1H]]724BP10QI1410M1098{R721F = TINA_COS_004.TMC
2V052@1S100@BH1H]]724BP10QI1410M1098{R721F = TINA_COS_005.TMC
2W052@1S100@BH1H]]724BP10QI1410M1098{R721F = TINA_COS_006.TMC
2X052@1S100@BH1H]]724BP10QI1410M1098{R721F = TINA_COS_007.TMC

BR062@1S100@CH1]I]723DP120QJ1310M1098{R721F = TINA_COS_001.TMCL
BS062@1S100@CH1]I]723DP120QJ1310M1098{R721F = TINA_COS_002.TMCL
BT062@1S100@CH1]I]723DP120QJ1310M1098{R721F = TINA_COS_003.TMCL
BU062@1S100@CH1]I]723DP120QJ1310M1098{R721F = TINA_COS_004.TMCL
BV062@1S100@CH1]I]723DP120QJ1310M1098{R721F = TINA_COS_005.TMCL
BW062@1S100@CH1]I]723DP120QJ1310M1098{R721F = TINA_COS_006.TMCL
BX062@1S100@CH1]I]723DP120QJ1310M1098{R721F = TINA_COS_007.TMCL

24AJ3_A91Q1F31]00A14]]20P00CMDI2L{ODAI = ZACK_FACE.TMC

2RB63@1S100@CT1H]71]825C10QR000N10{S5B941H = ZACK_COS_001.TMC
2SB63@1S100@CT1H]71]825C10QR000N10{S5B941H = ZACK_COS_002.TMC
2TB63@1S100@CT1H]71]825C10QR000N10{S5B941H = ZACK_COS_003.TMC
2UB63@1S100@CT1H]71]825C10QR000N10{S5B941H = ZACK_COS_004.TMC
2VB63@1S100@CT1H]71]825C10QR000N10{S5B941H = ZACK_COS_005.TMC

BRC73@1S100@DT1]61I]823E100QR000N10{S5B941H = ZACK_COS_001.TMCL
BSC73@1S100@DT1]61I]823E100QR000N10{S5B941H = ZACK_COS_002.TMCL
BTC73@1S100@DT1]61I]823E100QR000N10{S5B941H = ZACK_COS_003.TMCL
BUC73@1S100@DT1]61I]823E100QR000N10{S5B941H = ZACK_COS_004.TMCL
BVC73@1S100@DT1]61I]823E100QR000N10{S5B941H = ZACK_COS_005.TMCL

```
## Post #126
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-09-29T23:40:34+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

some of the files are missing the .tmc or .tmcl file extension in that list :-/
## Post #127
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-29T23:43:46+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Very thanks i will try this.
## Post #128
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2012-09-30T00:31:05+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thank you for the scripts,
I get this though when I try to view heads or hair meshes, the bodies are fine, some still don't load though.
## Post #129
- Username: leonkennedy4011
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-30T00:35:06+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

you are missing the tmcl file that goes with those models.
just search for the last 5 characters of the original tmc file name and the tmcl file will show up in the search results.

I am opening this to the public if anyone wants to update this with the list i have or if anyone wants to add any changes.
I can work on finding new names but it would be good to pull together i think.
[https://docs.google.com/spreadsheet/ccc ... 2xhdFZ6eHc](https://docs.google.com/spreadsheet/ccc?key=0AjHfst1X766adG9NcmQ5LUQyNzNrR3RUZ2xhdFZ6eHc)

this is a list of names i pulled from the demo.
[names.zip](https://xentaxbackup.github.io/file/5858_names.zip)
## Post #130
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-09-30T00:41:45+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from GDL
>
> some of the files are missing the .tmc or .tmcl file extension in that list :-/
Yeah you have to fill them in your self a final version of the dictionary will come to light when this is all complete but yeah fix it and ill fix it when I get sometime to fix the script as well.
## Post #131
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-30T00:53:23+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Lol I got more than half of the characters I wanted with hxd and win7 folder search engine. I've been having problems with christie, tina and milla (hair, head or costumes).

Just look for the last characters using quotations and the search engine will throw a pair number of files. The 2's files are .tmc and the b's files are .tmcl. For the tmc files located at the beginning of your dec folder, just open them with any hex program and find what character and what costume is (normally you just need to find one file in order to find the rest of the files of one character), copy those characters of your dec files and do a search inside your folder adding quotations. The search is gonna throw normally a pair number of files. 

See ya.
## Post #132
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-30T02:32:53+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Huh?? Export to tga and then convert to png with whatever program you want.

Well I can't because I can only use a dds to png converter.

And, I have the same problem in noesis when exporting in .TGA, I can only get a proper face texture by exporting in .JPG.

(When I export to TGA, the face texture are transparent....) 

EDIT: The alpha with the texture are bugged.

here a sample in .tga and .jpg of ayane:
[http://www.mediafire.com/?ihz7d86bd2erh](http://www.mediafire.com/?ihz7d86bd2erh)

I PRECISE THAT THE SAMPLE COME FROM THE DEMO, not the retail game.
## Post #133
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-09-30T07:57:53+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

hi chrrox
KASUMI_COS_003.TMC is texture bug?
## Post #134
- Username: pceedeie98
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 17, 2012 12:36 am
- Post datetime: 2012-09-30T08:13:20+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> its in the game archive section
viewtopic.php?f=10&t=9685

HI

How to convert pictures taken during the matches in DOA5 into formats that can be recognized and used on a PC?

How to convert pictures (which are) taken during the matches in DOA5 into formats that can be recognized and used on a PC? 

look at



DOWNLOAD
[http://www.sendspace.com/file/i0pk41](http://www.sendspace.com/file/i0pk41)
[Snap1.jpg](https://xentaxbackup.github.io/file/5860_Snap1.jpg)
## Post #135
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2012-09-30T08:32:29+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from moge1975
>
> 

hi chrrox
KASUMI_COS_003.TMC is texture bug?

Thats not a texture bug its just flipped faces on the mesh.
## Post #136
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-09-30T09:00:54+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Thats not a texture bug its just flipped faces on the mesh.

oh... ok thx rep
## Post #137
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-09-30T10:19:17+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I'm slowly adding characters to that Excel file, hopefully will have most of them added by the end of today.
## Post #138
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2012-09-30T11:00:10+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

damn good progress guys   

@chrrox any news about reinjection of modified textures or maybe even models yet?
## Post #139
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-09-30T11:49:22+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Hm, for Brad's face, 2414J8_81J1]]HA1400B145]20OCMBH2G1L{OJ is the TMC file, I'm almost completely positive B515J9_91J1]]913H00D125]20O0CMBI2H1L{OJ should be the tmcl file. However, although with this combination it opens the file in Noesis, there is absolutely nothing displayed. I'll skip adding that tmcl number in the excel file for now.
## Post #140
- Username: sophist82
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 21, 2012 11:39 pm
- Post datetime: 2012-09-30T12:37:40+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Any chance of getting animationa data?? Anyone?
## Post #141
- Username: JayK
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-30T12:39:16+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

yeah there are a few meshes that are more like the ps3 format and have model data in the TMC file instead of the TMCl.
I need to add a check for them I am reworking my script right now to work on a few things like this.
## Post #142
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-09-30T12:40:34+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Ah interesting, in that case I'll still add them to the excel file, as im certain those are the correct tmcl files.
## Post #143
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-30T12:46:25+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

yeah you can tell its the correct file also by viewing the textures and they look correct.
## Post #144
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-09-30T12:56:13+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

"AKIRA_FACE" may be

2411J8_J91]]4H515A146]20OI161CMEI221L{O4.dec = AKIRA_FACE.TMC
B511J9_JA1]]4414HC126]20OJ1612CMEJ221L{O4.dec = AKIRA_FACE.TMCL

but noesis not loading...
## Post #145
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-30T14:02:05+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Hi all, i have a error in Noesis.

I did rename .dec to .TMC and outher file .TMCL and when i try open in noesis appear this:





AND THIS:
## Post #146
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-30T14:09:17+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

what file?
i tried a few of ayane's costumes and they all worked fine.
## Post #147
- Username: pceedeie98
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 17, 2012 12:36 am
- Post datetime: 2012-09-30T14:27:05+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> what file?
i tried a few of ayane's costumes and they all worked fine.
How do you convert the pictures that you take in DOA5 to PC format?


DOWNLOAD
[http://www.sendspace.com/file/i0pk41](http://www.sendspace.com/file/i0pk41)
## Post #148
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-30T14:38:51+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> what file?
i tried a few of ayane's costumes and they all worked fine.

AYANE_COS_01





I did convert files from xbox 360 version final, full.
## Post #149
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-30T14:53:37+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

nobody have problem with texture when exporting from noesis ?

Anyone have already imported in some 3d softwares ?
## Post #150
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-30T15:07:43+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> Huh?? Export to tga and then convert to png with whatever program you want.

Well I can't because I can only use a dds to png converter.

And, I have the same problem in noesis when exporting in .TGA, I can only get a proper face texture by exporting in .JPG.

(When I export to TGA, the face texture are transparent....) 

EDIT: The alpha with the texture are bugged.

here a sample in .tga and .jpg of ayane:
http://www.mediafire.com/?ihz7d86bd2erh

I PRECISE THAT THE SAMPLE COME FROM THE DEMO, not the retail game.

The alpha channel is the specular texture. I don't see any problem on it.
## Post #151
- Username: suishiqi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 19, 2012 1:52 am
- Post datetime: 2012-09-30T15:27:39+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

i have imported the model into maya,thanks for your great tools!
[ayane.jpg](https://xentaxbackup.github.io/file/5862_ayane.jpg)
## Post #152
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-30T15:30:30+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Anybody can help me please?

Ready the last messages from me please.
## Post #153
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-30T15:41:38+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> The alpha channel is the specular texture. I don't see any problem on it.

That's what I get:

.TGA:

[](http://www.hostingpics.net/viewer.php?id=208668thetgaone.jpg)

.PNG:

[](http://www.hostingpics.net/viewer.php?id=454563thepngone.jpg)

.JPG

[](http://www.hostingpics.net/viewer.php?id=695118thejpgone.jpg)



> i have imported the model into maya,thanks for your great tools!

Wow !!  nice one, ayane with glass is Kawaii :p

So you didn't get any problem with texture ? what format are you used ?
## Post #154
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-30T15:48:07+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

milkshape is a really bad program to use.
you need to use any program that supports texture channels.
just delete the alpha channel of the texture if your not going to use the specular map.
## Post #155
- Username: suishiqi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 19, 2012 1:52 am
- Post datetime: 2012-09-30T16:07:29+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

i drag the png into maya,and use the fcheck to save a tga file.
[ayane_texture.jpg](https://xentaxbackup.github.io/file/5864_ayane_texture.jpg)
## Post #156
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-30T16:22:14+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> milkshape is a really bad program to use.
>
> you need to use any program that supports texture channels.

Well it doesn't change for me, I have used 3DS Max 8, and maybe I forget something, but I get the same result:


Map imported without any change:

[](http://www.hostingpics.net/viewer.php?id=919216alpha.jpg)


Map imported and set to "opaque":

[](http://www.hostingpics.net/viewer.php?id=948849opaque.jpg)


The config panel:

[](http://www.hostingpics.net/viewer.php?id=377465desktop.jpg)


I begin to think my Noesis have a problem, I will try to clean all noesis registry part of the system, hope it will sove this. 


> i drag the png into maya,and use the fcheck to save a tga file.

Ok, I have maya but not installed, I will try on this one too later.
## Post #157
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-30T16:27:38+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thats how the textures are. They look transparent when you open the image file, you can easily convert the ones that dont need alpha channel to jpg.
## Post #158
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-30T16:28:41+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Chrrox, does your script support stages??
## Post #159
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-30T16:35:21+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Chrrox, does your script support stages??

Yes it does:

[](http://www.hostingpics.net/viewer.php?id=663716Sanstitre2.jpg)


> Thats how the textures are. They look transparent when you open the image file, you can easily convert the ones that dont need alpha channel to jpg.

Yes but I fair for Stage and Costume, delete all non-desired alpha on a stage level will take time lol...
## Post #160
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-30T16:41:26+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

When i extract files with first pluggin for quick, i extract file .Ink chara_common and after .bin, this are step correct?

[](http://imageshack.us/photo/my-images/850/dudelg.jpg/)

Uploaded with [ImageShack.us](http://imageshack.us)

When i have extract second file .bin i must have overwrite or press r in command quickbms?
## Post #161
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-30T16:50:04+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

@zaihko look your box inside message please!
## Post #162
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-09-30T16:58:54+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from pceedeie98
>
> chrrox wrote:what file?
i tried a few of ayane's costumes and they all worked fine.
How do you convert the pictures that you take in DOA5 to PC format?


DOWNLOAD
http://www.sendspace.com/file/i0pk41

[http://www.freestepdodge.com/threads/xb ... post-45445](http://www.freestepdodge.com/threads/xbox360-converting-doa5-screenshots.1503/#post-45445)
## Post #163
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-30T16:59:47+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

@logansan25

Yep sorry, I didn't notice :p
## Post #164
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-30T18:27:47+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> @logansan25

Yep sorry, I didn't notice :p

Very thanks Zaykho!

Look this thread:

[viewtopic.php?f=10&t=9685&start=45](http://forum.xentax.com/viewtopic.php?f=10&t=9685&start=45)
## Post #165
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-30T18:37:23+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Yes it great, it will be more easier with this
## Post #166
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-30T18:45:43+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Stages are pretty hard in the full game. Plus I get errors for it even tho I think I got the correct tmcl file, it says:
local variable 'tmclData' referenced before assignment
## Post #167
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-30T19:06:59+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Stages are pretty hard in the full game. Plus I get errors for it even tho I think I got the correct tmcl file, it says:
>
> local variable 'tmclData' referenced before assignment

Try different noesis script, I know that:

For best export face character I use 1.4.1
For best export costume character I use 1.5.0
For best export stage I use 1.5.0 & 1.3.0

I know the demo is different from the retail, but give a try :p

I have indexed all interesting tools for DOA 5 here:
[http://www.mediafire.com/?ihz7d86bd2erh](http://www.mediafire.com/?ihz7d86bd2erh) (then go to --> Tool)
or directly here:
[http://www.mediafire.com/?sbd2c9r8ok3u3](http://www.mediafire.com/?sbd2c9r8ok3u3)
## Post #168
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-30T19:10:47+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I fixed the error, although, I see no meshes.
## Post #169
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-09-30T20:09:43+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

7RW71@10T100006@T1]]V3317MMS3G1TE1100P10{U8H61I514.dec

Is it possible to create a BMS script to extract the high-resolution textures?
*.dds output
## Post #170
- Username: oranges283
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 05, 2010 6:24 am
- Post datetime: 2012-09-30T20:13:54+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Are the bunny bikinis on disk dlc?
## Post #171
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-09-30T20:16:07+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from oranges283
>
> Are the bunny bikinis on disk dlc?

DLC
## Post #172
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-30T20:16:52+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

A quick render of Helena with free long hair:



I really like how they look like .

See ya
## Post #173
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-30T20:20:12+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> I really like how they look like

Not me, I think they have totally deformed Lei-Fang (my favorite) , now Lei-Fang look like a monk.  :/
Now all characters have the same head, body.... Only eyes change, so what Tecmo ? all these years for that ?
The only character that I think is good now is ayane.....

Even those stages are ugly like shit.....


:/
## Post #174
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-09-30T22:07:29+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Chrrox's original spreadsheet has been updated and pretty much contains a full listing of tmc files and their tmcl counterparts now. not all the 2J* tmc files have been added as they're just COS_TEST files, but feel free to add them for completeness if you wish. Here's a link to the spreadsheet again;

[https://docs.google.com/spreadsheet/ccc ... 6eHc#gid=0](https://docs.google.com/spreadsheet/ccc?key=0AjHfst1X766adG9NcmQ5LUQyNzNrR3RUZ2xhdFZ6eHc#gid=0)
## Post #175
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2012-09-30T22:50:16+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Can we add a few tabs for Stage/Dlc/Items data? I'm going through them right now.
Or should we just add the Dlc data to the existing sheets?
## Post #176
- Username: kokuto
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 31, 2011 1:26 am
- Post datetime: 2012-09-30T22:58:10+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

>Akira's face, Brad's face, Rig's face
0x60 stride vbuf sets require improved logic
## Post #177
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-30T23:42:45+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

yeah feel free to add tabs.
## Post #178
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2012-10-01T01:17:12+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Alright cool, then I added all the DLC costume data and a bit of stage stuff.
## Post #179
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-01T03:12:46+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Try different noesis script, I know that:
>
> 
>
> For best export face character I use 1.4.1
>
> For best export costume character I use 1.5.0
>
> For best export stage I use 1.5.0 & 1.3.0
>
> 
>
> I know the demo is different from the retail, but give a try :p
>
> 
>
> I have indexed all interesting tools for DOA 5 here:
>
> http://www.mediafire.com/?ihz7d86bd2erh (then go to --> Tool)
>
> or directly here:
>
> http://www.mediafire.com/?sbd2c9r8ok3u3
EDIT: now this folder is THE ULTIMATE TOOL FOLDER for Dead Or Alive & Ninja Gaiden, enjoy !!

[http://www.mediafire.com/?sbd2c9r8ok3u3](http://www.mediafire.com/?sbd2c9r8ok3u3)

***If I have missed some tool, let me know !
## Post #180
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-01T04:12:10+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from moge1975
>
> 

7RW71@10T100006@T1]]V3317MMS3G1TE1100P10{U8H61I514.dec

Is it possible to create a BMS script to extract the high-resolution textures?
*.dds output

I don't understand, they are 2 different resolution texture ? it's strange, Team-Ninja doesn't like to work this way......
## Post #181
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-10-01T07:39:22+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> I don't understand, they are 2 different resolution texture ? it's strange, Team-Ninja doesn't like to work this way......


ok,please this see


2U963@1S100@CE1G]]724C2154PQ10610MC121{R72100H.dec = KASUMI_COS_004.TMC
BUA73@1S100@DF1]H]723E21544PQ10310MC121{R72100H.dec = KASUMI_COS_004.TMCL

TMC,TMCL file into "low-resolution textures"
kas_04_base_01.dds = 64 x 64pix
kas_04_base_04.dds = 64 x 64pix
kas_04_nrm_04.dds = 64 x 64pix
kas_04_wet_base_01.dds = 64 x 64pix


-----------------------------------------------------------------------------------

Anticipation high-resolution textures

color1
7R97U@10T10000@8F1S]]17KRG13163S10410OD121{T921HH00I.dec = Texture information file
BRA7U@10T10000@EG1]T]17KRH131739S10510OD121{TA21HH00I.dec = dds file "high-res"

color2
7S97U@10T10000@8F1S]]17KRG13163S10410OD121{T921HH00I.dec = Texture information file
BSA7U@10T10000@EG1]T]17KRH131739S10510OD121{TA21HH00I.dec = dds file "high-res"

color3
7T97U@10T10000@8F1S]]17KRG13163S10410OD121{T921HH00I.dec = Texture information file
BTA7U@10T10000@EG1]T]17KRH131739S10510OD121{TA21HH00I.dec = dds file "high-res"

 "high-res" file
kas_04_base_01.dds
kas_04_base_04.dds
kas_04_nrm_04.dds
kas_04_wet_base_01.dds


I do not have the technology which writes a script
I want the script which extracts "high-res" dds files.
## Post #182
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-01T08:05:36+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from moge1975
>
> I don't understand, they are 2 different resolution texture ? it's strange, Team-Ninja doesn't like to work this way......


ok,please this see


2U963@1S100@CE1G]]724C2154PQ10610MC121{R72100H.dec = KASUMI_COS_004.TMC
BUA73@1S100@DF1]H]723E21544PQ10310MC121{R72100H.dec = KASUMI_COS_004.TMCL

TMC,TMCL file into "low-resolution textures"
kas_04_base_01.dds = 64 x 64pix
kas_04_base_04.dds = 64 x 64pix
kas_04_nrm_04.dds = 64 x 64pix
kas_04_wet_base_01.dds = 64 x 64pix


-----------------------------------------------------------------------------------

Anticipation high-resolution textures

color1
7R97U@10T10000@8F1S]]17KRG13163S10410OD121{T921HH00I.dec = Texture information file
BRA7U@10T10000@EG1]T]17KRH131739S10510OD121{TA21HH00I.dec = dds file "high-res"

color2
7S97U@10T10000@8F1S]]17KRG13163S10410OD121{T921HH00I.dec = Texture information file
BSA7U@10T10000@EG1]T]17KRH131739S10510OD121{TA21HH00I.dec = dds file "high-res"

color3
7T97U@10T10000@8F1S]]17KRG13163S10410OD121{T921HH00I.dec = Texture information file
BTA7U@10T10000@EG1]T]17KRH131739S10510OD121{TA21HH00I.dec = dds file "high-res"

 "high-res" file into
kas_04_base_01.dds
kas_04_base_04.dds
kas_04_nrm_04.dds
kas_04_wet_base_01.dds


I do not have the technology which writes a script
I want the script which extracts "high-res" dds files.

Alphas transparencies??
## Post #183
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-10-01T08:31:23+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Alphas transparencies??

its "High-resolution texture"

only,, change the color of underwear. Character
"High-resolution texture" contained in a separate file.
## Post #184
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-01T10:00:17+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

All the stage tmc and their respective tmcl files have been added to the spreadsheet.
## Post #185
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-10-01T13:37:42+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> All the stage tmc and their respective tmcl files have been added to the spreadsheet.

but you have managed to extract all models?

If yes, how?
## Post #186
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-01T14:16:17+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

By using Chrrox's tools and methods [viewtopic.php?p=79183#p79183](http://forum.xentax.com/viewtopic.php?p=79183#p79183) if they don't work for you then I'm sorry but I wouldn't know what the problem is.
## Post #187
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-10-01T15:45:01+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> All the stage tmc and their respective tmcl files have been added to the spreadsheet.
Using chrrox's script? Ah, I used b0ny's hopefully he makes a renamer for the stage files too 

EDIT: Dont need the renamer lol, extracting with chrrox's script now  Thanks for adding them to the spreadsheet!
## Post #188
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-10-02T03:59:34+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

How do I obtain the DLC costumes ? I have the game and downloaded the costumes using the code,but, how I am I supposed to extract those files off the xbox360? where is it stored if someone knows and can pm me that would be great =)


Okay I figured it out but it seems that script 1.4.1 noes-is python script errors out, after charox bms -> dat - charox extract-> ex -> charox decrypt -> dec
, then loading with the script appears not to work :S
## Post #189
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-10-02T04:59:00+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> Here is a version1 of a noesis script to import these models.
what is done
1.Geometry import
2.Uv sets assigned
3.textures are loaded but not assigned.
4.material creation and assignment
what is left.
2.reading in the model skeleton
3.assign bones and weights to the model.

DOA5 BMS
Code: Select allendian BIG
open FDSE "trial.lnk" 0
open FDSE "archive_order.bin" 1
goto 0x8 1
get files long 1
goto 0x24 1
savepos offset 1
for i = 0 < files
goto offset 1
get noff long 1
get arcnum long 1
get id long 1
savepos offset 1
goto noff 1
get name string 1
putarray 0 i name
next i
getarray name 0 0
putarray 0 files name
goto 0xC
get files long
get unk01 longlong
get unk02 longlong
for i = 0 < files
get offset longlong
get zsize longlong
get size longlong
get arc longlong
set id i
math id + 1
getarray name 0 id
if zsize == size
log name offset size
else
clog name offset zsize size
endif
next i

Charrox do you have an updated version of the script?  it appears that when I try and load the models they show up as empty blank spaces and noesis buggs out and says there is 1 model 0 verticies and etc... Thanks =)
## Post #190
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-10-02T06:46:41+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Mobuis
>
> How do I obtain the DLC costumes ? I have the game and downloaded the costumes using the code,but, how I am I supposed to extract those files off the xbox360? where is it stored if someone knows and can pm me that would be great =)


Okay I figured it out but it seems that script 1.4.1 noes-is python script errors out, after charox bms -> dat - charox extract-> ex -> charox decrypt -> dec
, then loading with the script appears not to work :S
You need to get the actual DLC files from your Xbox360, and use this: [http://skunkiebutt.com/Le%20Fluffie%20App.zip](http://skunkiebutt.com/Le%20Fluffie%20App.zip) to extract the dlc files and it brings out your .bin file then ready to use the tools for extraction
## Post #191
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-02T08:25:46+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> you are missing the tmcl file that goes with those models.
just search for the last 5 characters of the original tmc file name and the tmcl file will show up in the search results.

I am opening this to the public if anyone wants to update this with the list i have or if anyone wants to add any changes.
I can work on finding new names but it would be good to pull together i think.
https://docs.google.com/spreadsheet/ccc ... 2xhdFZ6eHc

this is a list of names i pulled from the demo.

Awesome 

Thank you very much chrrox, you are God.
## Post #192
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-02T15:34:34+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

The tmc and tmcl hashes for the DLC costumes that were released today have been added to the spreadsheet.
## Post #193
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-10-02T17:12:20+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> The tmc and tmcl hashes for the DLC costumes that were released today have been added to the spreadsheet.

Hey have you gotten the DLC costumes to work? I tried and it gives me a python buffer problem using all scripts released. 1.5 oddly named 1.0 in the comments, then 1.4 and 1.4.1. if so can you post the noesis script you used? thanks =)
## Post #194
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-02T17:17:56+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Yeah the DLC models work fine, I just use Chrrox's 1.5 script from this post; [viewtopic.php?p=79267#p79267](http://forum.xentax.com/viewtopic.php?p=79267#p79267)
## Post #195
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-10-02T17:24:41+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Got it work with DLC, i will try now with retail game.
## Post #196
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-02T20:10:31+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I'm making a script for automatic rename of all files, when I will finish this I will make the Tutorial for how to rip.
## Post #197
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-10-02T20:41:45+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> Yeah the DLC models work fine, I just use Chrrox's 1.5 script from this post; viewtopic.php?p=79267#p79267
Thank you this would be the final script =) it all works! yay~
## Post #198
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-10-02T20:55:44+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> I'm making a script for automatic rename of all files, when I will finish this I will make the Tutorial for how to rip.

Very nice so zaykho.

What is the difference between the extracted files folder .Ink and .bin?

 I've been watching and it seems that they are same.
## Post #199
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-02T21:11:51+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> What is the difference between the extracted files folder .Ink and .bin?
>
> 
>
> I've been watching and it seems that they are same.

Well it's because it's the same, when you click on the .lnk (LNK), the script will search for the .bin affiliated with him.

And if you click on .bin first, the script will search for the .lnk affiliated with him.

So you need the .bin and .lnk to have the same name in the same folder.



In a simple way, the extraction come from .bin & .lnk, so it doesn't matter what you choose.
## Post #200
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-10-02T21:25:58+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> What is the difference between the extracted files folder .Ink and .bin?

I've been watching and it seems that they are same.

Well it's because it's the same, when you click on the .lnk (LNK), the script will search for the .bin affiliated with him.

And if you click on .bin first, the script will search for the .lnk affiliated with him.

So you need the .bin and .lnk to have the same name in the same folder.



In a simple way, the extraction come from .bin & .lnk, so it doesn't matter what you choose.

Ok, i understood now, very thanks my friend!
## Post #201
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-03T06:32:13+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

OK here my script for extract-decrypt-rename files for DOA5:
(It's a simple .bat file, you just need to choose what do you want to extract and to wait until the script finish his work)
(only selection 1 is enabled for now !!!)
[http://www.mediafire.com/download.php?prugcc49akr9p8a](http://www.mediafire.com/download.php?prugcc49akr9p8a)

If you just want to rename lot of files, take this script:
[http://www.mediafire.com/download.php?ogqnwt4wr8b5b03](http://www.mediafire.com/download.php?ogqnwt4wr8b5b03)

And if you want the Ultimate Tool Folder for DOA/NG:
[http://www.mediafire.com/?sbd2c9r8ok3u3](http://www.mediafire.com/?sbd2c9r8ok3u3)
***If I have missed some tool, let me know !

PS: I have just make a simple .BAT, others things come from different users, thx chroxx & others Xentax user...
## Post #202
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-03T09:36:52+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I can't load models in Noesis

> 

I used DOA5 simple unpacker and new DOA5 python plugin and nothing ;/
## Post #203
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-03T09:46:20+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

It's best to use Chrrox's bms scripts instead.
## Post #204
- Username: exialk2012
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 03, 2012 12:57 pm
- Post datetime: 2012-10-03T09:59:05+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> OK here my script for extract-decrypt-rename files for DOA5:
(It's a simple .bat file, you just need to choose what do you want to extract and to wait until the script finish his work)
(only selection 1 is enabled for now !!!)
http://www.mediafire.com/download.php?prugcc49akr9p8a

If you just want to rename lot of files, take this script:
http://www.mediafire.com/download.php?ogqnwt4wr8b5b03

And if you want the Ultimate Tool Folder for DOA/NG:
http://www.mediafire.com/?sbd2c9r8ok3u3
***If I have missed some tool, let me know !

PS: I have just make a simple .BAT, others things come from different users, thx chroxx & others Xentax user...

thank you for your rip tool

i used it and succeed for cos,but face and hair can't show in noesis

import the XXXhair.tmc noesis don't prompt any error,but viewport is nothing

why

do you konw it??

thx
## Post #205
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-03T10:16:03+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> thank you for your rip tool
>
> 
>
> i used it and succeed for cos,but face and hair can't show in noesis
>
> 
>
> import the XXXhair.tmc noesis don't prompt any error,but viewport is nothing
>
> 
>
> why
>
> 
>
> do you konw it??
>
> 
>
> thx

You should have the respective .TMCL file of .TMC to open the face and hair.
## Post #206
- Username: exialk2012
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 03, 2012 12:57 pm
- Post datetime: 2012-10-03T10:21:30+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from blackfoxeye
>
> thank you for your rip tool

i used it and succeed for cos,but face and hair can't show in noesis

import the XXXhair.tmc noesis don't prompt any error,but viewport is nothing

why

do you konw it??

thx

You should have the respective .TMCL file of .TMC to open the face and hair.

um,the name list haven't face and hair tmcl corresponding file

overlook it ??

i must check it again!!
## Post #207
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-03T10:28:42+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Check this doc written by "chrrox"

[https://docs.google.com/spreadsheet/ccc ... 2xhdFZ6eHc](https://docs.google.com/spreadsheet/ccc?key=0AjHfst1X766adG9NcmQ5LUQyNzNrR3RUZ2xhdFZ6eHc)

Every model has separate page on it and having most of the names.
## Post #208
- Username: exialk2012
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 03, 2012 12:57 pm
- Post datetime: 2012-10-03T10:32:27+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from blackfoxeye
>
> Check this doc written by "chrrox"

https://docs.google.com/spreadsheet/ccc ... 2xhdFZ6eHc

Every model has separate page on it and having most of the names.

thx

yeah,i overlook it

it work
## Post #209
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-10-03T12:28:14+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> OK here my script for extract-decrypt-rename files for DOA5:
(It's a simple .bat file, you just need to choose what do you want to extract and to wait until the script finish his work)
(only selection 1 is enabled for now !!!)
http://www.mediafire.com/download.php?prugcc49akr9p8a

If you just want to rename lot of files, take this script:
http://www.mediafire.com/download.php?ogqnwt4wr8b5b03

And if you want the Ultimate Tool Folder for DOA/NG:
http://www.mediafire.com/?sbd2c9r8ok3u3
***If I have missed some tool, let me know !

PS: I have just make a simple .BAT, others things come from different users, thx chroxx & others Xentax user...

Amazing tool rename my friend!

I did rename with your tools, very fast, now waiting all list. 

Anybody know where are face_helena.tmcl?

I dont find in the folder chara_common.
## Post #210
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-03T12:55:40+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Amazing tool rename my friend!
>
> 
>
> I did rename with your tools, very fast, now waiting all list. 
>
> 
>
> Anybody know where are face_helena.tmcl?
>
> 
>
> I dont find in the folder chara_common.

Thank you :p

I will update tonight the Tool-Rip and the List-Name, more names to come  

EDIT:

> Anybody know where are face_helena.tmcl?

240J2_9F912F31]9161G16]]2573OC1DL000I0E{NF = HELENA_FACE.tmc
B50J2_AFA1221]GB161A14]]2573O4C1DL000I0E{NF = HELENA_FACE.tmcl
## Post #211
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-10-03T13:23:21+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> Amazing tool rename my friend!

I did rename with your tools, very fast, now waiting all list. 

Anybody know where are face_helena.tmcl?

I dont find in the folder chara_common.

Thank you :p

I will update tonight the Tool-Rip and the List-Name, more names to come  

EDIT:
Anybody know where are face_helena.tmcl?

240J2_9F912F31]9161G16]]2573OC1DL000I0E{NF = HELENA_FACE.tmc
B50J2_AFA1221]GB161A14]]2573O4C1DL000I0E{NF = HELENA_FACE.tmcl

But i dont find in my folder, why?
## Post #212
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-10-03T13:28:43+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I did find, and discovery error and because i didint find.

Very thanks!
## Post #213
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-03T13:34:52+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> I did find, and discovery error and because i didint find.
>
> 
>
> Very thanks!

good to hear :p
## Post #214
- Username: darkblueking
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 03, 2011 9:08 pm
- Post datetime: 2012-10-03T14:48:21+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

2414J8_81J1]]HA1400B145]20OCMBH2G1L{OJ = BRAD_FACE.TMC
B515J9_91J1]]913H00D125]20O0CMBI2H1L{OJ = BRAD_FACE.TMCL

2411J8_J91]]4H515A146]20OI161CMEI221L{O4 = AKIRA_FACE.TMC
B511J9_JA1]]4414HC126]20OJ1612CMEJ221L{O4 = AKIRA_FACE.TMCL

246J3_991E21]914]]2E11M1ODME62B8L{OI = RIG_FACE.TMC
B57J3_AA110]FB12]]2F11M1O2DME62B8L{OI = RIG_FACE.TMCL

2WDK3@1S100@DC1861]3]B1930QC1N0GI2A7MP{2Q71E = RTM_FACE_006.TMC
BWDK3@1S100@ED151]91]D1930Q0C1N0HJ2A7MP{2Q71D = RTM_FACE_006.TMCL

Noesis couldn't display these files . I got an error When imported these files as obj . 3ds max says , " vertex coordinate too big adjust object-scale " .  

2T763@1S100@BB1G]]724I1G1J1FE198PQF1710M10{R721K = LEIFANG_COS_003.TMC
BT873@1S100@CC1]H]723C1G1J1GE1298PQF1610M10{R721K = LEIFANG_COS_003.TMCL

These 2 files just use doa5decrypt.bms Script directly , you'll get correct dec files .    

7XXXX@10X10000@XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX = ???.TMC 
BXXXX@10X10000@XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX = ???.TMCL 

@logansan25 
Still can't open it .
## Post #215
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-10-03T15:07:36+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

@darkblueking

If you cant open this, i believe have fail in first extraction.

Try extract again.
## Post #216
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-03T23:00:11+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Any progress on the script?? At least mesh position maybe??

See ya.
## Post #217
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-04T02:04:13+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

DOA5 - Model Renamer v1.2.zip  *UPDATE - 04/10/2012 - 04:05 AM - GTM+2*
----------------------------------------------------------------------------------------------------------
the v1.2 give you: 
- The latest names from the GoogleDOC page --> https://docs.google.com/spreadsheet/ccc ... eHc#gid=27 (- 04/10/2012 - 04:05 AM - GTM+2-)
- Support now: Characters, Stages and DLC

This tool will rename all unknown model names from extracted files of DOA5 by an updated list of real names.
You just need to put the .bat file in the folder corresponding to the type of files you have extracted from DOA5 (Characters, Stages or DLC)


Link to the tool -->
[http://www.mediafire.com/?61z7llb902fabu1](http://www.mediafire.com/?61z7llb902fabu1)

Link to the ultimate folder tool of DOA/NG -->
[http://www.mediafire.com/?sbd2c9r8ok3u3](http://www.mediafire.com/?sbd2c9r8ok3u3)


PS: This tool contains work from chroxx & others Xentax user too.

EDIT: Link to folder corrected
## Post #218
- Username: Chimera
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 24, 2011 11:31 pm
- Post datetime: 2012-10-04T04:28:57+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thanks for the tools Zaykho and Chrrox ! 
just tested the scripts for DOA V and it works great ! Any plans on bone support ?
## Post #219
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-10-04T14:13:52+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

@Zaykho Very cool tools my friend!

I use rename version2 and great.

Very very thanks!
## Post #220
- Username: wdw89
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Apr 07, 2012 4:10 pm
- Post datetime: 2012-10-04T14:53:30+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

@chrrox, I notice some hairs have normal textures, but your doa5_360.py script set those normal textures to Specular Textures, I change the code, but it maybe has problem with other part, can you check that? 

```
material.setSpecularTexture(texNameList[texId])
```

change to

```
material.setNormalTexture(texNameList[texId])
```

And can you set the alpha to transparency in the script? So after exporting fbx, we don't need manually set transparency. I know the body also has alpha, but break connection in maya is easy, and that's just a few objects.
PS: I use filetexturemanager to add the path and extension
[http://www.creativecrash.com/maya/downl ... uremanager](http://www.creativecrash.com/maya/downloads/scripts-plugins/c/filetexturemanager)
## Post #221
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-04T18:53:08+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Thanks for the tools Zaykho and Chrrox !
>
> just tested the scripts for DOA V and it works great ! Any plans on bone support ?

> @Zaykho Very cool tools my friend!
>
> 
>
> I use rename version2 and great.
>
> 
>
> Very very thanks!

Thx guys, I will update names every 2 days, and I will finish my extract tool rip this night.
## Post #222
- Username: oranges283
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 05, 2010 6:24 am
- Post datetime: 2012-10-05T00:09:05+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thanks for all the great tools   

I wish I had the dlc models though   

Was anyone able to get Rig's face? It always appears blank for me
## Post #223
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-10-06T06:07:19+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Is there anywhere here interested in modding this game?

Right now I'm stuck getting past the game's file checksum. 
It be nice if someone with knowledge with disassembly could have a look.

PM me if your interested.
## Post #224
- Username: Shad
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 05, 2011 4:32 pm
- Post datetime: 2012-10-06T16:42:35+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Many thanks for these extraction tools   
Is there any way to get the correct normal maps for the bodies and the faces (the game seems to use 2 maps blended according the sweat of the fighters)??
## Post #225
- Username: exialk2012
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 03, 2012 12:57 pm
- Post datetime: 2012-10-07T14:15:02+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

=w=
## Post #226
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-08T01:14:19+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

DOA5 - Model Renamer v1.5  *UPDATE - 08/10/2012 - 03:05 AM - GTM+2*
----------------------------------------------------------------------------------------------------------
the v1.5 give you: 
- The latest names from the GoogleDOC page --> https://docs.google.com/spreadsheet/ccc ... eHc#gid=27 
- Support now: Characters, Stages and DLC in only one file

This tool will rename all unknown model names from extracted files of DOA5 by an updated list of real names.
You just need to put the .bat file in the folder where you have extracted files from DOA5 (Characters, Stages or DLC)

DOA5 - Ripping Tool v1.5  *UPDATE - 08/10/2012*
----------------------------------------------------------------------------------------------------------
the v1.5 give you: 
- Support now: Characters and DLC
- Automatically renaming files after finish
- Renaming.bat as been cleared and optimized   

This tool will extract and decrypt all chosen files of DOA5 and automatically rename them with an updated list of real names.
You just need to put the folder ( doa5_ripping_tool ) in the doa5 folder OR the dlc "root" folder (where .bin and .lnk are) 



Link to DOA5 - Model Renamer v1.5 -->
[http://www.mediafire.com/?rd3g3i234w8x84r](http://www.mediafire.com/?rd3g3i234w8x84r)

Link to DOA5 - Ripping Tool v1.5 -->
[http://www.mediafire.com/?h5xcs5zdj29jahi](http://www.mediafire.com/?h5xcs5zdj29jahi)

Link to the ultimate folder tool of DOA/NG -->
[http://www.mediafire.com/?sbd2c9r8ok3u3](http://www.mediafire.com/?sbd2c9r8ok3u3)



PS: These tools contains work from chroxx & others Xentax user too.
## Post #227
- Username: kraken973
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 21, 2010 11:31 pm
- Post datetime: 2012-10-08T02:53:34+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

What are the step for using this tool? any tutorial?
Don't work for me
## Post #228
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-08T03:07:42+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> What are the step for using this tool?
>
> Don't work for me

What tool ?

> DOA5 - Model Renamer v1.5:
>
> 
>
> if you have a folder with lot of :
>
> 
>
> BJ10_31EB1@1218I1B179131[]G1K13M1N{N1B1
>
> or
>
> BJ10_31EB1@1218I1B179131[]G1K13M1N{N1B1.dec
>
> 
>
> Then you need take the " 4_update_filenames.bat " and copy UNDER the folder where you have 
>
> the " BJ10_31EB1@1218I1B179131[]G1K13M1N{N1B1 "  files...
>
> 
>
> Double click on the " 4_update_filenames.bat " and voila ~~

OR

> DOA5 - Ripping Tool v1.5:
>
> 
>
> In your DOA5 folder you must have some .bin and .lnk (or shorcut) files:
>
> 
>
> chara_common
>
> or
>
> chara_common.lnk
>
> or
>
> chara_common.bin
>
> 
>
> Then you need take the FOLDER " doa5_ripping_tool " and copy UNDER the folder of DOA5, where you have 
>
> the chara_common,stage_common ....  files.
>
> 
>
> Now go the " doa5_ripping_tool " folder and Double click on the " doa5_rip.bat " and voila ~~

?
## Post #229
- Username: kraken973
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 21, 2010 11:31 pm
- Post datetime: 2012-10-08T03:47:46+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Now it's good. Thanks   
I missed chara_common.bin in the folder with chara_common.Ink. Not working without it.
## Post #230
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-08T03:53:11+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from kraken973
>
> Now it's good. Thanks   
I missed chara_common.bin in the folder with chara_common.Ink. Not working without it.

OK good to hear :p

EDIT: I will update to 1.7 tomorrow with the stages choice.
## Post #231
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-10-08T07:55:02+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I've been looking at the names, trying to figure out if they had something to do with the file checksum... I'm pretty sure they're not now

Anyway I looked at the demo, and the demo has full directories

Example:
\CHR\MILA\COSTUME\COS_001\MILA_COS_001.TMC (42 characters)
2R052@1S100@BF1G]]724B21G1PQ87710M10{R821F (42 characters)

So these names, are actually full filepath names that are encrypted

I think key or cipher is locally generated off the source string.. Like for example your source string is "C:\folder\myfile.dat" then you use the base filename "myfile.dat" as your key to encrypt the filepath "C:\folder\" .. again this is just a guess O-o

if you compare three simular character names, "LISA", "MILA" and "TINA". The encoding is a perfect match upto about half way. then the characters are completely different. 
If they are XOR'd or encrypted by their base file name, then the encryption is very minimal on these three names, and theres only two unique characters. Using the source string as the key makes sense because some adjacent characters are completly different.. so its not a single key thats being used across everything.

\CHR\LISA\COSTUME\COS_001\LISA_COS_001.TMC
\CHR\MILA\COSTUME\COS_001\MILA_COS_001.TMC
\CHR\TINA\COSTUME\COS_001\TINA_COS_001.TMC

Encoded names are printed in reverse

CMT.100_SOC_ASIL\100_SOC\EMUTSOC\ASIL\RHC\
CMT.100_SOC_ALIM\100_SOC\EMUTSOC\ALIM\RHC\
CMT.100_SOC_ANIT\100_SOC\EMUTSOC\ANIT\RHC\

2R052@1S100@BM1H]]724BJ165PQ610J1N10{9721F
2R052@1S100@BF1G]]724B21G1PQ87710M10{R821F
2R052@1S100@BH1H]]724BP10QI1410M1098{R721F

H1MB = LISA
G1FB = MILA
H1HB = TINA

All three girl's name end with A, and you can see the above example matches in a 4 character matchup, printed in reverse

I feel we could be on the verge of dissolving the encryption, but I just can't see what they did there.
## Post #232
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-08T09:05:12+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Hi Mariokart, I was also trying to figure out the encryption of these filenames, I did think maybe it was the directory backwards due to the tmc, tmcl numbers being at the end but the fact that it ended with completely different chars threw me off of that. What you say about the length of the characters name makes perfect senese, can't believe I overlooked that, so thanks for that.
## Post #233
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2012-10-09T18:10:30+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

mariokart64n
good luck to you. but the names are used in encrypted form inside the game, so no reverse engineering is possible to find the key(the models where encrypted using an antihack warning as a key). also i think i've seen files that doesn't meet your length criteria. i think too that the "abra cadabra names" are reversed, thus i'm reversing them back in the "simple doa5 unpacker" tool.

simple doa5 unpacker v3
## Post #234
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-10-09T21:52:02+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

thanks for providing source code. I wanted to do this myself, but I lacked the education to do so.

my two problems, were how do I manage large archive files, and how do I implement zpipe.
## Post #235
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2012-10-09T22:11:10+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

So, are there any updates regarding the model's and their bone weights? This topic seems to have gone pretty quiet on the Noesis script
## Post #236
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-10T07:05:46+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Inside Neosis we have all texture applied and display correctly.
But after exporting the link between mesh and textures are gone.
I am exporting .obj mesh, .tga textures with flip UV's check-box checked.

So is there any way to export the characters with textures applied correctly, so that when we import the models to other 3D programmes, the textures will show correctly.
## Post #237
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-10T08:53:57+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

[](http://www.hostingpics.net/viewer.php?id=535331Sanstitre3.jpg)

DOA5 - Model Tool v2.0 * UPDATE - 10/10/2012 *
----------------------------------------------------------------------------------------------------------
the v2.0 contain: 
- The Renamer Tool and the Rip Tool in only one file
the v2.0 give you: 
- The latest names from the GoogleDOC page --> https://docs.google.com/spreadsheet/ccc ... eHc#gid=27 (- 08/10/2012 - 04:05 AM - GTM+2-)
- Support now: Characters, Stages, DLC and User-Prompt update

This tool will extract/decrypt files of DOA5 and rename them automatically or manually
You just need to put the folder ( doa5_tool ) in the DOA5 folder OR the dlc "root" folder (where .bin and .lnk are) OR to just "browse" your folder for updating unknown names


Link to the tool -->
[http://www.mediafire.com/?7t1kdsy9t421h9n](http://www.mediafire.com/?7t1kdsy9t421h9n)

Link to the ultimate folder tool of DOA/NG -->
[http://www.mediafire.com/?sbd2c9r8ok3u3](http://www.mediafire.com/?sbd2c9r8ok3u3)

Edit:The ultimate folder tool of DOA/NG have been actualized and optimized

PS: This tool contains work from chroxx & others Xentax user too.
## Post #238
- Username: wdw89
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Apr 07, 2012 4:10 pm
- Post datetime: 2012-10-11T09:13:19+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from blackfoxeye
>
> Inside Neosis we have all texture applied and display correctly.
But after exporting the link between mesh and textures are gone.
I am exporting .obj mesh, .tga textures with flip UV's check-box checked.

So is there any way to export the characters with textures applied correctly, so that when we import the models to other 3D programmes, the textures will show correctly.

My method:
1. Open doa5_360.py (v1.5) noesis script, replace "material.setSpecularTexture(texNameList[texId])" to "material.setNormalTexture(texNameList[texId])", because some hair's normal maps are set to specular map in the original script.
2. Use noesis to export to fbx and tga.
3. download filetexturemanager, a maya script.[http://www.creativecrash.com/maya/downl ... uremanager](http://www.creativecrash.com/maya/downloads/scripts-plugins/c/filetexturemanager) Put it in \Documents\maya\2013-x64 (your version)\scripts
4. Import fbx in maya, then type filetexturemanager in mel, enter. it can add texture path and extension (use the suffix)
5. You still need add alpha to transparency manually.

I can't find a script in 3ds max to batch add extension for textures, but 3ds max can change texture path using utilities-more-bitmap/photometric paths
## Post #239
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2012-10-11T10:29:46+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thanx zaykho for your tools

but I have a Q

Why I cant extract bones?

Even in noesis i can't see bones -_- 


and

THANX alot
## Post #240
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2012-10-11T10:48:36+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from wdw89
>
> 
My method:
1. Open doa5_360.py (v1.5) noesis script, replace "material.setSpecularTexture(texNameList[texId])" to "material.setNormalTexture(texNameList[texId])", because some hair's normal maps are set to specular map in the original script.
2. Use noesis to export to fbx and tga.
3. download filetexturemanager, a maya script.http://www.creativecrash.com/maya/downl ... uremanager Put it in \Documents\maya\2013-x64 (your version)\scripts
4. Import fbx in maya, then type filetexturemanager in mel, enter. it can add texture path and extension (use the suffix)
5. You still need add alpha to transparency manually.

I can't find a script in 3ds max to batch add extension for textures, but 3ds max can change texture path using utilities-more-bitmap/photometric paths

I did all the steps you mentioned, but after opened the FileTextureManager, I am confused what to do.

How to add texture paths and extension ?

Can you please elaborate little bit more, how to use that.
## Post #241
- Username: sophist82
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 21, 2012 11:39 pm
- Post datetime: 2012-10-11T11:01:22+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

252gt// Which version of Noesis are u using? 
Because my noesis doesn't even show bones at all...
## Post #242
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2012-10-11T14:29:35+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Sorry 
I edit the post

I CAN NOT see Bones


I am really Sorry

--Sorry for BAD English--
## Post #243
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-11T14:38:32+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from 252gt
>
> Sorry 
I edit the post

I CAN NOT see Bones


I am really Sorry

--Sorry for BAD English--

The recent script doesn't support bones and skinning.

See ya
## Post #244
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-11T22:38:36+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> 252gt wrote:Sorry 
I edit the post

I CAN NOT see Bones


I am really Sorry

--Sorry for BAD English--

The recent script doesn't support bones and skinning.

See ya

Yes Bones and animation are not supported yet.
## Post #245
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-10-12T00:17:18+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Bones are extractable from this game; they are in the HieLay section. Data is in a simple adjacency list with joints in relative positions. I have no time, but if anyone wants to convert the following code you may do so:



```
#include "x_file.h"
#include "x_win32.h"
#include "x_stream.h"
using namespace std;

// HieLay 0x2A80

struct treenode {
 real32 m[16];
 real32 x;
 real32 y;
 real32 z;
 uint32 parent;
 deque<uint32> children;
};

bool traverse_tree(deque<treenode>& tree, uint32 root)
{
 // get parent
 uint32 parent = tree[root].parent;

 // get relative position
 real32 x = tree[root].m[12];
 real32 y = tree[root].m[13];
 real32 z = tree[root].m[14];
 tree[root].x = x;
 tree[root].y = y;
 tree[root].z = z;

 // relative-to-absolute position
 if(parent != 0xFFFFFFFF) {
    tree[root].x += tree[parent].x;
    tree[root].y += tree[parent].y;
    tree[root].z += tree[parent].z;
   }

 // DFS
 for(size_t i = 0; i < tree[root].children.size(); i++)
     traverse_tree(tree, tree[root].children[i]);

 return true;
}

bool TestDOA5(void)
{
 const char* filename = "HITOMI_DLC_006.TMC";
 ifstream ifile(filename, ios::binary);
 if(!ifile) return error("1");

 // move to HieLay
 uint32 hielayoffset = 0x2A80;
 ifile.seekg(hielayoffset);
 if(ifile.fail()) return error("2");

 // read magic number
 auto magic = BE_read_uint64(ifile);
 if(magic != 0x4869654C61790000L) return error("3");

 // read signature
 auto signature = BE_read_uint32(ifile);
 if(signature != 0xFF000101) return error("4");

 // read headersize
 auto headersize = BE_read_uint32(ifile);
 if(headersize != 0x30) return error("5");

 // read chunksize
 auto chunksize = BE_read_uint32(ifile);
 if(chunksize == 0) return error("6");

 // read number of joints
 auto njoints1 = BE_read_uint32(ifile);
 auto njoints2 = BE_read_uint32(ifile);
 if(njoints1 == 0) return error("7");
 if(njoints2 == 0) return error("8");
 if(njoints1 != njoints2) return error("9");

 // read zero
 auto z01 = BE_read_uint32(ifile);
 if(ifile.fail()) return error("10");

 // read headersize #2
 auto headersize2 = BE_read_uint32(ifile);
 if(headersize2 != 0x30) return error("11a");
 if(headersize != headersize2) return error("11b");

 // read zero
 auto z02 = BE_read_uint32(ifile);
 if(ifile.fail()) return error("12");

 // read offset to matrices
 auto moffset = BE_read_uint32(ifile);
 if(moffset == 0) return error("13");

 // read zero
 auto z03 = BE_read_uint32(ifile);
 if(ifile.fail()) return error("14");

 // move back to the beginning
 ifile.seekg(hielayoffset);
 if(ifile.fail()) return error("15");

 // read hielay section
 boost::shared_array<char> data(new char[chunksize]);
 ifile.read(data.get(), chunksize);
 if(ifile.fail()) return error("16");

 // create binary stream
 binary_stream bs(data, chunksize);

 // move to matrix offsets
 bs.seek(headersize);
 if(bs.fail()) return error("17");

 // read offsets
 deque<uint32> offsets;
 for(auto i = 0u; i < njoints1; i++) {
     auto item = bs.BE_read_uint32();
     if(item == 0) return error("18");
     offsets.push_back(item);
    }

 // read adjacency list
 deque<treenode> adjlist;
 for(auto i = 0u; i < njoints1; i++)
    {
     // move to data
     bs.seek(offsets[i]);
     if(bs.fail()) return error("19");

     // read matrix
     treenode node;
     bs.BE_read_array(&node.m[0], 16);
     if(bs.fail()) return error("20");

     // x, y, z
     auto x = node.m[12];
     auto y = node.m[13];
     auto z = node.m[14];

     // parent
     node.parent = bs.BE_read_uint32();
     if(bs.fail()) return error("21");

     // children
     auto children = bs.BE_read_uint32();
     if(bs.fail()) return error("22");

     // unknowns
     auto unk01 = bs.BE_read_uint32();
     auto unk02 = bs.BE_read_uint32();
     if(bs.fail()) return error("23");

     // children
     for(auto j = 0u; j < children; j++) {
         auto index = bs.BE_read_uint32();
         if(bs.fail()) return error("24");
         node.children.push_back(index);
        }

     // add node
     adjlist.push_back(node);
    }

 // traverse tree to compute relative to absolute
 traverse_tree(adjlist, 0);

 // create output file
 stringstream ss;
 ss << GetPathnameFromFilename(filename) << GetShortFilenameWithoutExtension(filename) << ".OBJ";
 ofstream ofile(ss.str().c_str());
 if(!ofile) return error("25");

 // print vertices
 for(size_t i = 0; i < adjlist.size(); i++) {
     real32 x = adjlist[i].x;
     real32 y = adjlist[i].y;
     real32 z = adjlist[i].z;
     ofile << "v " << x << " " << y << " " << z << endl;
    }

 // print faces
 for(size_t i = 0; i < adjlist.size(); i++) {
     for(size_t j = 0; j < adjlist[i].children.size(); j++) {
         uint32 a = i + 1;
         uint32 b = adjlist[i].children[j] + 1;
         ofile << "f " << a << " " << b << endl;
        }
    }

 return true;
}

int main()
{
 TestDOA5();
 return 0;
}

```
## Post #246
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-10-12T01:46:20+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

wow look at the bones they put there.. >_> on the boobs 

no wonder they move weird, that setup for for having them ripple lol
## Post #247
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-12T02:23:18+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from mariokart64n
>
> wow look at the bones they put there.. >_> on the boobs 

no wonder they move weird, that setup for for having them ripple lol

It's beacuase they wanted  to have "real boobs movements" lol.
## Post #248
- Username: sophist82
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 21, 2012 11:39 pm
- Post datetime: 2012-10-12T02:50:24+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

That's great!!! howfie!!

Then would u able to get skin weight data from it as well?

I hope it isn't that hard to pull it out...
## Post #249
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2012-10-12T05:18:58+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

can someone verify if this nude mod is real or shopped? the texture of the body looks like DOA4 so I am guessing this is DOA4 mod plus shopped DOA5 face. saw this on japanese site.

how can I disable the preview of the pic? it's not safe for work



Resize of 1349985587893.jpg (127.64 KiB) Viewed 795 times
## Post #250
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-10-12T05:51:59+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

*cough* xnalara
## Post #251
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-12T07:38:14+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from MuffinMan123
>
> can someone verify if this nude mod is real or shopped? the texture of the body looks like DOA4 so I am guessing this is DOA4 mod plus shopped DOA5 face. saw this on japanese site.

Yes it's a true one, at least, it's a perfect body from DOA 5, don't know if it's imported in the game.

Guys, next time provide the link !

here the link of where @MuffinMan123 found the picture -->
[http://3d.skr.jp/3d/3d.php?res=254267](http://3d.skr.jp/3d/3d.php?res=254267)

This one too is a perfect body from DOA5 :
[](http://www.hostingpics.net/viewer.php?id=3539901349998071603.jpg)
[http://www.coregrafx.info/sexy2/index.html](http://www.coregrafx.info/sexy2/index.html)

> how can I disable the preview of the pic? it's not safe for work
We don't care of this shit here, nude or not, everything is the same when it's in 3D...


Some comparison DOA4/DOAX2 vs DOA5 with the little princess Kasusu : :p

[](http://www.hostingpics.net/viewer.php?id=453939741.jpg)[](http://www.hostingpics.net/viewer.php?id=651104192.jpg)[](http://www.hostingpics.net/viewer.php?id=634867693.jpg)[](http://www.hostingpics.net/viewer.php?id=323842544.jpg)

[](http://www.hostingpics.net/viewer.php?id=997564final.jpg)

 some people have too much free time isn't it ?
## Post #252
- Username: wdw89
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Apr 07, 2012 4:10 pm
- Post datetime: 2012-10-12T10:18:23+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from blackfoxeye
>
> wdw89 wrote:
My method:
1. Open doa5_360.py (v1.5) noesis script, replace "material.setSpecularTexture(texNameList[texId])" to "material.setNormalTexture(texNameList[texId])", because some hair's normal maps are set to specular map in the original script.
2. Use noesis to export to fbx and tga.
3. download filetexturemanager, a maya script.http://www.creativecrash.com/maya/downl ... uremanager Put it in \Documents\maya\2013-x64 (your version)\scripts
4. Import fbx in maya, then type filetexturemanager in mel, enter. it can add texture path and extension (use the suffix)
5. You still need add alpha to transparency manually.

I can't find a script in 3ds max to batch add extension for textures, but 3ds max can change texture path using utilities-more-bitmap/photometric paths

I did all the steps you mentioned, but after opened the FileTextureManager, I am confused what to do.

How to add texture paths and extension ?

Can you please elaborate little bit more, how to use that.

Because all the texture names are in the fbx file, but without path and extension, so we need to add them.
After opening file texture manager:
1. Analyse scene file texture, then select the not exist one.
2. In target directory, change to the texture path.
3. In add suffix, type .tga (your texture extension with a dot)
4. Press set path, done.

The help tab has more information.
## Post #253
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-10-12T11:08:03+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

how to get this texture?
## Post #254
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-12T13:04:30+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

those textures are in the 7R* xpr2 files along with their respective tmcls
## Post #255
- Username: misquared
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 26, 2010 8:32 am
- Post datetime: 2012-10-14T07:40:44+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I have noesis and the new script
However my PC can't take anymore space

May I ask for Kokoro's Pink Kimono (default) model please?  (This: [http://images1.wikia.nocookie.net/__cb2 ... Render.png](http://images1.wikia.nocookie.net/__cb20120626071915/deadoralive/images/thumb/f/fc/DOA5_Kokoro_Render.png/250px-DOA5_Kokoro_Render.png))
That's the only one I want from this game^^;
## Post #256
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2012-10-14T18:31:29+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from misquared
>
> I have noesis and the new script
However my PC can't take anymore space

May I ask for Kokoro's Pink Kimono (default) model please?  (This: http://images1.wikia.nocookie.net/__cb2 ... Render.png)
That's the only one I want from this game^^;

OK

Here you go

[http://www.mediafire.com/?gt9vihlivmol13l](http://www.mediafire.com/?gt9vihlivmol13l)
## Post #257
- Username: sophist82
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 21, 2012 11:39 pm
- Post datetime: 2012-10-15T05:38:02+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Ok, I was trying to compile with the source code, which howfie wrote it.

But I wasn't able to find include files,(xentax.h, x_file.h, x_win32.h, x_stream.h).

Could anyone tell me where I would be able to find those?
## Post #258
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-15T06:23:20+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from sophist82
>
> Ok, I was trying to compile with the source code, which howfie wrote it.

But I wasn't able to find include files,(xentax.h, x_file.h, x_win32.h, x_stream.h).

Could anyone tell me where I would be able to find those?

From here:

[https://code.google.com/p/sticklove/sou ... x%2Fripper](https://code.google.com/p/sticklove/source/browse/#svn%2Ftrunk%2Fsource%2Fxentax%2Fripper)
## Post #259
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-10-15T07:30:28+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

wasn't expecting anyone to compile it... but rather maybe make a python script from it instead . the code is always changing and I wouldn't expect anyone other than myself to be able to get it working  . there is also the issue of weights... OG bones are useless without OG weights; best to wait for chroxx to update his script.
## Post #260
- Username: sophist82
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Apr 21, 2012 11:39 pm
- Post datetime: 2012-10-15T09:44:29+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I was trying compile it, as a way of understanding some extraction concepts from it. However, Bone location itself sometimes provides me great reference of understanding designers intention of making characters to animate. I could have create bones myself and bind it, but kind of wanna follow the original status much as possible. 

Hope that Chroxx updates new scripts for bones and weights. Better try something, rather than just waiting~.

Anyway, thx alot.
## Post #261
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-10-15T19:45:16+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I'm looking for file checksums, was there anything like that in the TMC?
## Post #262
- Username: oranges283
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 05, 2010 6:24 am
- Post datetime: 2012-10-15T23:15:27+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

snip
## Post #263
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-10-15T23:39:30+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

sharing of copyrighted files constitutes piracy.. you probably shouldn't be asking for those files here
## Post #264
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-17T17:27:54+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

New DLC:

```

2R052@1S100@BM1H]]J1835C00E175PQ6J1N{C761G = LISA_DLC_001.tmc
BR062@1S100@CM1]I]B1834D001E175PQ6J1N{C761G = LISA_DLC_001.tmcl
2S052@1S100@BM1H]]J1835C00E175PQ6J1N{C761G = LISA_DLC_002.tmc
BS062@1S100@CM1]I]B1834D001E175PQ6J1N{C761G = LISA_DLC_002.tmcl
2T052@1S100@BM1H]]J1835C00E175PQ6J1N{C761G = LISA_DLC_003.tmc
BT062@1S100@CM1]I]B1834D001E175PQ6J1N{C761G = LISA_DLC_003.tmcl

Hayabusa:

2R052@1S100@BMS131361I]]K1A35D64F1QR621O{D6J1D1811 = HAYABUSA_DLC_001.tmc
BR062@1S100@CMS131361]J]C1A34E643F1QR421O{D6J1D1811 = HAYABUSA_DLC_001.tmcl

Kasumi:

2S963@1S100@CE1G]]I1835D2164F1PQ107ME1{R72161J = KASUMI_DLC_002.tmc
BSA73@1S100@DF1]H]C1834E21644F1PQ104ME1{R72161J = KASUMI_DLC_002.tmcl

Lei fang:

2R763@1S100@BB1G]]I183500G1J1FE1H1A8PQG18M{R751L = LEIFANG_DLC_001.tmc
BR873@1S100@CC1]H]C183400G1J1GE12H1A8PQG17M{R751L = LEIFANG_DLC_001.tmcl

Rig:

2R763@1S100@BG]]I1735G1DN1G1PQ5B9N{R871K = RIG_DLC_001.tmc
BR873@1S100@C]H]B1734G1EN12G1PQ4B9N{R871K = RIG_DLC_001.tmcl

Mila:

2S052@1S100@BF1G]]00724B21G1E1PQ988M{R851G = MILA_DLC_002.tmc
BS062@1S100@C71]H]00723C212G1E1PQ987M{R851G = MILA_DLC_002.tmcl

Hitomi:

2S963@1S100@CG]]I1735C644712E1PQM13192{H1R2511 = HITOMI_DLC_002.tmc
BSA73@1S100@D]H]B1734D6447125E1PQM13152{H1R2511 = HITOMI_DLC_002.tmcl

Tina:

2T052@1S100@BH1H]]J1835CP1F11QJ15MB9{R771H = TINA_DLC_003.tmc
BT062@1S100@CH1]I]B1834DP12F11QJ14MB9{R771H = TINA_DLC_003.tmcl

Helena:

2T052@1S100@BH1H]]J18357110C75E1D1PQ007M{R651H = HELENA_DLC_003.tmc
BT062@1S100@CH1]I]B18347110D753E1D1PQ005M{R651H = HELENA_DLC_003.tmcl

Christie:

2T151@1S100@BG]1]1I172G62C10P1O1G12Q4C171NQ1{0871H = CHRISTIE_DLC_003.tmc
BT161@1S100@C]1]I2A173G52D10P1O12G13Q4C171NQ1{0871H = CHRISTIE_DLC_003.tmcl

```


For whoever wants to update the table.

Edit:

Is there a way to extract the extract texture from the current 2's and b'd files??

See ya.
## Post #265
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-17T19:43:47+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I could load them by replacing the texch header (??) for another tmc file header, but the textures are wrong:



See ya.
## Post #266
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-18T12:15:29+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Eww... There's a way to extract perfect dress text from Kasumi pink-white outfit?

>
## Post #267
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-19T22:11:54+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> I could load them by replacing the texch header (??) for another tmc file header, but the textures are wrong:

You have to attach the xpr2 header to the tmcl files and then you can view them correctly using Chrrox's xpr2 noesis plugin from here; [viewtopic.php?f=18&t=8102](http://forum.xentax.com/viewtopic.php?f=18&t=8102)
## Post #268
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-10-20T08:38:41+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> Darko wrote:I could load them by replacing the texch header (??) for another tmc file header, but the textures are wrong:


You have to attach the xpr2 header to the tmcl files and then you can view them correctly using Chrrox's xpr2 noesis plugin from here; viewtopic.php?f=18&t=8102

"fmt_XBOX_360_XPR" fixversion upload please....
## Post #269
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-20T08:50:13+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I edited Chrrox's doa5 noesis to make something that opens those 7* texch files, I only changed one single value so all credit goes to Chrrox. There's probably a lot more redundant code that could be deleted but I don't know how to do it without breaking it.

Just give the 7* files the extension .tex and the B* files tmcl as usual.



I might start adding the texture names to the google documents.
[fmt_doa5_tex.rar](https://xentaxbackup.github.io/file/5907_fmt_doa5_tex.rar)
## Post #270
- Username: moge1975
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Aug 09, 2012 6:32 pm
- Post datetime: 2012-10-20T09:33:37+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> I edited Chrrox's doa5 noesis to make something that opens those 7* texch files, I only changed one single value so all credit goes to Chrrox. There's probably a lot more redundant code that could be deleted but I don't know how to do it without breaking it.

Just give the 7* files the extension .tex and the B* files tmcl as usual.



I might start adding the texture names to the google documents.

thx  it works!!
## Post #271
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-20T10:28:46+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Hm no it doesnt work for all files, I just tested it on one and it only got the normals out, I'll keep having a look.

edit: Nevermind there's no problem, it was a specular in alpha channel thing.
## Post #272
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-10-20T11:13:41+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Can someone send me all the model files including latest dlcs?
## Post #273
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-20T11:22:02+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

This forum is for reverse engineering, not model sharing. As was stated before 'sharing of copyrighted files constitutes piracy' and you really shouldn't be asking for it here.

> Reply from Kamillho
>
> Eww... There's a way to extract perfect dress text from Kasumi pink-white outfit?

7R97U@10T10000@8F1S]]17KRG13163S10410OD121{T921HH00I
and
BRA7U@10T10000@EG1]T]17KRH131739S10510OD121{TA21HH00I

contains the hi-res 1024x1024 version.
## Post #274
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-20T15:50:26+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> This forum is for reverse engineering, not model sharing. As was stated before 'sharing of copyrighted files constitutes piracy' and you really shouldn't be asking for it here.
Kamillho wrote:Eww... There's a way to extract perfect dress text from Kasumi pink-white outfit?

7R97U@10T10000@8F1S]]17KRG13163S10410OD121{T921HH00I
and
BRA7U@10T10000@EG1]T]17KRH131739S10510OD121{TA21HH00I

contains the hi-res 1024x1024 version.
I dont understand... What I need to do?
## Post #275
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-20T15:52:57+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Use the script on my last post on the last page, rename the two files I mentioned above to anything.tex, anything.tmcl etc then open the .tex using Noesis.
## Post #276
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-20T16:36:37+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> Use the script on my last post on the last page, rename the two files I mentioned above to anything.tex, anything.tmcl etc then open the .tex using Noesis.

I don't have those files. Where are they located?
## Post #277
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-20T16:43:30+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

If you used Chrrox's bms script then they should be in the final output folder after you have run doa5decrypt.bms
## Post #278
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-20T16:53:49+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> If you used Chrrox's bms script then they should be in the final output folder after you have run doa5decrypt.bms
I totally dont understand you, because I used new simple unpacker with renamed files, but thanks for help!

Edit:

I got files, rename fro dat to tex and doesnt work
## Post #279
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-20T19:08:44+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Kamillho
>
> rman2 wrote:If you used Chrrox's bms script then they should be in the final output folder after you have run doa5decrypt.bms
I totally dont understand you, because I used new simple unpacker with renamed files, but thanks for help!

Edit:

I got files, rename fro dat to tex and doesnt work

Have fun looking for pantsu textures
## Post #280
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-20T19:10:26+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> Kamillho wrote:rman2 wrote:If you used Chrrox's bms script then they should be in the final output folder after you have run doa5decrypt.bms
I totally dont understand you, because I used new simple unpacker with renamed files, but thanks for help!

Edit:

I got files, rename fro dat to tex and doesnt work

Have fun looking for pantsu textures

Eww underwear texture are also 64x64!
## Post #281
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-10-21T06:19:08+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> This forum is for reverse engineering, not model sharing. As was stated before 'sharing of copyrighted files constitutes piracy' and you really shouldn't be asking for it here.

I think someone just sent a model file here .

> Reply from 252gt
>
> misquared wrote:I have noesis and the new script
However my PC can't take anymore space

May I ask for Kokoro's Pink Kimono (default) model please?  (This: http://images1.wikia.nocookie.net/__cb2 ... Render.png)
That's the only one I want from this game^^;

OK

Here you go

http://www.mediafire.com/?gt9vihlivmol13l

Sir, have you read this part Discuss anything related to game models here, both 3d and 2d. You can also request specific models for your game.
## Post #282
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-21T07:37:51+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Yes, it was bad enough that he asked for one model, to ask for every single one in the game is even worse. And that description is in reference to requesting a game to be reversed engineered to get the models from, not for requesting just the models alone.
## Post #283
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-10-21T09:25:38+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> Yes, it was bad enough that he asked for one model, to ask for every single one in the game is even worse. And that description is in reference to requesting a game to be reversed engineered to get the models from, not for requesting just the models alone.
Nope, nothing's wrong with that, and it means exactly what it said ; Request specific models for your game.
## Post #284
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-21T14:59:38+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from DOTAPRINCE
>
> rman2 wrote:Yes, it was bad enough that he asked for one model, to ask for every single one in the game is even worse. And that description is in reference to requesting a game to be reversed engineered to get the models from, not for requesting just the models alone.
Nope, nothing's wrong with that, and it means exactly what it said ; Request specific models for your game.

Stop with that !

We can request/share some files/sample for testing or reversing purpose, not for leech......

You want all models ? buy the game or find it under a rock, extract and decrypt them, like all others people do.

If you can't understand this, maybe a ban/kick will do ?
## Post #285
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-10-21T17:08:22+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> DOTAPRINCE wrote:rman2 wrote:Yes, it was bad enough that he asked for one model, to ask for every single one in the game is even worse. And that description is in reference to requesting a game to be reversed engineered to get the models from, not for requesting just the models alone.
Nope, nothing's wrong with that, and it means exactly what it said ; Request specific models for your game.

Stop with that !

We can request/share some files/sample for testing or reversing purpose, not for leech......

You want all models ? buy the game or find it under a rock, extract and decrypt them, like all others people do.

If you can't understand this, maybe a ban/kick will do ?
I did buy the game , like others people do. I just need steps on how to do it since I tried back reading but the methods seem complicated, if you can give me a step by step guide I'll do it myself and be grateful to you   .
## Post #286
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-21T18:28:42+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Can somebody help me?

[viewforum.php?f=10](http://forum.xentax.com/viewforum.php?f=10)

last post
## Post #287
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-22T07:01:59+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from DOTAPRINCE
>
> 
I did buy the game , like others people do. I just need steps on how to do it since I tried back reading but the methods seem complicated, if you can give me a step by step guide I'll do it myself and be grateful to you   .

> Reply from zaykho
>
> 

DOA5 - Model Tool v2.0 * UPDATE - 10/10/2012 *
----------------------------------------------------------------------------------------------------------
the v2.0 contain: 
- The Renamer Tool and the Rip Tool in only one file
the v2.0 give you: 
- The latest names from the GoogleDOC page --> https://docs.google.com/spreadsheet/ccc ... eHc#gid=27 (- 08/10/2012 - 04:05 AM - GTM+2-)
- Support now: Characters, Stages, DLC and User-Prompt update

This tool will extract/decrypt files of DOA5 and rename them automatically or manually
You just need to put the folder ( doa5_tool ) in the DOA5 folder OR the dlc "root" folder (where .bin and .lnk are) OR to just "browse" your folder for updating unknown names


Link to the tool -->
http://www.mediafire.com/?7t1kdsy9t421h9n

Link to the ultimate folder tool of DOA/NG -->
http://www.mediafire.com/?sbd2c9r8ok3u3

Edit:The ultimate folder tool of DOA/NG have been actualized and optimized

PS: This tool contains work from chroxx & others Xentax user too.

EDIT [22/10/2012]: I have fixed a bug in the stage rip --> [http://www.mediafire.com/?eaytbfmircfffj8](http://www.mediafire.com/?eaytbfmircfffj8)
## Post #288
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2012-10-22T08:08:02+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

^ 
Thank you
## Post #289
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2012-10-22T13:13:21+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

zaykho .. I can not download the fixed version 

 -- Split Archive Blocked --   

please help
## Post #290
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-10-22T14:19:26+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Me too!

I cant download too.
## Post #291
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-22T15:10:43+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Added all the textures to the google doc.
## Post #292
- Username: misquared
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Oct 26, 2010 8:32 am
- Post datetime: 2012-10-22T15:46:50+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from 252gt
>
> misquared wrote:I have noesis and the new script
However my PC can't take anymore space

May I ask for Kokoro's Pink Kimono (default) model please?  (This: http://images1.wikia.nocookie.net/__cb2 ... Render.png)
That's the only one I want from this game^^;

OK

Here you go

http://www.mediafire.com/?gt9vihlivmol13l

Alright!!! Many thanks1
## Post #293
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-22T17:07:38+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

[](http://www.hostingpics.net/viewer.php?id=728954Sanstitre2.jpg)

DOA5 - Tool v2.1 * UPDATE - 22/10/2012 *
----------------------------------------------------------------------------------------------------------
the v2.1 give you: 
- Fixed version of Stage Rip

This tool will extract/decrypt files of DOA5 and rename them automatically or manually
You just need to put the folder ( doa5_tool ) in the DOA5 folder OR the dlc "root" folder (where .bin and .lnk are) OR to just "browse" your folder for updating unknown names


Link to the tool -->
[http://www.mediafire.com/?eaytbfmircfffj8](http://www.mediafire.com/?eaytbfmircfffj8)

Link to the ultimate folder tool of DOA/NG -->
[http://www.mediafire.com/?sbd2c9r8ok3u3](http://www.mediafire.com/?sbd2c9r8ok3u3)

PS: This tool contains work from chroxx & others Xentax user too.[/quote]

EDIT: Fixed Download Link

Well it's seems that mediafire doesn't like to have 2 .zip with these names "2.0." && "2.1" in the same folder, so the  2.0 has been deleted.
## Post #294
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-22T17:16:52+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> Added all the textures to the google doc.

Nice I will update the DOA5 tool to 2.2 soon, it will includes all updates from this google doc
## Post #295
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-23T05:14:36+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Hey Chrrox, any news about the script??
## Post #296
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2012-10-23T09:32:07+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

hey guys, have you managed to get doa5 models in blender?
when i export the model head from noesis as obj and then import the obj file to blender, the model's textures seems somehow, like black and white.
(i export from noesis with -objmtl option and flipuv checked, and then add extension to textures names in mtl file)

left noesis, right blender
## Post #297
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-23T10:20:24+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

There's a specular map in the alpha channel of those textures so you'd have to turn it off.
## Post #298
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2012-10-25T07:55:52+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

rman2
tnx

ok guys.
i had a look at the file names encryption but i found the same thing chrrox found long time befor me.

the first letter in the encrypted name is the last letter in the extension of the real name
the second letter in the encrypted name is the last letter in the real file name

both letters are shifted by this array:

```
0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ 0123456789ABCDEFGHIJKLMNOPQ				- encrypted
```
i'll take the same example as  [mariokart64n did](http://forum.xentax.com/viewtopic.php?p=79697&sid=4f680c059b0d9d8fa31688dfd0a9a712#p79697):
LISA_COS_001.TMC
2R052@1S100@BM1H]]724BJ165PQ610J1N10{9721F

we look in the "decryption" arrays and see that: '2' = 'C'(last in extention) and 'R' = '1'(last in name)

but i couldn't find anytihing else, next letters are taken from the name by some algorithm, and some math is aplyed to them  if anyone find something please share it
## Post #299
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-26T20:19:52+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

i noticed the 2nd to last letter also by using the only model that ends in 011
2RD63@1S100 @C7    ]]624AP1Q031076M10P  {2R721A RTM_COS_001.tmc
2RD63@121S1 @C7    ]]724AP1Q031076M10P  {2R721A RTM_COS_011.tmc
in this example you can see as the name length increases the alphabet shifts by the same
its the number right after ]]

RIG_COS_001.TMC = 15
2R763@1S100@BG    ]]624F1CN1PQ41098N10 {R821I 
0 1 2 3 4 5 6 7 8 9 A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
U V W X Y Z 0 1 2 3 4 5 6 7 8 9 A B C D E F G H I J K L M N O P Q R S T

RTM_COS_001.TMC = 15
2RD63@1S100 @C7    ]]624AP1Q031076M10P  {2R721A
0 1 2 3 4 5 6 7 8 9 A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
U V W X Y Z 0 1 2 3 4 5 6 7 8 9 A B C D E F G H I J K L M N O P Q R S T

LISA_COS_001.TMC = 16
2R052@1S100@BM1H  ]]724BJ165PQ610J1N10 {9721F
0 1 2 3 4 5 6 7 8 9 A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
T U V W X Y Z 0 1 2 3 4 5 6 7 8 9 A B C D E F G H I J K L M N O P Q R S 

SARAH_COS_001.TMC  = 17
2R863@1S100 @6L1M1I]]8249C2PQ4104187O10 {6821D 
0 1 2 3 4 5 6 7 8 9 A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
S T U V W X Y Z 0 1 2 3 4 5 6 7 8 9 A B C D E F G H I J K L M N O P Q R
## Post #300
- Username: bondlaw
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Apr 15, 2010 5:46 am
- Post datetime: 2012-10-27T20:10:21+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> rman2 wrote:Added all the textures to the google doc.

Nice I will update the DOA5 tool to 2.2 soon, it will includes all updates from this google doc

wooopss mediafire wont let me download says is a split file and its limited, can you please fix this?  preety please
## Post #301
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-27T22:34:22+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from bondlaw
>
> zaykho wrote:rman2 wrote:Added all the textures to the google doc.

Nice I will update the DOA5 tool to 2.2 soon, it will includes all updates from this google doc

wooopss mediafire wont let me download says is a split file and its limited, can you please fix this?  preety please

> Reply from zaykho
>
> 

DOA5 - Tool v2.1 * UPDATE - 22/10/2012 *
----------------------------------------------------------------------------------------------------------
the v2.1 give you: 
- Fixed version of Stage Rip

This tool will extract/decrypt files of DOA5 and rename them automatically or manually
You just need to put the folder ( doa5_tool ) in the DOA5 folder OR the dlc "root" folder (where .bin and .lnk are) OR to just "browse" your folder for updating unknown names


Link to the tool -->
http://www.mediafire.com/?eaytbfmircfffj8

Link to the ultimate folder tool of DOA/NG -->
http://www.mediafire.com/?sbd2c9r8ok3u3

PS: This tool contains work from chroxx & others Xentax user too.
Take the red one

ps: sorry if I take some time to work on the 2.2 version, I'm busy with my job now.
## Post #302
- Username: bondlaw
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Apr 15, 2010 5:46 am
- Post datetime: 2012-10-28T23:35:07+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> ...
Take the red one

ps: sorry if I take some time to work on the 2.2 version, I'm busy with my job now.

i did and i got this 

[](http://imageshack.us/photo/my-images/849/imagenea.jpg/)

any help please ?
## Post #303
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-29T00:38:08+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from bondlaw
>
> zaykho wrote:...
Take the red one

ps: sorry if I take some time to work on the 2.2 version, I'm busy with my job now.

i did and i got this 



any help please ?

Yep:

[http://www.mediafire.com/?09r13cv3744nzlc](http://www.mediafire.com/?09r13cv3744nzlc)

See ya.
## Post #304
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-29T12:05:20+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

OK I understand why I didn't come across this bug, it's because when I'm logged into mediafire, this error does not show.

So I think this one will work.


DOA5 - Tool (v201).zip
--------------------------------------------------
[http://www.mediafire.com/?d4q1dn4z8e57lm7](http://www.mediafire.com/?d4q1dn4z8e57lm7)
## Post #305
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2012-10-29T18:40:38+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Apologies if I'm sounding like an idiot, but how would I go about getting the files out of my copy of DOA5 (Collector's Edition for 360, if you must know)? What about stuff like DLC costumes, would I need to figure out how to get them from my 360 to my computer?
## Post #306
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-10-29T20:09:39+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

put it in the cd rom
## Post #307
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-29T21:03:13+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from BakameExcalibur
>
> Apologies if I'm sounding like an idiot, but how would I go about getting the files out of my copy of DOA5 (Collector's Edition for 360, if you must know)? What about stuff like DLC costumes, would I need to figure out how to get them from my 360 to my computer?

Install the game in any 8gb pen drive and you are done.

See ya
## Post #308
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-10-29T22:15:34+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

i dont think that'll work, since it segs it in 128mb parts
## Post #309
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-29T22:36:53+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Lol trolling right now.

Seriously, check this thread:

[viewtopic.php?f=29&t=6803](http://forum.xentax.com/viewtopic.php?f=29&t=6803)
## Post #310
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2012-10-29T23:03:29+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I'm getting things setup to try that right now. Just picked up a new USB drive large enough to hold it.  

Can someone catch me up on if the system needs to be modded now to run modded games?  If a game can be extracted, can it not be then modified on the remote source (ie usb) and then still played from there with modded changes, or does updating the ISO / extracted data require some kind of signing process?

Edit: Okay, I've successfully extracted the game, created an ISO, etc.  What DOA5 'root' should I be putting the tool in? Do I need an ISO explorer or something?
## Post #311
- Username: xPreatorianx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 18, 2012 12:25 pm
- Post datetime: 2012-10-30T09:24:47+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Protocol X27
>
> I'm getting things setup to try that right now. Just picked up a new USB drive large enough to hold it.  

Can someone catch me up on if the system needs to be modded now to run modded games?  If a game can be extracted, can it not be then modified on the remote source (ie usb) and then still played from there with modded changes, or does updating the ISO / extracted data require some kind of signing process?

Edit: Okay, I've successfully extracted the game, created an ISO, etc.  What DOA5 'root' should I be putting the tool in? Do I need an ISO explorer or something?
Still requires JTAG/RGH to play a modded game. Unless you put it back into ISO form and burn it to a disc. Then it only requires the 360's drive to be flashed. (but no matter what it requires a non stock 360.)
## Post #312
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-31T04:42:51+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Table sheets updated with all the 3rd round crap dlc content.

```
AYANE_DLC_001.tmcl = BR161@1S100B@S1]]2J3B183K52E1F1QRG14N{S70051I
AYANE_DLC_002.tmc = 2S151@1S100A@S1]]J33J183K62DF1QRG15N{S70051I
AYANE_DLC_002.tmcl = BS161@1S100B@S1]]2J3B183K52E1F1QRG14N{S70051I
AYANE_DLC_003.tmc = 2T151@1S100A@S1]]J33J183K62DF1QRG15N{S70051I
AYANE_DLC_003.tmcl = BT161@1S100B@S1]]2J3B183K52E1F1QRG14N{S70051I

HAYATE_DLC_001.tmc = 2R512@1S100@BS121H]]J183Q62D75F15R6NG1{S70061H
HAYATE_DLC_001.tmcl = BR612@1S100@CS121]I]B183Q52E753F15R4NG1{S70061H

KASUMI_DLC_001.tmc = 2R963@1S100@CE1G]]I1835D2164F1PQ107ME1{R72161J
KASUMI_DLC_001.tmcl = BRA73@1S100@DF1]H]C1834E21644F1PQ104ME1{R72161J
KASUMI_DLC_003.tmc = 2T963@1S100@CE1G]]I1835D2164F1PQ107ME1{R72161J
KASUMI_DLC_003.tmcl = BTA73@1S100@DF1]H]C1834E21644F1PQ104ME1{R72161J

HITOMI_DLC_001.tmc = 2R963@1S100@CG]]I1735C644712E1PQM13192{H1R2511
HITOMI_DLC_001.tmcl = BRA73@1S100@D]H]B1734D6447125E1PQM13152{H1R2511
HITOMI_DLC_003.tmc = 2T963@1S100@CG]]I1735C644712E1PQM13192{H1R2511
HITOMI_DLC_003.tmcl = BTA73@1S100@D]H]B1734D6447125E1PQM13152{H1R2511

KOKORO_DLC_001.tmc = 2RF63@1S100@CH]]J1735C64C1E1PQPM10093610{R8611
KOKORO_DLC_001.tmcl = BRF73@1S100@D]I]B1734D64C14E1PQPM10063610{R8611
KOKORO_DLC_003.tmc = 2TF63@1S100@CH]]J1735C64C1E1PQPM10093610{R8611
KOKORO_DLC_003.tmcl = BTF73@1S100@D]I]B1734D64C14E1PQPM10063610{R8611

LEIFANG_DLC_003.tmc = 2T763@1S100@BB1G]]I183500G1J1FE1H1A8PQG18M{R751L
LEIFANG_DLC_003.tmcl = BT873@1S100@CC1]H]C183400G1J1GE12H1A8PQG17M{R751L

MILA_DLC_006.tmc = 2W052@1S100@BF1G]]00724B21G1E1PQ988M{R851G
MILA_DLC_006.tmcl = BW062@1S100@C71]H]00723C212G1E1PQ987M{R851G

dlc_aya_101_pants.tex = 7R161@10S100005@S1]]U33J128LLR3G1H1SH13O{T9J00K713
dlc_aya_101_pants.tmcl = BR161@10S10000B@S1]]2U3B128LLR3G1CH1SH13O{TAJ00K713
dlc_aya_101_pants_01.tex = 7SS71@10T100006@T1]]V33K128MMS3H1I1TG13P{U9J0061K3
dlc_aya_101_pants_01.tmcl = BSS71@10T10000C@T1]]2V3C128MMS3H1CI1TG13P{UAJ0061K3
dlc_aya_101_pants_02.tex = 7TS71@10T100006@T1]]V33K128MMS3H1I1TG13P{U9J0061K3
dlc_aya_101_pants_02.tmcl = BTS71@10T10000C@T1]]2V3C128MMS3H1CI1TG13P{UAJ0061K3
dlc_aya_101_pants_03.tex = 7US71@10T100006@T1]]V33K128MMS3H1I1TG13P{U9J0061K3
dlc_aya_101_pants_03.tmcl = BUS71@10T10000C@T1]]2V3C128MMS3H1CI1TG13P{UAJ0061K3

kasdlc001_white_wet.tex = 7R973@10S10000@7E1R]]I128JQG13176H1R105NF1{SB21JJ81K
kasdlc001_white_wet.tmcl = BRA73@10S10000@DF1]S]C128JQG13186AH1R106NF1{SC21JJ81K
kasdlc001_white_wet_02.tex = 7R973@10S10000@7R]]I127JQF1765912G1RN19162{I1S2JJ711
kasdlc001_white_wet_02.tmcl = BRA73@10S10000@D]S]B127JQF86359120G1RN19172{I1S2JJ711
kasdlc001_white_wet_03.tex = 7S97S@10T10000@8F1S]]J128KRH13176I1S105OF1{TB21J71JK
kasdlc001_white_wet_03.tmcl = BSA7S@10T10000@EG1]T]D128KRH13186AI1S106OF1{TC21J71JK
kasdlc001_white_wet_04.tex = 7T97S@10T10000@8F1S]]J128KRH13176I1S105OF1{TB21J71JK
kasdlc001_white_wet_04.tmcl = BTA7S@10T10000@EG1]T]D128KRH13186AI1S106OF1{TC21J71JK
kasdlc001_white_wet_05.tex = 7U97S@10T10000@8F1S]]J128KRH13176I1S105OF1{TB21J71JK
kasdlc001_white_wet_05.tmcl = BUA7S@10T10000@EG1]T]D128KRH13186AI1S106OF1{TC21J71JK

kok_02_01_wet.tex = 7RF73@10S10000@7R]]J127KQF176E1G1RQN10053510{SBKK811
kok_02_01_wet.tmcl = BRF73@10S10000@D]S]B127KQF186E1AG1RQN10063510{SCKK811
kok_02_01_wet_01.tex = 7SF7S@10T10000@8S]]K127LRG176E1H1SRO10053510{TBK71K2
kok_02_01_wet_01.tmcl = BSF7S@10T10000@E]T]C127LRG186E1AH1SRO10063510{TCK71K2
kok_02_01_wet_02.tex = 7TF7S@10T10000@8S]]K127LRG176E1H1SRO10053510{TBK71K2
kok_02_01_wet_02.tmcl = BTF7S@10T10000@E]T]C127LRG186E1AH1SRO10063510{TCK71K2
kok_02_01_wet_03.tex = 7UF7S@10T10000@8S]]K127LRG176E1H1SRO10053510{TBK71K2
kok_02_01_wet_03.tmcl = BUF7S@10T10000@E]T]C127LRG186E1AH1SRO10063510{TCK71K2

dlc_htm_101.tex = 7S97S@10T10000@8S]]J127KRG1765912H1SO19162{I1T2J61J2
dlc_htm_101.tmcl = BSA7S@10T10000@E]T]C127KRG86359120H1SO19172{I1T2J61J2
dlc_htm_101_01.tex = 7T97S@10T10000@8S]]J127KRG1765912H1SO19162{I1T2J61J2
dlc_htm_101_01.tmcl = BTA7S@10T10000@E]T]C127KRG86359120H1SO19172{I1T2J61J2
dlc_htm_101_02.tex = 7U97S@10T10000@8S]]J127KRG1765912H1SO19162{I1T2J61J2
dlc_htm_101_02.tmcl = BUA7S@10T10000@E]T]C127KRG86359120H1SO19172{I1T2J61J2


```


See ya.
## Post #313
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-10-31T04:56:19+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I wrote this in maxscript, to help manage and rename my files.
The form was designed to do lookup and allow custom name entry. 

It uses two text files, one with the encrypted names, and the other with your custom names
The encrypted names are in order with the list extracted from the XEX, which help with name predictions

You'll notice the reserve space would indicated the DLC was planned way in advanced.

Anyways here it is, you'll of course need 3dsmax installed to work it 




 NameTracker.zip
Manage and Rename Files Through 3dsmax (88.3 KiB) Downloaded 138 times
## Post #314
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-10-31T05:06:48+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from mariokart64n
>
> I wrote this in maxscript, to help manage and rename my files.
The form was designed to do lookup and allow custom name entry. 

It uses two text files, one with the encrypted names, and the other with your custom names
The encrypted names are in order with the list extracted from the XEX, which help with name predictions

You'll notice the reserve space would indicated the DLC was planned way in advanced.

Anyways here it is, you'll of course need 3dsmax installed to work it 


NameTracker.zip

Lol thanks. It feels weird being like an idiot matching files for one and half hour  now that you made this script.
## Post #315
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-10-31T08:44:00+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thanks for the tool Mario, will save a lot of time.
## Post #316
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-31T11:32:33+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

zaykho - Why I can't get DLC model using your tool? I copied all files in one folder and

> 

Ofc I have also those files in desktop. I have only with DLC problem. Works good with normal game files.
## Post #317
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-10-31T15:07:16+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Kamillho
>
> zaykho - Why I can't get DLC model using your tool? I copied all files in one folder and


Ofc I have also those files in desktop. I have only with DLC problem. Works good with normal game files.

I have tested and it works, you need to put the folder "doa5_tool" where all .bin and .lnk are.

[](http://www.hostingpics.net/viewer.php?id=674245Sanstitre2.jpg)
## Post #318
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-10-31T17:20:16+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Ah, silly me! Thanks! Now works fine!
## Post #319
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2012-10-31T17:36:38+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> 
I have tested and it works, you need to put the folder "doa5_tool" where all .bin and .lnk are.

I still don't have a file structure representing that, what might I be missing?  I got the data from the 360 and converted to an XISO what am I supposed to do from there to allow browsing in a normal file format so I know where to put the doa5_tool files?
## Post #320
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2012-10-31T21:40:06+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Okay, so I've transferred the DLC files for DOA5 over to a flash drive, and dumped the contents of the drive onto my computer with USBXTAF, but I still have no idea on how to actually extract the costumes and stuff out of these files. Am I missing something important? The BMS script doesn't seem to pick up on anything.
## Post #321
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2012-10-31T21:51:33+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Use Horizon and open the DLC on your USB

Then extract the content to a Folder ( e.g. DOA 5 DLC )

then copy doa5_tool folder to DOA 5 DLC folder

and then run doa5

that all ^_^
## Post #322
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2012-10-31T23:03:35+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from 252gt
>
> Use Horizon and open the DLC on your USB

Then extract the content to a Folder ( e.g. DOA 5 DLC )

then copy doa5_tool folder to DOA 5 DLC folder

and then run doa5

that all ^_^

Great! Thank that's what I needed and it worked.     Would I be using this same process on the main game?  I already installed it on a 32GB USB, but Horizon isn't recognizing it.  I'm not sure if it's the USB drive I have or not, because Horizon is not recognizing anything on it, but it is the smaller one that I have.  

Edit: Okay, got the main game to work through Horizon, but could only extract as a main file.  Still feels like I'm missing a step. 

Also, now that the tmc/l files are extracted is there anything useful I can do with those yet, or is that still a work in progress?
## Post #323
- Username: bondlaw
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Apr 15, 2010 5:46 am
- Post datetime: 2012-11-01T00:02:35+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> OK I understand why I didn't come across this bug, it's because when I'm logged into mediafire, this error does not show.

So I think this one will work.


DOA5 - Tool (v201).zip
--------------------------------------------------
http://www.mediafire.com/?d4q1dn4z8e57lm7

got it now, thanks a lot!!
## Post #324
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2012-11-01T01:10:07+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Protocol X27

mmmm....

I don't know about this method

If you have the DVD of the game, then insert it in the DVD driver of your PC
then open Xbox backup creator -> image tool -> image browser and extract everything ... that is the method I use
## Post #325
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-11-01T03:18:06+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from 252gt
>
> Protocol X27

mmmm....

I don't know about this method

If you have the DVD of the game, then insert it in the DVD driver of your PC
then open Xbox backup creator -> image tool -> image browser and extract everything ... that is the method I use

Unless you have a dvd driver compatible with xbox360 with flashed firmware you can't do that.

For protocol, you have to extract your files from your dvd. The easiest method is installing the game in a pen drive, then get the character_common.bin and character_common.lnk and then run zyahko's tool or you can do that with chrrox's bms scripts but it's gonna be too confusing for you if don't even know how to use a command line program.
## Post #326
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2012-11-01T03:23:49+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Me again! Got everything from the DLC packs extracted so far, I just need to know where the Noesis script for the model files is. Is it the one in the first post or have there been updates so far that I haven't seen?
## Post #327
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-11-01T03:32:58+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from BakameExcalibur
>
> Me again! Got everything from the DLC packs extracted so far, I just need to know where the Noesis script for the model files is. Is it the one in the first post or have there been updates so far that I haven't seen?

Page 8, check the thread.
## Post #328
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2012-11-02T01:30:14+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from 252gt
>
> Protocol X27

If you have the DVD of the game, then insert it in the DVD driver of your PC
then open Xbox backup creator -> image tool -> image browser and extract everything ... that is the method I use

Sorry to clog the thread with something mildly unrelated.... 

I finally got Xbox Backup creator installed / working, and it isn't reading anything that I have in the drive, or at least is only showing 50MB (it is a retail copy if that matters >_>  I've seen that not be helpful before. )   Any suggestions or places to look for tips? 

I've tried browsing ISO files as well for the heck of it which did nothing.
## Post #329
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2012-11-02T02:04:01+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Protocol X27
>
> 252gt wrote:Protocol X27

If you have the DVD of the game, then insert it in the DVD driver of your PC
then open Xbox backup creator -> image tool -> image browser and extract everything ... that is the method I use

Sorry to clog the thread with something mildly unrelated.... 

I finally got Xbox Backup creator installed / working, and it isn't reading anything that I have in the drive, or at least is only showing 50MB (it is a retail copy if that matters >_>  I've seen that not be helpful before. )   Any suggestions or places to look for tips? 

I've tried browsing ISO files as well for the heck of it which did nothing.
Only certain models of DVD drives can rip 360 games directly, and even then, only with custom firmware. Your best bet is to get a flash drive (16 GB should be fine), install the game to it using your 360, then using something like Horizon to rip the files off of the flash drive.
## Post #330
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2012-11-02T02:21:30+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from BakameExcalibur
>
> 
360, then using something like Horizon to rip the files off of the flash drive.

Thanks, that was the original plan which I have done. When Horizon extracts it though I'm only get a 'string' folder name full of DataXXXX files.  I've tried adding the doa5_tool folder to this and/or the parent folder, but when I run it to extract files its saying file not found.   At least with the DLC I can tell it is in more of an 'apparent' file structure.  Also Horizon isn't giving me a 'Contents' tab like it did with the DLC, thoughts?
## Post #331
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2012-11-02T23:14:17+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Protocol X27
>
> BakameExcalibur wrote:
360, then using something like Horizon to rip the files off of the flash drive.

Thanks, that was the original plan which I have done. When Horizon extracts it though I'm only get a 'string' folder name full of DataXXXX files.  I've tried adding the doa5_tool folder to this and/or the parent folder, but when I run it to extract files its saying file not found.   At least with the DLC I can tell it is in more of an 'apparent' file structure.  Also Horizon isn't giving me a 'Contents' tab like it did with the DLC, thoughts?
Hmm... not sure. Just got around to actually trying the extract-from-USB trick (finally got a flash drive big enough for the job), and now I'm running into the same issue. Hope I'm just forgetting a step somewhere...
## Post #332
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-11-02T23:31:22+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

did you use god2iso
## Post #333
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2012-11-02T23:52:53+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> did you use god2iso
Ugh, duh, thank you, I knew I was forgetting something. Extracting the ISO using wx360 seems to work fine afterwards.
## Post #334
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2012-11-03T04:02:34+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from BakameExcalibur
>
> chrrox wrote:did you use god2iso
Ugh, duh, thank you, I knew I was forgetting something. Extracting the ISO using wx360 seems to work fine afterwards.

I did use god2iso the first time before switching to the xbox backup creator method,     Am I supposed to do something after once I have the ISO file from that process?

Edit: sorry I posted before all of that sunk in.  I'm going to try the wx360 part now.
Edit2: Awesome, thanks guys, that worked.  Now I should be able to extract, will move forward on that in a couple of days. 

In the mean time, tech question.  Since Horizon allows a file to be extracted / injected, what process occurs on the Xbox 360 to prevent a modified DLC from running in relation to the signing process? Or does it not affect it all?  I'm just curious as to the conceptual workings that actually verify that a file has been altered from its original state (at least in an offline environment) since modded systems obviously allow unsigned code to run and default systems do not.
## Post #335
- Username: Mobuis
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Jan 04, 2012 3:42 pm
- Post datetime: 2012-11-06T08:56:39+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Can any one confirm that there are only DLC packs 1,2,5,6,7 ?where it seems like 1 and 2 are almost identical except for the first suit I think its ayanes suit
## Post #336
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-11-06T10:09:11+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I think that's correct, apart from there probably being a 3 and 4 relating to the devil swimsuits for ayane, tina and christie, as well as devil swimsuits for kokoro, helena and lisa, that one is entitled the divas pack.
## Post #337
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2012-11-07T18:17:15+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

can someone make a tutorial on how to get everything  working. I would like to to extract the textures and replace with new ones. I am a great artist but not so great with code and tech stuff.
## Post #338
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-11-07T21:36:32+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Any news about the script??
## Post #339
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2012-11-08T13:54:32+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

got horizon and extracted dlc and got the doa5 tool to extract the models but I don't understand how to get them to work with noesis. 
someone uploaded a model of kokoro already ectracted and I was able to open that in noesis. can someone make some simple noob steps for me to follow. not sure what I am doing wrong.
## Post #340
- Username: andthen619
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 18, 2010 7:43 pm
- Post datetime: 2012-11-08T16:36:47+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

[http://i50.tinypic.com/20pucra.jpg](http://i50.tinypic.com/20pucra.jpg)

[http://tinypic.com/view.php?pic=awfggp&s=6](http://tinypic.com/view.php?pic=awfggp&s=6)
got some textures i made but how do i now put it back together to play in game?
## Post #341
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2012-11-09T02:40:18+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I have .tmc files extracted, dropped the .py script into the proper plugins folder for Noesis and I can view the list of objects, but I cannot yet open / view anything in Noesis.  Anyone know what I missed?

I haven't used Noesis prior to this,
## Post #342
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-11-09T11:56:22+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Did you put their corresponding tmcl files in with them, renamed the same?
## Post #343
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2012-11-10T01:43:17+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from rman2
>
> Did you put their corresponding tmcl files in with them, renamed the same?

Looks like I did.  All of the .tmc files have a corresponding .tmcl file with the same name, but I notice that Noesis is only seeing the .tmc files.  Is that normal, or am I missing a plugin?  I am using the 1.4 version of the python script.  

All of the files are located in the \doa5_tool\doa5_characters_(chara_common) folder from the actual export.  

So at this point no dice. :-/
## Post #344
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2012-11-10T18:54:35+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

You need to download the version from this link;

[viewtopic.php?p=79267#p79267](http://forum.xentax.com/viewtopic.php?p=79267#p79267)
## Post #345
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2012-11-13T06:19:09+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Hmm... seems upgrading to Windows 8 partially broke the script. I can still see the models fine, but the textures don't show up.

edit: I'm an idiot; seems installing DirectX9 runtime components bring the missing textures "to life".
[Win8Noesis.jpg](https://xentaxbackup.github.io/file/5986_Win8Noesis.jpg)
## Post #346
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-11-14T01:21:39+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from BakameExcalibur
>
> 
edit: I'm an idiot; seems installing DirectX9 runtime components bring the missing textures "to life".

I thought W8 wasn't compatible with previous DX versions anymore
## Post #347
- Username: BakameExcalibur
- Rank: advanced
- Number of posts: 68
- Joined date: Wed Feb 02, 2011 8:02 am
- Post datetime: 2012-11-14T01:55:08+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from GDL
>
> I thought W8 wasn't compatible with previous DX versions anymore
Oh, it is. Don't know how people have managed to convince themselves that W8 breaks everything made before it...
## Post #348
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2012-11-15T23:09:30+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from BakameExcalibur
>
> GDL wrote:I thought W8 wasn't compatible with previous DX versions anymore  
Oh, it is. Don't know how people have managed to convince themselves that W8 breaks everything made before it...

I red somewhere that was the case, have to install and see for myself, dual boot ftw!
## Post #349
- Username: serioud
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 29, 2010 5:12 pm
- Post datetime: 2012-11-19T18:36:37+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Hi, guys. I have a several problem.

I was looking for DOA5's demo, but i can't. already realese DOA5 original, demo was gone every forum.
I want just hitomi's modeling, and i found this, Darko's link. [http://www.mediafire.com/?ycmoi5tagpfvfdh](http://www.mediafire.com/?ycmoi5tagpfvfdh)
I tried open this file with noesis. and using doa5_360.py and fmt_DOA5_NG3_tmc.py, 
but i got a message 'File could not previewed' , 'The file type coule not be determind'.
someone says 'this file was corrupted', but someone succees load this file.
It' is correct file, or corrupt file? somebody answer me....

And someone if you know DOA5's demo's link, plz make a link, i want only hitome's file. I will convert obj. 
or have a Hitomi's tmc file or any convert thing, plz send me...

I'm sorry that I can't speak English well. thx read this.
## Post #350
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-11-20T11:08:48+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from serioud
>
> Hi, guys. I have a several problem.

I was looking for DOA5's demo, but i can't. already realese DOA5 original, demo was gone every forum.
I want just hitomi's modeling, and i found this, Darko's link. http://www.mediafire.com/?ycmoi5tagpfvfdh
I tried open this file with noesis. and using doa5_360.py and fmt_DOA5_NG3_tmc.py, 
but i got a message 'File could not previewed' , 'The file type coule not be determind'.
someone says 'this file was corrupted', but someone succees load this file.
It' is correct file, or corrupt file? somebody answer me....

And someone if you know DOA5's demo's link, plz make a link, i want only hitome's file. I will convert obj. 
or have a Hitomi's tmc file or any convert thing, plz send me...

I'm sorry that I can't speak English well. thx read this.

Go here, (it's my personal sharing mediafire folders) -->
[http://www.mediafire.com/?ihz7d86bd2erh](http://www.mediafire.com/?ihz7d86bd2erh)

download CHARACTER.zip, contains all characters from the DEMO !
## Post #351
- Username: serioud
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 29, 2010 5:12 pm
- Post datetime: 2012-11-20T12:56:44+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> 
Go here, (it's my personal sharing mediafire folders) -->
http://www.mediafire.com/?ihz7d86bd2erh

download CHARACTER.zip, contains all characters from the DEMO !

Oh, dear god! THanks!! You are my hero!!
## Post #352
- Username: 123456
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 07, 2011 3:11 am
- Post datetime: 2012-11-23T18:34:06+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I want all models characters for dead or alive 5

for 3ds max
## Post #353
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-11-23T20:24:51+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from 123456
>
> I want all models characters for dead or alive 5

for 3ds max

Rip them by yourself.
## Post #354
- Username: 123456
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 07, 2011 3:11 am
- Post datetime: 2012-11-23T20:34:24+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> 123456 wrote:I want all models characters for dead or alive 5

for 3ds max

Rip them by yourself.

i don't know 

i want Ayane & Kasumi & Hitomi & Hayate for 3ds max 

All Costumes

please help me!!! 
or
Taught me
## Post #355
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-11-24T00:17:31+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from 123456
>
> Darko wrote:123456 wrote:I want all models characters for dead or alive 5

for 3ds max

Rip them by yourself.

i don't know 

i want Ayane & Kasumi & Hitomi & Hayate for 3ds max 

All Costumes

please help me!!! 
or
Taught me

Ok, do you have the game??
## Post #356
- Username: 123456
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 07, 2011 3:11 am
- Post datetime: 2012-11-24T07:46:39+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

yes
Please Help me
## Post #357
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2012-11-24T07:53:31+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Any news about script that import bones to 3ds Max ?
## Post #358
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2012-11-28T16:53:28+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

mmmmm

I have a question ?

Can anybody tell me how to extract bones with model from Ninja Gaiden 3 ?

Is there any way, script or still you can't 


and THANX



-Sorry for Bad English-
## Post #359
- Username: DarkSSJShinji
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 15, 2011 10:05 am
- Post datetime: 2012-12-05T00:34:22+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Hi there. First, I want to say that you guys are doing a 
great job with all the organization of the file names and such.

Second, for those who have bought the Round 5 DLC Pack, I'd like to contribute the file names for that pack.
Feel free to add them to the google doc.

```
MODELS
---------
BASS_DLC_001.tmc = 2R1J6@1S100B@91]]J33J1835DE1PQ4FG1N3{27613
BASS_DLC_001.tmcl = BR1J7@1S100C@91]]2J3C1834D1E1PQ3FG1N3{27613

BRAD_DLC_001.tmc = 2R145@1S100A@L1]]J33J1C9436DD1PQ4G1N{R7616
BRAD_DLC_001.tmcl = BR156@1S100B@L1]]2J3C1C9435E1D1PQ3G1N{R7616

CHRISTIE_DLC_001.tmc = 2R151@1S100@BG]1]1I172G62C10P1O1G12Q4C171NQ1{0871H
CHRISTIE_DLC_001.tmcl = BR161@1S100@C]1]I2A173G52D10P1O12G13Q4C171NQ1{0871H	

ELIOT_DLC_001.tmc = 2RK63@1S100@CH]]J173553C00E1C1DQ5I1M1{R07612
ELIOT_DLC_001.tmcl = BRK73@1S100@D]I]B173453D001E1C1DQ5I1M1{R07612

GENFU_DLC_002.tmc = 2SL63@1S100@CH]]J1735G1K175EG1QGG15M{RL82618
GENFU_DLC_002.tmcl = BSL73@1S100@D]I]B1734G1K175F1G1QGG14M{RL82618

HELENA_DLC_002.tmc = 2S052@1S100@BH1H]]J18357110C75E1D1PQ007M{R651H
HELENA_DLC_002.tmcl = BS062@1S100@CH1]I]B18347110D753E1D1PQ005M{R651H

JANNLEE_DLC_001.tmc = 2R512@1S100@BD1G]]I18396002C75E1J1PQ00G18M{R751C
JANNLEE_DLC_001.tmcl = BR612@1S100@CE1]H]B18395002D753E1J1PQ00G16M{R751C

KASUMI_DLC_007.tmc = 2X963@1S100@CE1G]]I1835D2164F1PQ107ME1{R72161J
KASUMI_DLC_007.tmcl = BXA73@1S100@DF1]H]C1834E21644F1PQ104ME1{R72161J

LEIFANG_DLC_002.tmc = 2S763@1S100@BB1G]]I183500G1J1FE1H1A8PQG18M{R751L
LEIFANG_DLC_002.tmcl = BS873@1S100@CC1]H]C183400G1J1GE12H1A8PQG17M{R751L

MILA_DLC_003.tmc = 2T052@1S100@BF1G]]00724B21G1E1PQ988M{R851G
MILA_DLC_003.tmcl = BT062@1S100@C71]H]00723C212G1E1PQ987M{R851G

TINA_DLC_002.tmc = 2S052@1S100@BH1H]]J1835CP1F11QJ15MB9{R771H
TINA_DLC_002.tmcl = BS062@1S100@CH1]I]B1834DP12F11QJ14MB9{R771H

ZACK_DLC_002.tmc = 2SB63@1S100@CT1H]71]J1936D10F1QR3N{S6DA71J
ZACK_DLC_002.tmcl = BSC73@1S100@DT1]61I]C1934E100F1QR3N{S6DA71J


TEXTURES
------------
DLC_TIN_102_01_wet.tex = 7R06S@10T10000@7I1S]]K128LRG121H1SL14O{CBT9KK91K
DLC_TIN_102_01_wet.tmcl = BR06S@10T10000@DI1]T]C128LRG121AH1SL15O{ECT9KK91K
DLC_TIN_102_01_wet_01.tex = 7S062@10S10000@6H1R]]J128KQF121G1RK14N{CBS9KK91K
DLC_TIN_102_01_wet_01.tex = BS062@10S10000@CH1]S]B128KQF121AG1RK15N{ECS9KK91K
DLC_TIN_102_01_wet_02.tex = 7T06T@10T10000@7I1S]]K128LRG121H1SL14O{CBT9K81KK
DLC_TIN_102_01_wet_02.tmcl = BT06T@10T10000@DI1]T]C128LRG121AH1SL15O{ECT9K81KK
DLC_TIN_102_01_wet_03.tex = 7U06T@10T10000@7I1S]]K128LRG121H1SL14O{CBT9K81KK
DLC_TIN_102_01_wet_03.tmcl = BU06T@10T10000@DI1]T]C128LRG121AH1SL15O{ECT9K81KK

hel_pantsu.tex = BR06S@10T10000@DI1]T]C128L8110RG9735H1F1S005O{TB0J61J
hel_pantsu.tmcl = 7R06S@10T10000@7I1S]]K128L8110RG187H1F1S003O{TA0J61J
hel_pantsu_01.tex = 7S062@10S10000@6H1R]]J128K8110QF187G1F1R003N{SA0J61J
hel_pantsu_01.tmcl = BS062@10S10000@CH1]S]B128K8110QF9735G1F1R005N{SB0J61J
hel_pantsu_02.tex = 7T06T@10T10000@7I1S]]K128L8110RG187H1F1S003O{TA051JJ
hel_pantsu_02.tmcl = BT06T@10T10000@DI1]T]C128L8110RG9735H1F1S005O{TB051JJ
hel_pantsu_03.tex = 7U06T@10T10000@7I1S]]K128L8110RG187H1F1S003O{TA051JJ
hel_pantsu_03.tmcl = BU06T@10T10000@DI1]T]C128L8110RG9735H1F1S005O{TB051JJ

htmdlc002_pants.tex = 7R87S@10T10000@8C1S]]J128K00RJ1M1J1G1K1BASH16O{TDAL71M
htmdlc002_pants.tmcl = BR87S@10T10000@DD1]T]D128K00RJ1M1J1G1DK1DBSH17O{TEAL71M
htmdlc002_pants_01.tex = 7S873@10S10000@7B1R]]I128J00QI1L1I1G1J1BARH16N{SDAL71M
htmdlc002_pants_01.tmcl = BS873@10S10000@CC1]S]C128J00QI1L1I1G1DJ1DBRH17N{SEAL71M
htmdlc002_pants_02.tex = 7T87T@10T10000@8C1S]]J128K00RJ1M1J1G1K1BASH16O{TDA61LM
htmdlc002_pants_02.tmcl = BT87T@10T10000@DD1]T]D128K00RJ1M1J1G1DK1DBSH17O{TEA61LM
htmdlc002_pants_03 = 7U87T@10T10000@8C1S]]J128K00RJ1M1J1G1K1BASH16O{TDA61LM
htmdlc002_pants_03 = BU87T@10T10000@DD1]T]D128K00RJ1M1J1G1DK1DBSH17O{TEA61LM


```


Also, is anyone willing to rig this model? You know you want to. 
[CHRISTIE_DLC_001.png](https://xentaxbackup.github.io/file/6061_CHRISTIE_DLC_001.png)
## Post #360
- Username: farakh
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Jul 13, 2012 11:11 pm
- Post datetime: 2012-12-05T18:55:14+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

How do you extract models from this game? I can use umodel to extract characters and textures from unreal engine but there dont seem to be any tutorials for noesis or quickbms, well not any simple ones with step by step instruction. I have the game and I can rip the game and extract its content with xbox backup creator, what do I do next? How do I use all these scripts posted here?
## Post #361
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-12-14T17:03:57+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Ok, Nevermind

I fixed!
## Post #362
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-12-16T00:11:05+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

can someone help decipher the hitboxes

the structures are seen in the MDLInfo block. and also once at the start of the file at offset 0x60

I don't think its a matrix, seems like min, max but what I've tried doesnt look right.
## Post #363
- Username: Milesgboy
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Jul 04, 2010 12:02 am
- Post datetime: 2012-12-16T05:27:05+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I'm not sure if I'm using the right script or not. Since I want to import NG3 models but it just give me this error. 

[http://puu.sh/1BrfN](http://puu.sh/1BrfN)
## Post #364
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2012-12-17T00:07:50+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Delete
## Post #365
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-12-17T00:49:37+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from 252gt
>
> Hi

I found this Chinese site 

http://hi.baidu.com/luis_dior/item/69e4 ... 741009b59a

It may be helpful

inside, there is a MAX script to import DOA 5 models with bones

I don't know if anybody mention it before

anyway here is the link for script
http://pan.baidu.com/share/link?shareid ... 3305297226


I was able to import model with bones, but you know that model is not align to bone

so you need to skin it and ..... ( alot of work )

I hope this will help you.


-- Sorry for bad English --

isn't that the max script mario made for research??

That script isn't even complete and has uv problems. Even the newest one is not ready yet to completely import a doa5 character in 3ds max.
## Post #366
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-12-17T03:55:31+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

lol yeah thats my script, you can see all the boxes I've tried to import.

anyways thats why I've finally posted here about it. I can't resolve the way they've encoded their hitboxes.
Any help or ideas on the encoding would be helpful

also here's the latest script, test it out and report any problems.


 TMC Praser.zip
WIP!! {DO NOT REDISTRIBUTE, SCRIPT IS NOT FINISHED!} (14.68 KiB) Downloaded 238 times
## Post #367
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2012-12-17T04:59:13+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Well
It is kind of shame 
That Chinese site didn't even credit your work

Well thanx alot mariokart


-- sorry for bad English  --
## Post #368
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-12-21T06:31:33+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Lol the forum was offline for a couple of days and it seems the last sql backup was from a day before the crash and the posts couldn't be saved.

Ok basically:

The converter works fine with bodies and ayane-kasumi boss faces and hitomi's face. The other faces as far as I have imported have weighting problems. Also, eyes and eye shadows have no uv's.

The texture I tried to unswizzle was 0x001A7000_DXT1_TX3D.dds from helena costume 02
## Post #369
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-12-23T20:31:34+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

its a typical 1024x512 3D tiled texture, the problem is from my script. data in the DDS should be written at position 0x80, but instead its at 0x78

there must be an error in my script where I read the XPR2 header. I had known about the texture support being buggy, this further supports the need for me to redo that part
## Post #370
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-12-23T21:16:09+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from mariokart64n
>
> its a typical 1024x512 3D tiled texture, the problem is from my script. data in the DDS should be written at position 0x80, but instead its at 0x78

there must be an error in my script where I read the XPR2 header. I had known about the texture support being buggy, this further supports the need for me to redo that part

Lol yeah, and It's a shame the forum was offline, I could'nt contact you.

Also don't forget the .tex files, those files have some normal bumps that need to be untiled.
## Post #371
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2012-12-24T12:29:10+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

can anyone share the script that imports weighting on body's and some faces again? It got lost during the forum crash ><

Also is there any chance to update it to support more faces?
## Post #372
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-12-24T13:40:38+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from o0Crofty0o
>
> can anyone share the script that imports weighting on body's and some faces again? It got lost during the forum crash ><

Also is there any chance to update it to support more faces?

The importer is above:

tmcpraser.zip.
## Post #373
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2012-12-24T14:07:33+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thanks but wasn't there one that imports weights too?
## Post #374
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-12-24T16:22:42+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from o0Crofty0o
>
> Thanks but wasn't there one that imports weights too?

That script imports weights, just write true in:

skinON = true

Edit:

Not all the meshes are imported with uv's in my case (kasumi_boss_cos001) the kodachi and kodachi's ropes have no uv's. What I do is to transfere weight data from one mesh generated with Mario's script to another one generated in noesis. I use a perl script called riggomatic.pl by hunter.
## Post #375
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-12-24T19:15:30+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

lol my list of bug fixing is getting ever so large 

please tell me if theres anything else wrong

anyway about the UVs, DOA5 uses 2D UVs and 4D UVs.

I don't think I implemented the use of 4D UVs, so thats probably why UVs are not all there

the goal is to be able to import and file and export it back with very little change. that is why 4D uvs are skipped, because I'm not 100% sure how to handle them in max

however chrrox likely treated the 4D ones, as normal 2D ones.
## Post #376
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-12-24T21:17:35+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

4d uvs? Doesn't max have multiple uv map channels? Usually the second one is for some kind of effect and can be tossed.
## Post #377
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-12-24T21:21:51+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from mariokart64n
>
> lol my list of bug fixing is getting ever so large 

please tell me if theres anything else wrong

anyway about the UVs, DOA5 uses 2D UVs and 4D UVs.

I don't think I implemented the use of 4D UVs, so thats probably why UVs are not all there

the goal is to be able to import and file and export it back with very little change. that is why 4D uvs are skipped, because I'm not 100% sure how to handle them in max

however chrrox likely treated the 4D ones, as normal 2D ones.

Just fix the faces weights, mesh location and the untile script and it's almost done.

This is how Kasumi looks with all the shaders:



> 4d uvs? Doesn't max have multiple uv map channels? Usually the second one is for some kind of effect and can be tossed.

The sweat and dirt maps maybe.
## Post #378
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-12-26T05:36:20+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> mariokart64n wrote:lol my list of bug fixing is getting ever so large 

please tell me if theres anything else wrong

anyway about the UVs, DOA5 uses 2D UVs and 4D UVs.

I don't think I implemented the use of 4D UVs, so thats probably why UVs are not all there

the goal is to be able to import and file and export it back with very little change. that is why 4D uvs are skipped, because I'm not 100% sure how to handle them in max

however chrrox likely treated the 4D ones, as normal 2D ones.

Just fix the faces weights, mesh location and the untile script and it's almost done.

This is how Kasumi looks with all the shaders:


4d uvs? Doesn't max have multiple uv map channels? Usually the second one is for some kind of effect and can be tossed. 

The sweat and dirt maps maybe.

Excellent !!
## Post #379
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2012-12-26T13:53:25+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Hi

Darko can you please help me with this problem

I have 2 :

1st is about Chain :


and 

2nd about the inner side of forearms as well as legs armor ( It should be RED )


They should be like this



and THANX
## Post #380
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-12-26T14:40:31+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Are you applying textures on a model imported with Mario's script??
## Post #381
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-12-26T14:42:02+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

do the materials not work ?
## Post #382
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-12-26T15:08:22+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from mariokart64n
>
> do the materials not work ?

That could be the uv problems I posted before. Also some bones names are assigned incorrectly in some models:



Kokoro dlc 004.

The weightin is correct, but names are not xD.

About materials, for skin material is taking wet base body as a diffuse texture instead of character_body_base or dusty_all or the specular map in some cases.
## Post #383
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2012-12-26T15:48:58+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I import it with Mariokart script and just make some correction of materials 

Most of the materials ( diffuse map ) are incorrect, while the others ( spec and Bumb ) are correct


so basically I check the spec and search for the correct diffuse map and change it 

I do it for chain and Armor but without luck ( although the chain map is correct from the beginning )

Before ----- After Correction



I tried with Kokoro kimono, same problem ( incorrect diffuse map )

May be I did something wrong, I am using Max 2012 and 2009
## Post #384
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-12-26T16:07:37+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

There's nothig wrong with your max. It simply has no uv's:
## Post #385
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2012-12-26T16:41:07+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thanx alot

By the way

about the pic of Kasumi with all shaders on it

If I am not wrong, this is XNALara right ?

Is it a complete model?
if yes ( can you give me the link to download it ^_^ )


and THANX
## Post #386
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-12-26T18:25:39+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from 252gt
>
> Thanx alot

By the way

about the pic of Kasumi with all shaders on it

If I am not wrong, this is XNALara right ?

Is it a complete model?
if yes ( can you give me the link to download it ^_^ )


and THANX

Yep I did the port. Only compatible with xps.

[http://xnaaral.deviantart.com/journal/X ... -338900048](http://xnaaral.deviantart.com/journal/XPS-10-9-3-Broadway-Edition-338900048)

Check your PM
## Post #387
- Username: qq99q1
- Rank: beginner
- Number of posts: 29
- Joined date: Mon Aug 01, 2011 2:51 pm
- Post datetime: 2012-12-28T23:45:47+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr


## Post #388
- Username: WoobiE
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Oct 14, 2011 12:48 pm
- Post datetime: 2013-01-02T10:40:56+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Kudos to everyone. 
Hey mariokart64n, I have tried your script to get the bones and they work, the only problem is that the weights are partly wrong. I tried it briefly on the default costume for Hitomi (tank top) and the envelope for her left leg was horizontal instead of vertical. Just wanted to let you know and yes I do know it is a WIP script. Keep it up everyone.
## Post #389
- Username: CDD Xtreme
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Jun 14, 2010 3:24 pm
- Post datetime: 2013-01-13T02:47:28+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

For Anyone Needing a Tutorial Video on How to do this I have made one.

[http://youtu.be/RcsXk2DDbzY](http://youtu.be/RcsXk2DDbzY)

Also note that I noticed the older version of the TMC Praser by Mariokart worked properly with UVWS but the New Version does not - at least for me the Eyes in the older version work properly I can see the UVWS OVerlaying EachOther in the UVUNWRAP Editor but the New version called TMC Praser (Old is called For "Research or something") Shows a tiny vertex that when selected as Element is all of the Eyes and Lids. So This is an Easy Fix, Also as you all know for certain Characters like for Helenas Face her Skinning is Way Off where as for Most Characters like Ayane her Skinning is well done.

Anyway If anyone needs more Tutorials let me know. Since I am a Game Developer I can make The Girls Easily myself and make Serious Modifications if anyone wants to do that let me know we can do some crazy stuff.

PS. All of The Files in the Video can be found On This Forum or Through Google.
Do not expect For me to give you files unless you really need them. If you are confused or need help with the video let me know.
## Post #390
- Username: CDD Xtreme
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Jun 14, 2010 3:24 pm
- Post datetime: 2013-01-13T16:50:53+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

DLC Trouble, hey guys I have gone and spent Hours getting this DLC to work.
Am I suppose to leave the DLC as 000(etc) profile and Console ID , doing so causes the Content to Show up as Valid content but in game no DLC content Shows. When I change the DLC Content ID and Profile ID to my Native IDs which works for my SaveFile (Rehash and Resign) I get a corrupted content error.

I have Used Lefluffie and Have Unlocked the content using WM360 but get 1 of those errors above. Not Happy Am I.
I have heaps of tools. Can anyone help? 

If I cant get the DLC to work then well I have the Option of Editing the Non DLC files directly but I havent heard of .link and .bin Injector yet....
## Post #391
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-01-16T01:55:48+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

any update regarding the max script??
## Post #392
- Username: WoobiE
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Oct 14, 2011 12:48 pm
- Post datetime: 2013-01-16T10:10:03+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from CDD Xtreme
>
> For Anyone Needing a Tutorial Video on How to do this I have made one.

http://youtu.be/RcsXk2DDbzY

Also note that I noticed the older version of the TMC Praser by Mariokart worked properly with UVWS but the New Version does not - at least for me the Eyes in the older version work properly I can see the UVWS OVerlaying EachOther in the UVUNWRAP Editor but the New version called TMC Praser (Old is called For "Research or something") Shows a tiny vertex that when selected as Element is all of the Eyes and Lids. So This is an Easy Fix, Also as you all know for certain Characters like for Helenas Face her Skinning is Way Off where as for Most Characters like Ayane her Skinning is well done.

Anyway If anyone needs more Tutorials let me know. Since I am a Game Developer I can make The Girls Easily myself and make Serious Modifications if anyone wants to do that let me know we can do some crazy stuff.

PS. All of The Files in the Video can be found On This Forum or Through Google.
Do not expect For me to give you files unless you really need them. If you are confused or need help with the video let me know.
Thanks man. This tutorial helped me out a lot. 

Can someone help me out with the DLC extraction? I have gotten my hands on the DLC but what do I do with them? I have tried to extract the DLC with Le Fluffie. It gives me a root folder with costume_pack files. I tried to place the DOA5 tools into the folder and run the option of "Rip DLC" but nothing works. I think I'm doing something wrong. Can ya lend me a hand please.
## Post #393
- Username: CDD Xtreme
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Jun 14, 2010 3:24 pm
- Post datetime: 2013-01-16T14:11:33+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Updates are coming, I myself got a corrupted marketplace error because I left out the DLC License tool that Mariokart used.
You can find the DLC License tool as well as using Lefluffie lying around or by getting the Xbox 360 SKD. 

Anyway heres an Update and yes Darkro that script needs fixing on Standard UVWs as well as Some Skin Weights for certain characters like Helenas Face. 

Heres my Model Modification which I will be adding for my own mod.

You can see the changes as Time Lapse. 

[http://youtu.be/jxBImXwFOkQ](http://youtu.be/jxBImXwFOkQ)

Guy who needed help, I will make another tutorial eventually, but if your in a Rush do some research or wait a few days or ask another person since I am quite busy, you can always learn yourself.
## Post #394
- Username: WoobiE
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Oct 14, 2011 12:48 pm
- Post datetime: 2013-01-17T02:29:44+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from CDD Xtreme
>
> Updates are coming, I myself got a corrupted marketplace error because I left out the DLC License tool that Mariokart used.
You can find the DLC License tool as well as using Lefluffie lying around or by getting the Xbox 360 SKD. 

Anyway heres an Update and yes Darkro that script needs fixing on Standard UVWs as well as Some Skin Weights for certain characters like Helenas Face. 

Heres my Model Modification which I will be adding for my own mod.

You can see the changes as Time Lapse. 

http://youtu.be/jxBImXwFOkQ

Guy who needed help, I will make another tutorial eventually, but if your in a Rush do some research or wait a few days or ask another person since I am quite busy, you can always learn yourself.
No worries mate I can wait, there is no rush. I'm looking forward to your stuff. Those tutorials you done were great stuff.
## Post #395
- Username: CDD Xtreme
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Jun 14, 2010 3:24 pm
- Post datetime: 2013-01-17T06:32:27+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Everyone here is the complete ready to go Helena, There might be tid bits here and their but meh Shes OVerall Great Enough.

[http://youtu.be/44wK0Di4EH8](http://youtu.be/44wK0Di4EH8)

Let me know what ye guys think?
## Post #396
- Username: CDD Xtreme
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Jun 14, 2010 3:24 pm
- Post datetime: 2013-01-17T10:22:09+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Here are some photos of the New helena in game, she looks fatter than she is supposed to be lol but still, job well done.
[http://www.coregrafx.info/sexy/moegrafx.php?res=9295](http://www.coregrafx.info/sexy/moegrafx.php?res=9295)

Scroll down to see her. You literally cant miss her .
## Post #397
- Username: WoobiE
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Oct 14, 2011 12:48 pm
- Post datetime: 2013-01-17T13:48:17+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from CDD Xtreme
>
> Here are some photos of the New helena in game, she looks fatter than she is supposed to be lol but still, job well done.
http://www.coregrafx.info/sexy/moegrafx.php?res=9295

Scroll down to see her. You literally cant miss her .
Man she looks big in-game.
I'm guessing you like girls that are a little bigger than the usual?
## Post #398
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-01-19T05:42:37+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Little update:

Mario's script works fine with doa5 demo files.
## Post #399
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-01-20T16:23:43+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

i noticed that the names for the doa5 stages textures contain information on the texture type.
_k = has transparency
_spe = baked specular
_nrm = baked normals
_base = diffuse

this doesn't work for the skins
## Post #400
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-01-23T02:02:52+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Lol I Itried Mario's script on NG3 models and got this:
## Post #401
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-01-23T18:52:40+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

i don't think it's a complete script; it's sometimes a lot of work to make sure all the different vertex formats are accounted for.
## Post #402
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2013-01-23T22:20:56+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I think the script was mainly to support DOA5 models rather than NG3 models, the script probably needs finishing to support NG3 models fully.
## Post #403
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-01-24T02:37:07+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I hit soo many unknowns, I figured I'd would take a break.

when I done with these distractions, I'll come back to this. and look at past tecmo games. they may give insight to the road blocks encountered in DOA5.

I'll make sure to share structures here as I go along encase anyone wants to join in.

currently working on xnalara and mmd re-scripts and possibly a modding suite for soul calibur 2.
## Post #404
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-01-24T03:43:10+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from mariokart64n
>
> I hit soo many unknowns, I figured I'd would take a break.

when I done with these distractions, I'll come back to this. and look at past tecmo games. they may give insight to the road blocks encountered in DOA5.

I'll make sure to share structures here as I go along encase anyone wants to join in.

currently working on xnalara and mmd re-scripts and possibly a modding suite for soul calibur 2.

Are you going to add support to pmdx format??
## Post #405
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-01-24T12:54:51+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from mariokart64n
>
> I hit soo many unknowns, I figured I'd would take a break.
I'll make sure to share structures here as I go along encase anyone wants to join in.

can you post info you have on doa5 format, or spend some time to write it if you don't have it "on paper". 

i think to make an importer for blender cycles(to speedup the learning process), and it will be cool to not "reinvent the bike" and spend my time finding something new about the format(i solemnly swear to share every thing i'll find:))

right now i'm working on converting doa5 skins to doau/doao, and i found that doau have a file size limit for a xpr per skin. it can load only xpr's smaller than 2 MegaBaits. have you found the limit for the doa5 skins?
## Post #406
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-01-24T21:28:11+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I posted my maxscript a few pages ago. refer to that for format help.

I'm not planning to type up structs until after I've inspected other tecmo games. and my structs are 80% full of unknowns.. it would be pointless to waste time typing it out

also yes I want to add PMX support, and No I haven't created a new TMC+TMCL pair yet to test file limits. (these answers come after we have got new geo in obviously...)
## Post #407
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-02-17T15:38:46+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

i've found the files table inside the doa5 executable(i was blind enough not to find it until now).
that list contains the names/types/lnk_location of all doa5 files(8027 files), including the dlc ones

a file is represented in the files table like this:
long pointer_to_the_filename
long file_type_id
long pointer_to_the_lnk_archive_name_containing_the_file

among the lnk names we can see DLC archives and such thing as "NO_LINK". i think just by "fixing" this value to point at the "right lnk name" we can change the location of any file(costume). 
changing the path for all files to "NO_LINK" could be possible to get rid of lnk files and use their content directly, placing all files on the disc along with the xbe file. also having the names offsets is possible to vary the name length, so we can make the game work with the original unencrypted filenames.
also changing the drive letter from cdrom0:\ to hdd0:\, possible could make the game read the files NO_LINK files from the hdd
the file_type value indicates is this a tmc for hair or a tmcl for face, or is it something else.

if you want to follow my steps. do:

> 1.import the doa executable in ida. see this video for howto - youtu.be/VroCdCE9mnY
>
> 
>
> 2.A)open the strings window(menu: windows->"strings window"), B)scroll down till you see the file names(you'll quickly recognize those encrypted bastards), C)scroll down to the last name and double click on it.
>
> 
>
> 
>
> 3. now in "IDA View-A" tab(window), you see the location of that filename in the code. and you see that it's referenced(a pointer is pointing at it) somewhere in the code. click that blue text just under the filename "# DATA XREF: .rdata:off_820E15F8", to follow to the place it's referenced.
>
> 
>
> 
>
> 4. here we are this is the begining of the file table. click on the byte just after the refference and press a few times on the keyboard the "D" key to convert it to "long", then do this to the next item and so one to see that bellow are referenced other file names/filetype/lnk_archive.the address for the files_table beginning is 0x820E15F8, to get the offset for the exe file you should extract 0x82000000 from it(0x820E15F8 - 0x82000000 = 0xE15F8)

[update]
simple doa5 unpacker
re-uploaded with:
- more names and *.--C to *.---C "fix"
- searched for double names and fixed the colliding names LEIFANG_HAIR_002 to LEIFANG_HAIR_001(few names where borrowed from the xentax users renamer list, that's the price paid for not checking if all names are correct)
 - and ALPHA152_COS_001 to ALPHA152_COS_001_A(that's a tricky dude you should examine, tgg instead of ttx and some other unique stuff)

i've restored a lot of names using doa5 and demo file tables information. using these names i have updated the "simple doa5 unpacker". do NOT forget about "DOA5REALNAMES.INI", if you want to rename your files automatically.

i couldn't restore the extensions for some files. doa5 has three files per costume, two are like in demo - *.tmc and *.tmcl, and one more type, with the last letter in extension "C", thus i named it *.---C. 
also doa5 has additional textures([mentioned here](http://forum.xentax.com/viewtopic.php?p=79405#p79405)) for some costumes which are stored in external files with partially known extension *.--H and *.--HL.
if you have any information about the real extensions names for these types, i'd like to hear it.
## Post #408
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-02-27T05:32:17+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Lol Tried the new dlc. One curious thing, the hotties dlc has repeated bunnie or evil bunnie swim wears.

See ya.
## Post #409
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2013-02-27T13:43:20+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Darko, did the script work for you successfully? 

When I ran it against the patch file, no files were found.  Any idea if I'm running against the wrong file (using the 200MB one), or if there's a newer version of the script I may have missed? 

Thanks
## Post #410
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-02-27T19:28:40+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Protocol X27
>
> Darko, did the script work for you successfully? 

When I ran it against the patch file, no files were found.  Any idea if I'm running against the wrong file (using the 200MB one), or if there's a newer version of the script I may have missed? 

Thanks

Yep, just run then lnk bms script on patch_02_catalog.bin and you'll have the files extracted.
## Post #411
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-02-27T21:34:37+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

have anyone succeed to extract correctly volume textures or D3DFMT_L8 textures?

i tried "unbundler.exe" but it's crashing on many unknown textures while unswizzling, also it unpacks "D3DFMT_L8" textures as grayscale:
## Post #412
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2013-02-27T21:50:35+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> Protocol X27 wrote:Darko, did the script work for you successfully? 

When I ran it against the patch file, no files were found.  Any idea if I'm running against the wrong file (using the 200MB one), or if there's a newer version of the script I may have missed? 

Thanks

Yep, just run then lnk bms script on patch_02_catalog.bin and you'll have the files extracted.

Thank you, I think the issue was that I was using the other script from a while pack.  I just tested the one in b0ny's post and that did the trick on the patch files.
## Post #413
- Username: tomatofarmer
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu May 17, 2012 7:54 pm
- Post datetime: 2013-03-03T13:51:00+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> Lol Tried the new dlc. One curious thing, the hotties dlc has repeated bunnie or evil bunnie swim wears.

See ya.

Maybe they did this so that (when you're fighting online) other players can see your bunny outfit even if they didn't pre-order/purchase it themselves. It's free advertising and slipstreaming it with another update saves them certification money.

Another possibility is that that something with the old bunny suits needed to be updated specifically for the new beach stage. Since it's now the warmest stage it's possible that it allows a greater degree of bounce than what the old suits were designed around. Or maybe it was the added motion controls? I forget when that update was added.
## Post #414
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-03-16T18:10:59+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

the island patch is useng some files not from the doa5_files_table, or maybe it's patching that table.

some names to add to the end of the "doa5realnames.ini":

> NC6_8LA]{71626]O5G8{51KB = stg_isl.tmc
>
> B15_7K9]{71687]RO6GA{51KD = stg_isl.tmcl
>
> 2RS}61M@5G1HI1{{P19A1J163} = ISLAND@1.TMC
>
> BRS}71M@571HI1{{DP1AB1J173} = ISLAND@1.TMCL
>
> 2S141K_E1FG1[]N18A1H153{ = ISLAND2.TMC
>
> BS151K_51FG1[]BN19B1H163{ = ISLAND2.TMCL

note: you can use the "simple doa5 unpacker" and it's files(source code, correct names for files...) as you wish, i would be happy if they will help you in any way(you can put even your name in it). and it's true for all my works - cheers...
## Post #415
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-03-17T19:29:46+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Know what guys, Mario's tmcpraser seems to work on razor's edge demo:



Also Chrrox's noesis script.

I used simple ninja gaiden 3 unpacker to unpack. if someone has problems finding it, You can download it from here:

[https://skydrive.live.com/#cid=FFBE4E57 ... 49FCBE!177](https://skydrive.live.com/#cid=FFBE4E570949FCBE&id=FFBE4E570949FCBE!177)

Mega lol, the demo contains:

2 Ayane Costumes, nude ayane, ayane covered with a towel and the model included in NG3.
2 kasumi costumes with 3 different hair styles (DMB).
Mizuki
And a set of different Hayabusas (normal, infected, unmasked and costume 01)

A lot of stuff considering It's just a demo.

Just rename the gmd to tmc and the ttcl to tmcl so both scripts can load them.
## Post #416
- Username: 252gt
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Aug 14, 2011 1:52 am
- Post datetime: 2013-03-18T16:05:53+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thanx Darko

I will try it ^_^
## Post #417
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2013-03-21T22:45:36+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> Know what guys, Mario's tmcpraser seems to work on razor's edge demo:



Also Chrrox's noesis script.

I used simple ninja gaiden 3 unpacker to unpack. if someone has problems finding it, You can download it from here:

https://skydrive.live.com/#cid=FFBE4E57 ... 49FCBE!177

Mega lol, the demo contains:

2 Ayane Costumes, nude ayane, ayane covered with a towel and the model included in NG3.
2 kasumi costumes with 3 different hair styles (DMB).
Mizuki
And a set of different Hayabusas (normal, infected, unmasked and costume 01)

A lot of stuff considering It's just a demo.

Just rename the gmd to tmc and the ttcl to tmcl so both scripts can load them.
How did you extract from the demo? Is it supposed to be in iso format?
## Post #418
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-03-21T23:15:29+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from DOTAPRINCE
>
> 
How did you extract from the demo? Is it supposed to be in iso format?

Download the demo from xbox live, save it in a pen drive, use an usb extractor (I don't remember the name right now) to extract the container and then use le fluffie to extract the files... or you can just download the demo from a torrent web site or direct download.
## Post #419
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2013-03-22T16:28:03+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> DOTAPRINCE wrote:
How did you extract from the demo? Is it supposed to be in iso format?

Download the demo from xbox live, save it in a pen drive, use an usb extractor (I don't remember the name right now) to extract the container and then use le fluffie to extract the files... or you can just download the demo from a torrent web site or direct download.

Well I downloaded the demo and this is the file I got.

070D4A2A77B3FF9F74B675025AF4D3C1BA0005DE4B

With no extensions. Is it the right one to use the usb extractor for?
## Post #420
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-03-22T17:03:28+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from DOTAPRINCE
>
> Well I downloaded the demo and this is the file I got.

070D4A2A77B3FF9F74B675025AF4D3C1BA0005DE4B

With no extensions. Is it the right one to use the usb extractor for?use wxPirs
## Post #421
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-03-22T19:27:20+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from DOTAPRINCE
>
> Darko wrote:DOTAPRINCE wrote:
How did you extract from the demo? Is it supposed to be in iso format?

Download the demo from xbox live, save it in a pen drive, use an usb extractor (I don't remember the name right now) to extract the container and then use le fluffie to extract the files... or you can just download the demo from a torrent web site or direct download.

Well I downloaded the demo and this is the file I got.

070D4A2A77B3FF9F74B675025AF4D3C1BA0005DE4B

With no extensions. Is it the right one to use the usb extractor for?

No, He's done well, just extract the package with this:

[http://skunkiebutt.com/Le%20Fluffie%20App.zip](http://skunkiebutt.com/Le%20Fluffie%20App.zip)
## Post #422
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2013-03-23T00:32:47+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thanks. Got it extracted.
## Post #423
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-03-23T06:57:52+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from DOTAPRINCE
>
> Thanks. Got it extracted.

No problem
## Post #424
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2013-03-25T03:19:34+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Does anyone know why I might not be able to view / extract .tmc files in Noesis? 

I have version 3971, I copied version 1.4 into the plugins/python folder & reloaded plugins, but I can still only see a list of .tmc files.  Selecting them still won't cause anything to show up...  

Really stuck on this, and need to know what I'm missing.  

Thanks.

Edit: Problem resolved. Not sure why, but I couldn't get v1.4 working.  I tried 1.5 that Darko mentioned and it worked.
## Post #425
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2013-04-03T14:26:40+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Could someone please help me understand something I'm missing in the DOA5 extraction process? 

I'm missing certain stage files that I'd like to extract, such as Sakura and the Additional Island stage files.  I noticed a file name updater.ini, but where does that play into the process and with which extractor? (Also where do I find the link for it)

Every version of 'simple unpacker' crashes anytime I try to extract from stage_common.   DOA5_tool works, BUT I only get some of the files AND most will still crash in Noesis using v1.5 of the Noesis script.  

Any light that could be shed on this would be appreciated. Thanks
## Post #426
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2013-04-06T09:37:11+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

hey guys quick question

can i use tools/scripts for NG3 to extract stuff from Ninja gaiden 3 razors edge as well?  has anyone looked into it if it has everything same as NG3?

thanks
## Post #427
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-04-06T14:15:22+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from khanbot
>
> hey guys quick question

can i use tools/scripts for NG3 to extract stuff from Ninja gaiden 3 razors edge as well?  has anyone looked into it if it has everything same as NG3?

thanks

Yes, It's the same format as DOA5.
## Post #428
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2013-04-08T16:36:16+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

hi again

i extracted NG3 razor edge files wtih simple ng3 unpacker but noesis cannot open/preview .gmd files!  I use doa5 plugin 1.5 version.  It gives me  error.  I also try renaming .gmd files to .tmc but no luck.


edit: solved.
## Post #429
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-04-08T16:58:56+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from khanbot
>
> hi again

i extracted NG3 razor edge files wtih simple ng3 unpacker but noesis cannot open/preview .gmd files!  I use doa5 plugin 1.5 version.  It gives me  error.  I also try renaming .gmd files to .tmc but no luck.

Rename .gmd to .tmc and .ttgl to .tmcl

I used this to do a batch rename, and It supports subfolders:

[http://www.advancedrenamer.com/](http://www.advancedrenamer.com/)

Where It says add method select replace, text to be replaced: gmd replace with: tmc, add the same method but now the text to be replaced: ttgl replace with: tmcl. Then, in your right windows there's a file browser where all the files that we're gonna rename will be listed. There, there's an add button, press that button, select directories and then select the folder where all your ng3re files are stored. All the files that are going to be renamed will be colored in red. After that, just press Start batch.
## Post #430
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2013-04-08T17:18:50+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

thanks for fast reply 

I renamed .gmd to .tmc and .ttgl to .tmcl but this is what i get


what can i be doing wrong?
## Post #431
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-04-08T18:53:14+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from khanbot
>
> thanks for fast reply 

what can i be doing wrong?

Nothing, the opt_blur meshes are for some kind of effect inside the game (blood??) or could be for collision detection. When importing in 3ds max just don't select them using guru wave plugin.

For mesh position I use Mario's tmc praser script to import in max and the stick it back to save the position.
## Post #432
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2013-04-09T16:58:25+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

i import using mariokart's tmc parser script, but in max i get no material applied i just get a grey model.  is this normal too?  do materials/maps needs to be applied separately after extraction with noesis or some other means?

thanks.
## Post #433
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-04-09T19:11:02+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from khanbot
>
> i import using mariokart's tmc parser script, but in max i get no material applied i just get a grey model.  is this normal too?  do materials/maps needs to be applied separately after extraction with noesis or some other means?

thanks.

Yes, It's normal and mario's Script has UV's problems, but the weights (what it's the thing that matters for us) are correct.

I'm gonna write a tutorial using smd as the medium format and how transfere vertex weights from one wesh to another using magnum's riggomatic. The process to allocate correctly the meshes is very simple and it's the same as you allocate meshes with SCIV-V, but in this case you need to reinject that data inside the tmc again to get proper static mesh in noesis.
## Post #434
- Username: blablukura
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 25, 2012 9:32 pm
- Post datetime: 2013-04-09T21:51:20+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> khanbot wrote:i import using mariokart's tmc parser script, but in max i get no material applied i just get a grey model.  is this normal too?  do materials/maps needs to be applied separately after extraction with noesis or some other means?

thanks.

Yes, It's normal and mario's Script has UV's problems, but the weights (what it's the thing that matters for us) are correct.

I'm gonna write a tutorial using smd as the medium format and how transfere vertex weights from one wesh to another using magnum's riggomatic. The process to allocate correctly the meshes is very simple and it's the same as you allocate meshes with SCIV-V, but in this case you need to reinject that data inside the tmc again to get proper static mesh in noesis.
Is that how you correct the mesh position in max ? Please do the tutorial for this because some models have meshes place in the erong position, like hair mesh attached to a waist bone, I think there is a simple way to change the mesh bone to the correct one and it will be plAced there correctly but I dont know how to do it in max
## Post #435
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-04-10T05:23:01+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from blablukura
>
> Darko wrote:khanbot wrote:i import using mariokart's tmc parser script, but in max i get no material applied i just get a grey model.  is this normal too?  do materials/maps needs to be applied separately after extraction with noesis or some other means?

thanks.

Yes, It's normal and mario's Script has UV's problems, but the weights (what it's the thing that matters for us) are correct.

I'm gonna write a tutorial using smd as the medium format and how transfere vertex weights from one wesh to another using magnum's riggomatic. The process to allocate correctly the meshes is very simple and it's the same as you allocate meshes with SCIV-V, but in this case you need to reinject that data inside the tmc again to get proper static mesh in noesis.
Is that how you correct the mesh position in max ? Please do the tutorial for this because some models have meshes place in the erong position, like hair mesh attached to a waist bone, I think there is a simple way to change the mesh bone to the correct one and it will be plAced there correctly but I dont know how to do it in max

The tutorial is similar to this:

[https://www.youtube.com/watch?v=ZA0tTKvXxrs](https://www.youtube.com/watch?v=ZA0tTKvXxrs)

Just check where the pivot of the mesh you want to position is and you will figure out on what bone you have to allign with (using alt+a in max and check pivot on both current object and target objet and also check x,y,z axis). Some times you'll need to rotate your object, also check the rotation axis.
## Post #436
- Username: blablukura
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 25, 2012 9:32 pm
- Post datetime: 2013-04-11T07:26:34+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> 

The tutorial is similar to this:

https://www.youtube.com/watch?v=ZA0tTKvXxrs

Just check where the pivot of the mesh you want to position is and you will figure out on what bone you have to allign with (using alt+a in max and check pivot on both current object and target objet and also check x,y,z axis). Some times you'll need to rotate your object, also check the rotation axis.
thanks for your explanation, I've been trying to use aligning tool too but it didn't work. for example, the file AYA_COS_04, I tried to align WGT_face (the face mesh) with the bone WGT_face, and this is what I get  
I also tried to align it with other bones too like neck, head, faceroot.....and even the body mesh...with many different settings for the Aligning too ( center, pivot point....) but it always ended up messed. What am I doing wrong ? It just doesnt work like in the tutorial with that model.....
for this mesh I can somehow move it manually to fit but sometimes for the hair, doing it manually cant make it perfectly fit .... so I'm really want to learn how to reposition it in the correct way
## Post #437
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-04-11T14:08:36+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from blablukura
>
> Darko wrote:

The tutorial is similar to this:

https://www.youtube.com/watch?v=ZA0tTKvXxrs

Just check where the pivot of the mesh you want to position is and you will figure out on what bone you have to allign with (using alt+a in max and check pivot on both current object and target objet and also check x,y,z axis). Some times you'll need to rotate your object, also check the rotation axis.
thanks for your explanation, I've been trying to use aligning tool too but it didn't work. for example, the file AYA_COS_04, I tried to align WGT_face (the face mesh) with the bone WGT_face, and this is what I get  
I also tried to align it with other bones too like neck, head, faceroot.....and even the body mesh...with many different settings for the Aligning too ( center, pivot point....) but it always ended up messed. What am I doing wrong ? It just doesnt work like in the tutorial with that model.....
for this mesh I can somehow move it manually to fit but sometimes for the hair, doing it manually cant make it perfectly fit .... so I'm really want to learn how to reposition it in the correct way

Which model is that??
## Post #438
- Username: blablukura
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 25, 2012 9:32 pm
- Post datetime: 2013-04-11T14:52:22+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> 

Which model is that??
Its AYA_COS_04.tmc (.gmd) . Most of the character models of ng3re also have this wrong position mesh problem. I m not so good withax so I dont know any othe way to fix this
## Post #439
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-04-11T19:09:18+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from blablukura
>
> Darko wrote:

Which model is that??
Its AYA_COS_04.tmc (.gmd) . Most of the character models of ng3re also have this wrong position mesh problem. I m not so good withax so I dont know any othe way to fix this

Ok, normally the body goes alligned with hips. There's a model that has rotation problem, allign it with hips (also check the rotation options), and the mesh will be rotated 90 on your x axis. Just select your mesh, go to your modifier window, select the skin modifier, roll down until you find the advance parameters, uncheck always deforms, after that, select the rotation snap and rotate 90 grades on your x axis.

For the head in that model:

Select it, then let's check the pivot point:



From that pivot point We can assume that we can not use the head or neck as a reference for the position or our mesh. Let's Use hips:



We're near, but the mesh position is not correct yet, then let's try this bone:



The bone is: WGT_acs_hair_b_1

Here is the result:



The head now is in the correct position. In this case, rotation wasn't needed.

Now the hair alligned with the Head bone (MOT01_Head):



And back hair alligned with the same bone:



Now the model is correctly assembled:



The next step, make a a new folder for your proyect, copy your tmc and tmcl files there (do not use the original files) because we're going to modiy the tmcl file by reinjecting back the geometry.

Back in max, with our model correctly assembled, Run the stick it back script, open the tmcl file inside of your project folder and just hit yes when it asks if you want to replace it. Start by selecting the meshes you located (one by one) and select inject vertices. Repeat the process until you have finished. The scene and the model you imported export it to whatever.smd (I use body) using am smd plugin exporter. Now, in Noesis, we're going to have something like this:



Export it as .obj with the next options:



Import your new model in max, without importing the OPTblur meshes, assign textures, attach all your meshes in only one mesh, convert to editable mesh, enter in vertex selection mode, select all your vertices and weld them by 0.001 to smooth the model. Export it as whatever.smd inside your project folder and we're almost done.

Download rig-o-matic by hunter from my skydrive (thanks to the resident evil modding forum) 

[https://skydrive.live.com/#cid=FFBE4E57 ... 49FCBE!177](https://skydrive.live.com/#cid=FFBE4E570949FCBE&id=FFBE4E570949FCBE!177)

Unpack, run the executable and where it says source model, select the first model you exported (the one with skeleton and the skin modifier). where It says unrigged, we're going to select the model you exported from the modified tmcl. Click on the rig button and It will start the process. The process can last from 2 or 3 minutes until 1 hour (depending how complex your model is). After that, you're going to get a secondmodelnameexported_rigged.smd. At this point we're done. Just Import your rigged model in max and reassign textures and that's all.
## Post #440
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-04-11T19:17:43+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

And this is how ayane looks like with bones in noesis after all the process:
## Post #441
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-05-02T10:11:00+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Sorry,stupid question. Can i use,for example hitomi head+hair from demo version to hitomi body from free dlc?can it works?and how to assemble head part and body part into full body in 3ds max so they become one part?can anyone give me tutorial?all help i apreciate
## Post #442
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2013-05-02T15:47:55+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from aagems
>
> Sorry,stupid question. Can i use,for example hitomi head+hair from demo version to hitomi body from free dlc?can it works?and how to assemble head part and body part into full body in 3ds max so they become one part?can anyone give me tutorial?all help i apreciate

This is similar to what happens with models from other games that handle body and head separately, check the second post of this thread I think it will help you:

[http://www.gildor.org/smf/index.php/topic,478.0.html](http://www.gildor.org/smf/index.php/topic,478.0.html)
## Post #443
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-05-03T01:19:42+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from aagems
>
> Sorry,stupid question. Can i use,for example hitomi head+hair from demo version to hitomi body from free dlc?can it works?and how to assemble head part and body part into full body in 3ds max so they become one part?can anyone give me tutorial?all help i apreciate

Supposedly Yeah, It should work, just rename the root bone (the bone where all the bones are parented) to the model's head name.
## Post #444
- Username: synce
- Rank: n00b
- Number of posts: 12
- Joined date: Tue May 01, 2012 2:26 pm
- Post datetime: 2013-05-03T04:32:11+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Can someone help, I'm trying to extract the models from DOA5's latest bikini pack on PS3 (to use with XNALara) but I ran into a problem. 

I used the scripts in DOA5 Tool v201 to get the files out of the DLC, everything went fine except it can't rename the files. I can see the TMC files in a hex editor but not the TMCL files, and they won't open in Noesis either. Does that mean they're not properly decrypted? Is my Noesis plugin outdated?

Kasumi's TMC: 2Q963R1@131@CE1G]]I1835D2164F1PQ107MF1{R72161J
Maybe her TMCL: BQA73R1@131@DF1]H]C1834E21644F1PQ104MF1{R72161J

Both the TMC and TMCL hex data looked like gibberish before running the scripts, but not anymore

UPDATE: Found out the problem, I didn't place the plugin in the py subfolder. After doing so, I get this error when opening the TMC:

```
Noesis Python Error
---------------------------
Traceback (most recent call last):
  File "F:\noesisv40798\plugins\python\doa5_360.py", line 341, in tmcLoadModel
    vbase = VtxLay[vindex]
IndexError: list index out of range
```


UPDATE 2: Tried all the other TMCL files with matching names but same error
UPDATE 3: Tried ver1.4 of the plugin (was using 1.5) and the error disappeared, the TMC loads, but there's no model. I give up 
[2013-05-03_004414.png](https://xentaxbackup.github.io/file/6377_2013-05-03_004414.png)
## Post #445
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2013-05-03T19:16:05+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

How extract DOA5 demo models?
## Post #446
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-05-03T20:34:50+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from synce
>
> Can someone help, I'm trying to extract the models from DOA5's latest bikini pack on PS3 (to use with XNALara) but I ran into a problem. 

I used the scripts in DOA5 Tool v201 to get the files out of the DLC, everything went fine except it can't rename the files. I can see the TMC files in a hex editor but not the TMCL files, and they won't open in Noesis either. Does that mean they're not properly decrypted? Is my Noesis plugin outdated?

Kasumi's TMC: 2Q963R1@131@CE1G]]I1835D2164F1PQ107MF1{R72161J
Maybe her TMCL: BQA73R1@131@DF1]H]C1834E21644F1PQ104MF1{R72161J

Both the TMC and TMCL hex data looked like gibberish before running the scripts, but not anymore

UPDATE: Found out the problem, I didn't place the plugin in the py subfolder. After doing so, I get this error when opening the TMC:
Code: Select all---------------------------
Noesis Python Error
---------------------------
Traceback (most recent call last):
  File "F:\noesisv40798\plugins\python\doa5_360.py", line 341, in tmcLoadModel
    vbase = VtxLay[vindex]
IndexError: list index out of range

UPDATE 2: Tried all the other TMCL files with matching names but same error
UPDATE 3: Tried ver1.4 of the plugin (was using 1.5) and the error disappeared, the TMC loads, but there's no model. I give up

Different format, or at least there are some differences. I had tried with ps3 files some time ago.
## Post #447
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-05-04T12:21:21+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from synce
>
> the TMC loads, but there's no model. I give up
afaik there are no tools that understand the ps3 tmc's, tough you can extract them.
## Post #448
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-05-04T16:01:47+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from GDL
>
> aagems wrote:Sorry,stupid question. Can i use,for example hitomi head+hair from demo version to hitomi body from free dlc?can it works?and how to assemble head part and body part into full body in 3ds max so they become one part?can anyone give me tutorial?all help i apreciate 

This is similar to what happens with models from other games that handle body and head separately, check the second post of this thread I think it will help you:

http://www.gildor.org/smf/index.php/topic,478.0.html

Ok,thanks for the info
## Post #449
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-05-05T14:58:47+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Can anyone reupload simple_doa5_unpacker.zip in page 28 to another file hosting?my ISP having a problem downloading from rghost.net. And for latest dlc (hottie swimsuit+zack island),i always had an error when opening it in noesis.Anyone got the same problem? i'm unpacking it using doa 5 tool from zaykho mediafire folder,and even in earliest dlc some file doesnt named correctly.



please help..
## Post #450
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-05-07T18:52:30+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from aagems
>
> Can anyone reupload simple_doa5_unpacker.zip in page 28 to another file hosting?my ISP having a problem downloading from rghost.net. And for latest dlc (hottie swimsuit+zack island),i always had an error when opening it in noesis.Anyone got the same problem? i'm unpacking it using doa 5 tool from zaykho mediafire folder,and even in earliest dlc some file doesnt named correctly.



please help..

Let me take a look at this, (long time didn't mod some doa) I will see if I can update my tool to the latest name & unpacking function that other users has created.

I think I have the "simple_doa5_unpacker.zip" that you want:

Go here -->
[http://www.mediafire.com/?sbd2c9r8ok3u3](http://www.mediafire.com/?sbd2c9r8ok3u3)

And choose DOA5 - Simple DOA5 Unpacker (February 17 2013).zip
## Post #451
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-05-08T19:02:23+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Thanks zaykho  .Now it named properly and i can view it on noesis the hottie swimsuit using updated version of simple doa5 unpacker from the link you give.Oh,i have a question.I'm using tmc parser script from mariokart64n but it seems can only load one object at a time,when i open another part,the previous object that i open is disappear.So,how can i assemble those body part in one piece using tmc parser in one scene?or is it not possible for now?if its possible,can you give me tutorial?
## Post #452
- Username: Artunia
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 08, 2010 2:12 am
- Post datetime: 2013-05-09T08:44:56+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Hi guys
I want to know what the latest version of chrrox script?
## Post #453
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-05-09T12:23:36+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from aagems
>
> I'm using tmc parser script from mariokart64n but it seems can only load one object at a time,when i open another part,the previous object that i open is disappear.So,how can i assemble those body part in one piece using tmc parser in one scene?or is it not possible for now?if its possible,can you give me tutorial?

Sorry, can't help you on this part because I didn't tried yet this "tmc parser". Maybe Darko or even Mariokart64n will be able to help you.

I updating right now my DOA 5 tool, it will be an .exe file, it will have more options and will be able to decrypt/extract both type of DOA5 (demo & retail), plus, it will have an "auto-extract" noesis fully  configured for doa5 models.

Just need to wait. :p

EDIT: Well no, I will make it better, its time to make a " DOA Center ", an .exe where all doa app (3,4,5,xbv,paradise) will be merged and used with good graphics for a better user friendly interface. :p
## Post #454
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-05-09T14:09:32+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> aagems wrote:I'm using tmc parser script from mariokart64n but it seems can only load one object at a time,when i open another part,the previous object that i open is disappear.So,how can i assemble those body part in one piece using tmc parser in one scene?or is it not possible for now?if its possible,can you give me tutorial?

Sorry, can't help you on this part because I didn't tried yet this "tmc parser". Maybe Darko or even Mariokart64n will be able to help you.

I updating right now my DOA 5 tool, it will be an .exe file, it will have more options and will be able to decrypt/extract both type of DOA5 (demo & retail), plus, it will have an "auto-extract" noesis fully  configured for doa5 models.

Just need to wait. :p

EDIT: Well no, I will make it better, its time to make a " DOA Center ", an .exe where all doa app (3,4,5,xbv,paradise) will be merged and used with good graphics for a better user friendly interface. :p

Ok,maybe i just wait darko or mario to respond then.Wow,your idea look cool!! a combined all doa tool in one,must be great!!!can't wait to see it
## Post #455
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-05-09T23:11:01+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I'm just leaving this here:

[https://www.youtube.com/watch?v=hJg34xkx7GI](https://www.youtube.com/watch?v=hJg34xkx7GI)

So the guy requesting PS3 crap just wait for the 360 release It's almost possible that the format is the same as DOA5 and RE, and It'll contain all the DLC crap from DOA5 plus.

I don't understand this kind of practices when the game doesn't even have a year since It was released.
## Post #456
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-05-10T05:14:28+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> I don't understand this kind of practices when the game doesn't even have a year since It was released.i wonder if this new version is with blackjack and hookers. if so then it's worth any money   

this is the list of "selectable" characters from doa5demo: PAI, SARAH, AKIRA, MILA, RIG, SHIDEN, KASUMI_A, GENRA, RAIDOU, BAYMAN, RTM, HITOMI, CHRISTIE, BRAD, BANKOTSUBOU, ALPHA152, LISA, ELIOT, AYANE, LEIFANG, HAYATE, KOKORO, BASS, LEON, HELENA, GENFU, KASUMI, HAYABUSA, EIN, JANNLEE, TINA, ZACK. i hope this time no one will be left behind...
## Post #457
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-05-10T09:27:10+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> I'm just leaving this here:

https://www.youtube.com/watch?v=hJg34xkx7GI

So the guy requesting PS3 crap just wait for the 360 release It's almost possible that the format is the same as DOA5 and RE, and It'll contain all the DLC crap from DOA5 plus.

I don't understand this kind of practices when the game doesn't even have a year since It was released.

God dam !

Lei Fang is so cute with this new orange and white dress (even with this new ugly face)......wow.........

Momiji !!!!
I have dreamed many hours to play with her on DOA  :p


Please tecmo, do a DOAX with momiji 
(or I will finish my html5 doax.....  )

So now: Lei Fang > Momiji > kokoro > Ayane

[](http://www.hostingpics.net/viewer.php?id=547181leifang3dsexperimentbyx2gond5yr0xg.jpg)[](http://www.hostingpics.net/viewer.php?id=143456leifang3dsrender2byx2gond600b76.jpg)

[](http://www.hostingpics.net/viewer.php?id=753271momijibyarai1986d60rwae.png)[](http://www.hostingpics.net/viewer.php?id=621577momijibystickloved5waen8.jpg)

[](http://www.hostingpics.net/viewer.php?id=6903413dsrenderrequestkokoro3byx2gond5zrflt.jpg)[](http://www.hostingpics.net/viewer.php?id=389311kokoro3dsrenderbyx2gond5yyb85.jpg)

[](http://www.hostingpics.net/viewer.php?id=889387ayane3dsrenderbyx2gond5zgkhq.jpg)[](http://www.hostingpics.net/viewer.php?id=316305ayane3dsrender4byx2gond60h2ge.jpg)
## Post #458
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-05-12T13:51:17+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

doa5 tmc to blender 2.67 importer (test) - the result of some tests in importing do5 to blender. don't expect much from it.

things i hate the most about blender right now:
- blender don't support normals
- can't assign correctly the doa5 texture with a specular_map in alpha channel, because you cant stop the alpha affecting the diffuse colors

- blender doesn't understand dds volume textures
## Post #459
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2013-05-18T14:34:26+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Quick Notes: Thanks to those of you who are still putting work into this game.  The tools are still continuing to be a huge help.  

Been working on some XNALara porting recently, and didn't notice until someone brought it up.  Rig's head doesn't convert properly at all either in Noesis or through the 3dmsax .tmc script.  Does anyone know of any work arounds, or potential updates to the scripts that might help with that in the future.  

Thanks.
## Post #460
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-05-20T20:23:26+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Nice Boobs and Nice picture    My head spinning everytime seeing those boobs
## Post #461
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-05-21T00:42:53+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from aagems
>
> Nice Boobs and Nice picture    My head spinning everytime seeing those boobs
 

the picture come from a devianart user:

[http://x2gon.deviantart.com/gallery/25894032](http://x2gon.deviantart.com/gallery/25894032)
## Post #462
- Username: b0ny
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Sat May 22, 2010 5:10 pm
- Post datetime: 2013-05-24T18:47:09+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

doa5(tmc)\ng3(gmd) to blender 2.67 importer (test 2) - the result of some tests in importing do5 to blender. don't expect much from it.

+ weighted skeletons for models(wrong weights for faces)
+ attempt for ninja gaiden 3 - gmd support(wrong weights)
- no fix for rig's and brad's heads
- blender's internal render doesn't support backface culling(ugly renderings)
- blender doesn't support node bones (the skeleton is a little mess)
still no sure how to import correctly the texture maps

[edit]
hotfixed transparency bug on kas04 and reuploaded. the link works now
## Post #463
- Username: WoobiE
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Oct 14, 2011 12:48 pm
- Post datetime: 2013-05-29T06:15:12+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I'm trying to import the stages into 3ds max. I can't seem to get the material library to match up with the texture files. I use Noesis and convert with the extra option of -objmtl but it does not seem to work. Any advice would be great. I also use Maya and Blender so if the solution lies with another program I can use all 3 of them.

With zaykho's NG3 simple unpacker and Noesis script, does it work on NG3 Razors Edge or only NG3. I tried to use it on the NG3:RE and I got an error. Not sure if I was doing something wrong.
## Post #464
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-05-29T11:42:10+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from WoobiE
>
> With zaykho's NG3 simple unpacker and Noesis script.

Wait, wait, wait, it's not my "NG3 simple unpacker and Noesis script", I just make a folder where everybody can download everything easily about DOA. Nothing else !

I'm not the owner of those scripts, the only thing who was made by me is the "Doa5 tool".
## Post #465
- Username: WoobiE
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Oct 14, 2011 12:48 pm
- Post datetime: 2013-05-29T11:47:11+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from zaykho
>
> WoobiE wrote:With zaykho's NG3 simple unpacker and Noesis script.

Wait, wait, wait, it's not my "NG3 simple unpacker and Noesis script", I just make a folder where everybody can download everything easily about DOA. Nothing else !

I'm not the owner of those scripts, the only thing who was made by me is the "Doa5 tool".
Oh ok, sorry my bad. Since you have been hosting them I thought you made it as well. 

But yeah, do you have any clues to the problems that I ran into?
## Post #466
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-05-29T13:50:08+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> But yeah, do you have any clues to the problems that I ran into?

No sorry, I have stopped to work into my html5 DOA (temporarily), so I didn't go further yet.

Darko can help you.
## Post #467
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2013-05-30T14:43:33+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

This may be a rather complicated question, but is anyone familiar with differences between the DOA5 .tmc/l's and the NG3RE tmc/l's?

I injected one from NG3:RE into DOA5.  The Geometry worked, but the materials did not.  I don't understand the containers well enough yet to know what needs to be removed from the Ninja Gaiden one without screwing up the file. 

Thanks
## Post #468
- Username: MuffinMan123
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Feb 25, 2011 10:36 am
- Post datetime: 2013-06-11T20:26:50+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

finally I can update the 3D model for rachel 

the only 3D model that was floating around the internet was her old face with those fat lips from ninja gaiden 1 

sigma 2 was largely ignored because ninja gaiden 2 code was already done, but that's all in the past, now that we already have the code for dead or alive 5, ultimate's data structure will probably be very similar, I can finally have up to date 3D model for rachel. 

5 years of waiting is finally over, thx for all of your work
## Post #469
- Username: kasake
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Feb 16, 2012 3:03 pm
- Post datetime: 2013-08-19T15:00:52+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I'm this problem when I try to load the HELENA_FACE.TMC



I'm using the latest version of noesis (v4.0847) with the doa5_360.py plugin. As for the data extraction, I used the latest version of QuickBMS(v0.5.24b), chrrox's .bms files for ripping the data, extacting, and decrypting. My decrypted file name for Helena's face is 240J2_9F912F31]9161G16]]2573OC1DL000I0E{NF.dec, which I changed to HELENA_FACE.TMC

This happens to a couple other files as well when I try to load them in Noesis. I saw 2 separate posts of people successfully extracting Helena with long hair and one of her DLC costumes. Can anyone tell me what's wrong?
## Post #470
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-08-19T17:27:48+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from kasake
>
> I'm this problem when I try to load the HELENA_FACE.TMC



I'm using the latest version of noesis (v4.0847) with the doa5_360.py plugin. As for the data extraction, I used the latest version of QuickBMS(v0.5.24b), chrrox's .bms files for ripping the data, extacting, and decrypting. My decrypted file name for Helena's face is 240J2_9F912F31]9161G16]]2573OC1DL000I0E{NF.dec, which I changed to HELENA_FACE.TMC

This happens to a couple other files as well when I try to load them in Noesis. I saw 2 separate posts of people successfully extracting Helena with long hair and one of her DLC costumes. Can anyone tell me what's wrong?

Use this to unpack:

[http://rghost.ru/download/47261913/08d2 ... er_v44.zip](http://rghost.ru/download/47261913/08d2ba0661f8813e44834b7887cbfb83ab7b8af3/simple_doa5_unpacker_v44.zip)

And check this thread, there are some blender importers for DOA games, and the DOA5 importer supports bones and vertex weights.

[viewtopic.php?f=16&t=6392&start=540](http://forum.xentax.com/viewtopic.php?f=16&t=6392&start=540)
## Post #471
- Username: paradoxflyer
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 05, 2012 10:49 pm
- Post datetime: 2014-05-01T03:07:25+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

I need help to apply textures to models extracted with noesis, I'm using 3ds max but I'm havign problems with the coordinates, if somebody can share a tutorial or provide some help would be great.
## Post #472
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2014-05-01T07:55:35+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from paradoxflyer
>
> I need help to apply textures to models extracted with noesis, I'm using 3ds max but I'm havign problems with the coordinates, if somebody can share a tutorial or provide some help would be great.

If you have already extracted the models with Noesis, then you must have the OBJ file and TGA texture files with you.
Then import the obj inside Max then apply unwrap uvw modifier, and check the UVs, then you can get an overall idea which is the respective texture for that mesh.
## Post #473
- Username: paradoxflyer
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 05, 2012 10:49 pm
- Post datetime: 2014-05-04T23:54:42+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from blackfoxeye
>
> paradoxflyer wrote:I need help to apply textures to models extracted with noesis, I'm using 3ds max but I'm havign problems with the coordinates, if somebody can share a tutorial or provide some help would be great.

If you have already extracted the models with Noesis, then you must have the OBJ file and TGA texture files with you.
Then import the obj inside Max then apply unwrap uvw modifier, and check the UVs, then you can get an overall idea which is the respective texture for that mesh.

Thank you very much you solve my problem, it's easier than I thought.
## Post #474
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2015-02-23T02:54:18+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Hi, I ask for help.
Someone can help me export Fiend Bow of Ryu Hayabusa from NG3? ^^
## Post #475
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-02-23T05:11:52+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from ngovandang
>
> Hi, I ask for help.
Someone can help me export Fiend Bow of Ryu Hayabusa from NG3? ^^

Do you have any image of the weapon??
## Post #476
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2015-02-24T17:19:17+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> ngovandang wrote:Hi, I ask for help.
Someone can help me export Fiend Bow of Ryu Hayabusa from NG3? ^^
Do you have any image of the weapon??

Here [http://vignette1.wikia.nocookie.net/nin ... 0415203748](http://vignette1.wikia.nocookie.net/ninjagaiden/images/0/0b/Lock-On_Bow.png/revision/latest?cb=20120415203748)

^^! if you has more free time, then help me e port his arrows too 
hehe
## Post #477
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-02-25T17:14:20+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from ngovandang
>
> Darko wrote:ngovandang wrote:Hi, I ask for help.
Someone can help me export Fiend Bow of Ryu Hayabusa from NG3? ^^
Do you have any image of the weapon??

Here http://vignette1.wikia.nocookie.net/nin ... 0415203748

^^! if you has more free time, then help me e port his arrows too 
hehe

Ok, What scale you need and do want it skinned or just the mesh??
## Post #478
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2015-02-26T12:39:48+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
>  Ok, What scale you need and do want it skinned or just the mesh??
 Sorry, my English is very bad. But I think you ask about I want a model with bones or just mesh, right?   

hmm... I want a model with bones!
## Post #479
- Username: Cubeburner
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 11, 2011 2:53 pm
- Post datetime: 2015-03-03T09:09:35+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Does this script still have issues with various DOA5 characters? Or have they been fixed in a revision?

EDIT: Hmm... can't even download Noesis. Does anyone have a link to their version they could share? I get a "Senor is dead" message when I try to download.
## Post #480
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-03-03T14:52:54+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Cubeburner
>
> Does this script still have issues with various DOA5 characters? Or have they been fixed in a revision?

EDIT: Hmm... can't even download Noesis. Does anyone have a link to their version they could share? I get a "Senor is dead" message when I try to download.
[http://richwhitehouse.com/index.php?con ... sv4145.zip](http://richwhitehouse.com/index.php?content=inc_projects.php&filemirror=noesisv4145.zip)
## Post #481
- Username: Cubeburner
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 11, 2011 2:53 pm
- Post datetime: 2015-03-03T21:56:54+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from Darko
>
> Cubeburner wrote:Does this script still have issues with various DOA5 characters? Or have they been fixed in a revision?

EDIT: Hmm... can't even download Noesis. Does anyone have a link to their version they could share? I get a "Senor is dead" message when I try to download.
http://richwhitehouse.com/index.php?con ... sv4145.zip
Thanks mate!
## Post #482
- Username: Cubeburner
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 11, 2011 2:53 pm
- Post datetime: 2015-03-05T02:36:25+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

Something seems odd... I'm getting no error when I'm viewing the TMC files, but the preview window comes up blank.
I can't export either - it throws a "Nothing to export!" log message.

This is what I see:


Did something go wrong, am I using an outdated version of the plugin, or do I need Python installed?

EDIT: Sorry, had the wrong plugin installed. Now it works with the doa5_360.py plugin. The one in the first post may be defective.
## Post #483
- Username: nampukkk
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 28, 2016 12:34 am
- Post datetime: 2017-08-08T19:04:25+00:00
- Post Title: Re: Ninja Gaiden 3 (NG3) / Dead or Alive 5 (DOA5) noesis scr

> Reply from chrrox
>
> Here is a version1 of a noesis script to import these models.
what is done
1.Geometry import
2.Uv sets assigned
3.textures are loaded but not assigned.
4.material creation and assignment
what is left.
2.reading in the model skeleton
3.assign bones and weights to the model.

DOA5 BMS
Code: Select allendian BIG
open FDSE "trial.lnk" 0
open FDSE "archive_order.bin" 1
goto 0x8 1
get files long 1
goto 0x24 1
savepos offset 1
for i = 0 < files
goto offset 1
get noff long 1
get arcnum long 1
get id long 1
savepos offset 1
goto noff 1
get name string 1
putarray 0 i name
next i
getarray name 0 0
putarray 0 files name
goto 0xC
get files long
get unk01 longlong
get unk02 longlong
for i = 0 < files
get offset longlong
get zsize longlong
get size longlong
get arc longlong
set id i
math id + 1
getarray name 0 id
if zsize == size
log name offset size
else
clog name offset zsize size
endif
next i
