## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-14T13:02:35+00:00
- Post Title: Dante's Inferno .tg4d textures

Hello everyone! Need help with Dante's Inferno textures .tg4d. Same format as Dead Space series, though DS tools didn't help. I tried to add dxt header and it was pretty close to success, but I don't know what to do to make them look right. Can someone please take a look at them? Thanks in advance.
[tg4d_sample.7z](https://xentaxbackup.github.io/file/6330_tg4d_sample.7z)
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-17T16:47:37+00:00
- Post Title: Dante's Inferno .tg4d textures

Bump. I wrote an import script for Dante's Inferno models, too bad it's useless until textures not working 
[Без имени-1.jpg](https://xentaxbackup.github.io/file/6335_Без имени-1.jpg)
## Post #3
- Username: modes
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 05, 2011 11:18 am
- Post datetime: 2013-04-18T13:44:49+00:00
- Post Title: Dante's Inferno .tg4d textures

TextureFinder.v21 can open texture from ps3 format, format is dds.

Please release this script! 
thank you

sorry for my bad english
## Post #4
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-08-08T09:17:26+00:00
- Post Title: Dante's Inferno .tg4d textures

Sorry for the late. You can obtain textures from ps3 version, add the DXT (DXT1 or DXT5 if is normal map) dds header.

(some textures still compressed.)




can you publish your importer script? please.
## Post #5
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2017-11-25T20:54:21+00:00
- Post Title: Dante's Inferno .tg4d textures

Привет у тебя не осталось скрипта для Dantes Inferno
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-26T01:22:58+00:00
- Post Title: Dante's Inferno .tg4d textures

the tg4d samples are headerless, if these are anything like deadspace there might be a tg4h header file to accompany 
each tg4d. if anyone can take a look and see and upload some paired samples i will try make a Noesis python script.  
the image data is big-endian but not tiled, so i guess your samples are from PS3?
## Post #7
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-26T19:29:38+00:00
- Post Title: Dante's Inferno .tg4d textures

> Reply from Crazy31139
>
> Привет у тебя не осталось скрипта для Dantes Inferno

I still have that script, actually I found it again not while ago, so I will publish it soon with Noesis texture plugin.
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-16T05:44:43+00:00
- Post Title: Dante's Inferno .tg4d textures

> Reply from zaramot
>
>  I will publish it soon with Noesis texture plugin.
time is up   
here is Noesis python texture script to open the tg4h/tg4d sample pairs for PS3 version of this game
*script modified on Nov 28 2018*


 tex_DantesInferno_PS3_tg4h.zip
(1.25 KiB) Downloaded 60 times



the script is set to open tg4h header files, but each one must have a corresponding 
tg4d data file in the same folder so the script can find everything to display the texture.

this script will likely conflict with other tg4h/tg4d scripts so you have to move them out of python folder temporarily.
## Post #9
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-11-27T19:37:11+00:00
- Post Title: Dante's Inferno .tg4d textures

> Reply from Acewell
>
> zaramot wrote: I will publish it soon with Noesis texture plugin.
time is up   
here is Noesis python texture script to open the tg4h/tg4d sample pairs for PS3 version of this game
tex_DantesInferno_PS3_tg4h.zip

the script is set to open tg4h header files, but each one must have a corresponding 
tg4d data file in the same folder so the script can find everything to display the texture.

this script will likely conflict with other tg4h/tg4d scripts so you have to move them out of python folder temporarily.I can't get it work, always get some 'load noepyLoadRGBA' error
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-11-28T00:41:05+00:00
- Post Title: Dante's Inferno .tg4d textures

> Reply from Tosyk
>
> I can't get it work, always get some 'load noepyLoadRGBA' error
upload your problem samples and i will check, otherwise nothing more i can do.
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-11-28T16:43:54+00:00
- Post Title: Dante's Inferno .tg4d textures

> Reply from Acewell
>
> Tosyk wrote:I can't get it work, always get some 'load noepyLoadRGBA' error
upload your problem samples and i will check, otherwise nothing more i can do.sure
[https://drive.google.com/open?id=1pJ0fm ... qHXxeC7u6a](https://drive.google.com/open?id=1pJ0fmrqA2S3RV3ThmYefuhqHXxeC7u6a)
[https://drive.google.com/open?id=1r-QNQ ... E8zjmoScdq](https://drive.google.com/open?id=1r-QNQpanbwI8iQEgKxJLyE8zjmoScdq)_
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-11-28T22:07:25+00:00
- Post Title: Dante's Inferno .tg4d textures

okay i made a change to the script from my previous post to work with your samples
but i don't like it because when i made that script i downloaded the PS3 version of the 
game and extracted the samples myself and they worked fine with the original script,
so i'm not sure what is going on here.
## Post #13
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-11-30T09:06:35+00:00
- Post Title: Dante's Inferno .tg4d textures

Acewell, damn, that's weird!
can you send me some of your files?
also is it possible to make you script work with both types of sample?
## Post #14
- Username: Naomi9
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 30, 2018 6:46 pm
- Post datetime: 2018-11-30T10:51:59+00:00
- Post Title: Dante's Inferno .tg4d textures

Who can give scripts for Dead Space?
## Post #15
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-02T06:30:31+00:00
- Post Title: Dante's Inferno .tg4d textures

> Reply from Tosyk
>
> can you send me some of your files?
also is it possible to make you script work with both types of sample?
i haven't had those samples for many months now, they are long deleted.  
what other type of sample are you referring to? x360? 
the original script was downloaded 24 times but only you responded about it,
so i just adjust it to the only feedback i get. if you find something it doesn't work
with then i will try modify it further.
## Post #16
- Username: TyapLyap
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 01, 2019 4:37 am
- Post datetime: 2021-03-29T20:58:19+00:00
- Post Title: Re: Dante's Inferno .tg4d textures

Hello,soo someone have script for .tg4d?
## Post #17
- Username: kskui008
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 04, 2018 11:56 am
- Post datetime: 2022-08-31T15:04:23+00:00
- Post Title: Re: Dante's Inferno .tg4d textures

Thanks for everything you've done here, I'm wondering how I can quickly find the character model I want to extract, I just got the textures here. Can you write a PY script for a geo file that can preview the model.
