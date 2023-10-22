## Post #1
- Username: RunaWhite
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-23T22:10:21+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

Supports Models with 
Bones
Weights
Materials
Morph Target Facial Animation
bnd extractor

```
goto 0x10
get files long
set base 0x20
for i = 0 < files
goto base
get null long
get size long
get offset long
get type long
get nameoff long
savepos base
goto nameoff
get name string
log name offset size
next i
cleanexit

```


[fmt_EnchantedArms_mdl.7z](https://xentaxbackup.github.io/file/6793_fmt_EnchantedArms_mdl.7z)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-11-24T00:26:19+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

nice; doing some older games for a change huh?
## Post #3
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-11-24T20:20:00+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

I just wanted to say a big thank you to you, chrrox. You always work on so many games, many of which with a very complicated format, and it's because of awesome people like you (and howfie) that we can play around with all of these great game models. Your work is so much appreciated.
## Post #4
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2013-11-25T06:05:26+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

OH REALLY THANK YOU... Muchas Gracias, Domo Arigato, Merci, Molto graccie.   

You have no idea of how desperated I was for ripping and converting the models from this game...   

The Taigalion, The white Tiger, Omega, The Queen of ice... those amazingly sexy golem models... and now... those models will be on my reach. Fully rigged and fully textured... OMG. if this is a dream... I hope to NEVER WAKE UP!!!!!
## Post #5
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2013-11-25T13:33:20+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

What do I use to get the mdl from the bnd's?
The first script just gives me bnd's again.
(PS3 ultimate edition version)
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-26T01:36:31+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

\BLJS10003\PS3_GAME\USRDIR\chr\c0000comp.bnd
extracts to
00000800.bnd
extracts to
c0000.mdl
c0000.tbnd
c0000.smd
c0000.m2a
c0000.cma
## Post #7
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2013-11-26T01:48:29+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

> Reply from rexil
>
> What do I use to get the mdl from the bnd's?
The first script just gives me bnd's again.
(PS3 ultimate edition version)

i need to know how to exactly perform the extraction... becuz Noesis can't read or export BNDs.

I only can access MDLs and TBNDs using the scripts of the file.
plz help me... i waited desperately for this and I dunno how to use the script code on the first post... thanks in advance Chrrox.

PS: Sorry if I am a total nOOb at scripting... but the only known programing language I ever used was GW Basic, and I almost forgot everything I learned from it... 
I'm 33 years old.
## Post #8
- Username: Farlavor
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-26T01:58:40+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

download quickbms
run
quickbms.exe c:\bnd.bms c:\c0000comp.bnd c:\Extracted\c0000\
it will extract 00000800.bnd into that folder
now run quickbms again on
00000800.bnd
and you will get the model files.
## Post #9
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2013-11-26T02:25:20+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

Maybe the version I have have something different with the files? (BLES00049)
## Post #10
- Username: rexil
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-26T02:36:37+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

run offzip on that
offzip -a c:\file.bnd c:\extract 0
## Post #11
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2013-11-26T03:42:39+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

> Reply from chrrox
>
> download quickbms
run
quickbms.exe c:\bnd.bms c:\c0000comp.bnd c:\Extracted\c0000\
it will extract 00000800.bnd into that folder
now run quickbms again on
00000800.bnd
and you will get the model files.

I cannot, it gives me an error saying it cant read 1 byte or wathever the heck is that... I managed to extract the BNDs
succesfully with 4gb files version, anyway when I try this on CMD, it always gives me an error saying "wrong command-line argument C:\bnd.bms" . so I think I only can do it on Windows... What can I do to solve this? should I write quickbms.exe c:\bnd.bms c:\wathever the file it is.bnd c:\name of folder\c0000\????
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-26T03:46:29+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

just run offzip on the first bnd file
then use the bms script on the 2nd bnd it outputs.

offzip.exe -a c:\file.bnd c:\extract 0x0
## Post #13
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2013-11-26T03:59:32+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

> Reply from chrrox
>
> just run offzip on the first bnd file
then use the bms script on the 2nd bnd it outputs.

offzip.exe -a c:\file.bnd c:\extract 0x0

it seems i'm not the only nOOb here... becuz I tried wathever you said... A new error appeared saying the following...

"Error: Recheck your options, C:\c0000comp.bnd is not valid"

so after considering that ALL the files I've tried never works... I have a few questions to ask.

Which exact version of QuickBMS must I download and where to get it?
Can you check your code of BND.bms just in case it has any kind of errors of missing script texts? or at least attach the file to download it instead of forcing me to make one by myself?
Should I delete Offzip considering it's useless?

pls. answer kindly... I'm bitting all my nails already...  

PS: QuickBMS didn't extracted the file name exactly... instead of it, it appeared C0000.bnd with half size. sorry if I have to mention this, but I feel that your code is Wrong, and Offzip is useless to extract bnd.

maybe if Noesis could have support for Bnd files, I would never have to write down scripts without having knowledge of programming and just making a BMS file that only helped screwing things up.
## Post #14
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-26T04:30:41+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

ok create a new folder on your c drive called extract
download offzip and place it there [http://aluigi.altervista.org/mytoolz/offzip.zip](http://aluigi.altervista.org/mytoolz/offzip.zip)
Now download quickbms and also place it in there [http://aluigi.altervista.org/papers/quickbms.zip](http://aluigi.altervista.org/papers/quickbms.zip)
now copy BLJS10003\PS3_GAME\USRDIR\chr\c0000comp.bnd into that folder
create a new text document called bnd.bms and paste my script into it and save it into the extract folder.

open a command prompt
type
cd c:\extract
now type this exactly

```
offzip.exe -a c0000comp.bnd c:\extract 0x0
```

you will end up with 00000800.bnd
Now type this exactly

```
quickbms.exe bnd.bms 00000800.bnd c:\extract
```

you will get your model file.
## Post #15
- Username: Farlavor
- Rank: beginner
- Number of posts: 24
- Joined date: Tue Apr 10, 2012 7:02 pm
- Post datetime: 2013-11-26T17:16:17+00:00
- Post Title: Enchanted Arms (PS3) Noesis Script

> Reply from chrrox
>
> ok create a new folder on your c drive called extract
download offzip and place it there http://aluigi.altervista.org/mytoolz/offzip.zip
Now download quickbms and also place it in there http://aluigi.altervista.org/papers/quickbms.zip
now copy BLJS10003\PS3_GAME\USRDIR\chr\c0000comp.bnd into that folder
create a new text document called bnd.bms and paste my script into it and save it into the extract folder.

open a command prompt
type
cd c:\extract
now type this exactly
Code: Select alloffzip.exe -a c0000comp.bnd c:\extract 0x0
you will end up with 00000800.bnd
Now type this exactly
Code: Select allquickbms.exe bnd.bms 00000800.bnd c:\extract
you will get your model file.

OH YEAH... This time I got it without any kind of troubles... at least Offzip worked like a charm.
I hope it's not too late to learn scripting, becuz I never expected that even on the most basic of 3D modeling, rigging and extracting, requires too much efforts, specially on model extracting.

I miss the times you could extract models from BRRES files, or using 3D Ripper DX.

PRO TIP: Extract the files one by one... NEVER TRY to extract using all files by "*.bnd"... That was the cause of the error. (Just in case there still some nOObs, I highly Doubt that there's a nOOb like me).  

Edit: Everything works like a charm... I am currently extracting every character model possible... I hope to get all the golem models in a few hours. if those aren't on chr folder, then I will look on other game folders.
## Post #16
- Username: nowayme
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 02, 2011 7:28 am
- Post datetime: 2014-05-10T12:52:02+00:00
- Post Title: Re: Enchanted Arms (PS3) Noesis Script

Hey, I was wondering if you could make the script (or a different script based on that) that extracts ps3_bgm_wave_bank.mwb aswell (located at /sound).
It seems that the script you have already provided kinda works on them as is but it can't recognize on 1/3rd of files their start or end points or something. Some others though are perfectly extracted and are compltely unaffected by the error.
