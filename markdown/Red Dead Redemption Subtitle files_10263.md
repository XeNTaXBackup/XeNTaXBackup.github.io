## Post #1
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-03-24T13:01:13+00:00
- Post Title: Red Dead Redemption Subtitle files

Could someone have a look at the attached RDR subtitles file? I'd like to add a translation tool to rpftool for people to translate the game but haven't worked with subtitles at all so progress is slow!

Thanks.

[speechcontextsubtitles-en.xst](http://dl.dropbox.com/u/9950356/speechcontextsubtitles-en.xst)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-24T13:47:15+00:00
- Post Title: Red Dead Redemption Subtitle files

> Reply from twisted
>
> Could someone have a look at the attached RDR subtitles file? I'd like to add a translation tool to rpftool for people to translate the game but haven't worked with subtitles at all so progress is slow!

Thanks.

speechcontextsubtitles-en.xst

You don't have repack possibility so what is the point mate ?
## Post #3
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-03-24T13:53:11+00:00
- Post Title: Red Dead Redemption Subtitle files

> Reply from michalss
>
> twisted wrote:Could someone have a look at the attached RDR subtitles file? I'd like to add a translation tool to rpftool for people to translate the game but haven't worked with subtitles at all so progress is slow!

Thanks.

speechcontextsubtitles-en.xst

You don't have repack possibility so what is the point mate ?

[viewtopic.php?f=10&t=10246](http://forum.xentax.com/viewtopic.php?f=10&t=10246)
## Post #4
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-03-25T20:41:58+00:00
- Post Title: Red Dead Redemption Subtitle files

No one managed to decipher this at all? 

All I have is this so far, not much but its a start!

```
long magic; //0x7c095d00
long* unk1; //Always 0?
long Tableoffset;
long unk2; //Always 0?
long unk3; //Always 0?

//Table
long SubTableCount;
long TableOffset;

```


A lot of the values begin with 0x50, not sure if this signifies a pointer/offset?

Some more files: [https://dl.dropbox.com/u/9950356/translation.zip](https://dl.dropbox.com/u/9950356/translation.zip)
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-26T06:27:50+00:00
- Post Title: Red Dead Redemption Subtitle files

> Reply from twisted
>
> michalss wrote:twisted wrote:Could someone have a look at the attached RDR subtitles file? I'd like to add a translation tool to rpftool for people to translate the game but haven't worked with subtitles at all so progress is slow!

Thanks.

speechcontextsubtitles-en.xst

You don't have repack possibility so what is the point mate ?

viewtopic.php?f=10&t=10246

But as i remeber you said you not gonna support repack ? So did u change your mind mate ?
## Post #6
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-03-26T14:57:35+00:00
- Post Title: Red Dead Redemption Subtitle files

I haven't touched my xbox in over a year so decided it was probably time to release it as I had no use for it any more and there are people who would like to translate the game, anyway can we get back on topic now?
## Post #7
- Username: listener
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 22, 2011 7:30 am
- Post datetime: 2013-05-11T23:29:05+00:00
- Post Title: Red Dead Redemption Subtitle files

Just found this topic.

[https://dl.dropboxusercontent.com/u/123 ... st-full.bt](https://dl.dropboxusercontent.com/u/1237855/rdr-xst-full.bt)

Complete template for .xst/.cst 
Published almost two years ago.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-05-12T07:07:48+00:00
- Post Title: Red Dead Redemption Subtitle files

Template is only for header its seems, does anyone sorted the fonts ?
## Post #9
- Username: listener
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 22, 2011 7:30 am
- Post datetime: 2013-05-12T15:57:35+00:00
- Post Title: Red Dead Redemption Subtitle files

This template for all .xst contents 
.xst contains only text (like .gxt in GTA series)

[https://dl.dropboxusercontent.com/u/1237855/xst2.png](https://dl.dropboxusercontent.com/u/1237855/xst2.png)
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-05-13T06:45:09+00:00
- Post Title: Red Dead Redemption Subtitle files

I can write repacer but i dont have a files. Can you please send me all text files from X360 version ? No PS3 i wont touch PS3 version!
## Post #11
- Username: listener
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 22, 2011 7:30 am
- Post datetime: 2013-05-13T18:15:45+00:00
- Post Title: Red Dead Redemption Subtitle files

All 2500 files? (RDR + Undead Nightmare)
Or only ~550 -en.xst ?
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-05-13T19:48:53+00:00
- Post Title: Red Dead Redemption Subtitle files

only files where is text..
## Post #13
- Username: listener
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 22, 2011 7:30 am
- Post datetime: 2013-05-14T10:36:51+00:00
- Post Title: Red Dead Redemption Subtitle files

RDR + UN contains ~2500 files with text (of ~60 000 files total)
It have a separate text file for each cutscene and each mission. 

Almost all text files exist in 5 versions (-en, -de, -fr, -it, -sp), which gives ~550 files with an english text.
## Post #14
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-05-14T12:00:56+00:00
- Post Title: Red Dead Redemption Subtitle files

hmm uff ok can you please then send 10 of them at least ?
## Post #15
- Username: iTzZ Fenix
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 26, 2018 2:48 pm
- Post datetime: 2018-12-26T09:32:41+00:00
- Post Title: Red Dead Redemption Subtitle files

> Reply from listener
>
> Just found this topic.

https://dl.dropboxusercontent.com/u/123 ... st-full.bt

Complete template for .xst/.cst 
Published almost two years ago.

Could you reupload this??
also i cant find speechcontextsubtitles-en.xst file, where is?

Thank you
## Post #16
- Username: zx2395
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 17, 2019 4:09 pm
- Post datetime: 2019-10-17T08:19:56+00:00
- Post Title: Re: Red Dead Redemption Subtitle files

> Reply from listener ↑Tue May 14, 2013 6:36 pm at Tue May 14, 2013 6:36 pm
>
> 
RDR + UN contains ~2500 files with text (of ~60 000 files total)
It have a separate text file for each cutscene and each mission. 

Almost all text files exist in 5 versions (-en, -de, -fr, -it, -sp), which gives ~550 files with an english text.

Can you share this again?
File has been deleted
Thank you.
## Post #17
- Username: ihatboys
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 21, 2018 2:40 am
- Post datetime: 2020-04-29T02:12:09+00:00
- Post Title: Re: Red Dead Redemption Subtitle files

> Reply from zx2395 ↑Thu Oct 17, 2019 4:19 pm at Thu Oct 17, 2019 4:19 pm
>
> 
listener wrote: ↑Tue May 14, 2013 6:36 pm
RDR + UN contains ~2500 files with text (of ~60 000 files total)
It have a separate text file for each cutscene and each mission. 

Almost all text files exist in 5 versions (-en, -de, -fr, -it, -sp), which gives ~550 files with an english text.


Can you share this again?
File has been deleted
Thank you.

the same files, but for xbox360
in ps3 game, I tried to decompress the .edat file, without sucess
[Google Drive Link.rar](https://xentaxbackup.github.io/file/18056_Google Drive Link.rar)
## Post #18
- Username: zx2395
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 17, 2019 4:09 pm
- Post datetime: 2020-06-21T06:50:57+00:00
- Post Title: Re: Red Dead Redemption Subtitle files

> Reply from ihatboys ↑Wed Apr 29, 2020 10:12 am at Wed Apr 29, 2020 10:12 am
>
> 
zx2395 wrote: ↑Thu Oct 17, 2019 4:19 pm
listener wrote: ↑Tue May 14, 2013 6:36 pm
RDR + UN contains ~2500 files with text (of ~60 000 files total)
It have a separate text file for each cutscene and each mission. 

Almost all text files exist in 5 versions (-en, -de, -fr, -it, -sp), which gives ~550 files with an english text.


Can you share this again?
File has been deleted
Thank you.


the same files, but for xbox360
in ps3 game, I tried to decompress the .edat file, without sucess

Thank you very much.
You are my hero!
## Post #19
- Username: ihatboys
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 21, 2018 2:40 am
- Post datetime: 2021-07-08T20:33:52+00:00
- Post Title: Re: Red Dead Redemption Subtitle files

> Reply from zx2395 ↑Sun Jun 21, 2020 2:50 pm at Sun Jun 21, 2020 2:50 pm
>
> 
ihatboys wrote: ↑Wed Apr 29, 2020 10:12 am
zx2395 wrote: ↑Thu Oct 17, 2019 4:19 pm


Can you share this again?
File has been deleted
Thank you.


the same files, but for xbox360
in ps3 game, I tried to decompress the .edat file, without sucess


Thank you very much.
You are my hero!

Any progress?
I'm still looking for a solution as I can't edit the texts
## Post #20
- Username: zx2395
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 17, 2019 4:09 pm
- Post datetime: 2021-07-13T02:16:22+00:00
- Post Title: Re: Red Dead Redemption Subtitle files

> Reply from ihatboys ↑Fri Jul 09, 2021 4:33 am at Fri Jul 09, 2021 4:33 am
>
> 
zx2395 wrote: ↑Sun Jun 21, 2020 2:50 pm
ihatboys wrote: ↑Wed Apr 29, 2020 10:12 am


the same files, but for xbox360
in ps3 game, I tried to decompress the .edat file, without sucess


Thank you very much.
You are my hero!


Any progress?
I'm still looking for a solution as I can't edit the texts

In conclusion, I succeeded in translating this game.
First, extract the game's RPF files with rdr explorer.
Font files are in the fonts folder
And the "content\stringtable\global.strtbl" file is a text file.
[https://zenhax.com/viewtopic.php?t=7073](https://zenhax.com/viewtopic.php?t=7073)
modify the text file by downloading .strtbl export_import.rar [1.21 MiB].
Finally, compress the game files with RPFTOOL.!!!!
(Some text may not be translated)

If you don't have enough fonts, try buying a Japanese version.
## Post #21
- Username: ihatboys
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 21, 2018 2:40 am
- Post datetime: 2021-10-12T21:39:14+00:00
- Post Title: Re: Red Dead Redemption Subtitle files

> Reply from zx2395 ↑Tue Jul 13, 2021 10:16 am at Tue Jul 13, 2021 10:16 am
>
> 
ihatboys wrote: ↑Fri Jul 09, 2021 4:33 am
zx2395 wrote: ↑Sun Jun 21, 2020 2:50 pm


Thank you very much.
You are my hero!


Any progress?
I'm still looking for a solution as I can't edit the texts


(Some text may not be translated)

If anyone wants to analyze the files...
The .xst files do not work properly with .bms script
and the .strtbl file does not contain all the texts.

[ .strtbl and .xst  language files](https://drive.google.com/file/d/1ETtAWAtaXIqLzxv2s4cBFWT_ztcHNSAy/view?usp=sharing)
## Post #22
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2023-08-22T15:38:37+00:00
- Post Title: Re: Red Dead Redemption Subtitle files

Hi there, anybody have srtbl export import text tool?:) I try localization switch version tnx....
[https://www.mediafire.com/file/4xk7xmg0 ... trtbl/file](https://www.mediafire.com/file/4xk7xmg0sqaxup8/global.strtbl/file)
## Post #23
- Username: brtraducoes
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Sep 30, 2015 12:54 am
- Post datetime: 2023-08-23T01:10:46+00:00
- Post Title: Re: Red Dead Redemption Subtitle files

Hi, I edited and extracted the texts in txt.
I don't know if it works.
[https://cdn.discordapp.com/attachments/ ... bal.strtbl](https://cdn.discordapp.com/attachments/1013461591540367432/1143713586552782870/global.strtbl)

example text
brtraducoes central de traducoes When you complete missions with a high percentage of kills via headshot, you become more famous.
You left El Presidio.
Undefined Name
Next Scrap: Win a game of Blackjack at Rathskeller Fork
## Post #24
- Username: dvoika
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Nov 08, 2014 4:19 am
- Post datetime: 2023-08-23T21:29:14+00:00
- Post Title: Re: Red Dead Redemption Subtitle files

you have tool? or hex? tnx:)
i dont know where find tools:(
## Post #25
- Username: brtraducoes
- Rank: advanced
- Number of posts: 41
- Joined date: Wed Sep 30, 2015 12:54 am
- Post datetime: 2023-08-24T00:28:58+00:00
- Post Title: Re: Red Dead Redemption Subtitle files

and tool, but did it work?
I show brtraducoes central de traducoes.
