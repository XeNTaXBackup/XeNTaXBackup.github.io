## Post #1
- Username: alon
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-01-23T02:29:31+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

Here is a plugin for noesis that supports xpr2 files.
if you find a xpr file that does not work just upload it somewhere and let me know ill add support for it.
[fmt_XBOX_360_XPR.rar](https://xentaxbackup.github.io/file/5009_fmt_XBOX_360_XPR.rar)
## Post #2
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-01-23T09:44:26+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

The noesis plugin is perfect.
Thank you very much!
## Post #3
- Username: majinmartin93
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Feb 05, 2012 10:07 pm
- Post datetime: 2012-02-05T14:20:31+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-05T15:50:57+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

what game is it from
## Post #5
- Username: majinmartin93
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Feb 05, 2012 10:07 pm
- Post datetime: 2012-02-05T18:56:47+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

> Reply from chrrox
>
> what game is it from
fifa 12
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-02-05T19:20:42+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

pc ps3 360?
## Post #7
- Username: majinmartin93
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Feb 05, 2012 10:07 pm
- Post datetime: 2012-02-05T21:28:49+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

> Reply from chrrox
>
> pc ps3 360?
xbox 360, or i woudn't post it here
## Post #8
- Username: majinmartin93
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Feb 05, 2012 10:07 pm
- Post datetime: 2012-02-07T17:58:29+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

Opened a discussion with more info here:
[viewtopic.php?f=10&t=8213](http://forum.xentax.com/viewtopic.php?f=10&t=8213)
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2012-03-17T11:00:59+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

does not work on this : [http://dl.dropbox.com/u/38234344/Reside ... _Fotns.rar](http://dl.dropbox.com/u/38234344/Resident%20Evil%20Operation%20Raccoon%20City%20_Text_Fotns.rar)
## Post #10
- Username: kostasishere
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Mar 20, 2012 10:00 am
- Post datetime: 2012-03-20T03:43:48+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

Thank's a lot but it doesn't work on RE:ORC for 360 like the above msg, 
here is the message from Noesis

and here is another file (hunkgear_s.xpr) if it's possible for a fix
[http://www.mediafire.com/?gnzfdabubc8b2j3](http://www.mediafire.com/?gnzfdabubc8b2j3)

Edit: it works with this script from here
[viewtopic.php?f=10&t=8574&start=15](http://forum.xentax.com/viewtopic.php?f=10&t=8574&start=15)

> from inc_noesis import *
>
> 
>
> def registerNoesisTypes():
>
>    handle = noesis.register("Hackity Hack Hack", ".xpr")
>
>    noesis.setHandlerTypeCheck(handle, noeCheckGeneric)
>
>    noesis.setHandlerLoadRGBA(handle, hackLoadRGBA)
>
>    return 1
>
> 
>
> def hackLoadRGBA(data, texList):
>
>    w = 256
>
>    h = 256
>
>    fmt = noesis.NOESISTEX_DXT5
>
>    data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), w, h, 8 if fmt == noesis.NOESISTEX_DXT1 else 16)
>
>    texList.append(NoeTexture("hacktex", w, h, data, fmt))
>
>    return 1

but few files are buggy like this one
[http://www.mediafire.com/?aou3hlj9qboy2h3](http://www.mediafire.com/?aou3hlj9qboy2h3)
## Post #11
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-03-25T10:47:25+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

How can i fix this?
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-26T02:19:55+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

Like I said in the ORC thread the old ssg script could produce corrupt data. Go get the new script and reextract with that.
## Post #13
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-03-26T14:22:16+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

> Reply from MrAdults
>
> Like I said in the ORC thread the old ssg script could produce corrupt data. Go get the new script and reextract with that.

But it doesn't work with new script also
## Post #14
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-27T02:03:01+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

Different issue, your size and/or format is wrong.
## Post #15
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-03-27T12:06:03+00:00
- Post Title: Xbox 360 XPR2 (noesis plugin)

I used
def hackLoadRGBA(data, texList):
   w = 256/512/1024/2048
   h = 256/512/1024/2048
   fmt = noesis.NOESISTEX_DXT5
   data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), w, h, 8 if fmt == noesis.NOESISTEX_DXT1 else 16)
   texList.append(NoeTexture("hacktex", w, h, data, fmt))
   return 1

And always diffuse are wrong or not reading at Noesis :/
## Post #16
- Username: greywaste
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 30, 2010 5:10 am
- Post datetime: 2012-03-27T12:47:48+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

> Reply from Kamillho
>
> 
   fmt = noesis.NOESISTEX_DXT5
[Here's some info about .dds compression types](http://www.poopinmymouth.com/tutorial/dds_types.html)
Play around with the value I left alone in your quote.
## Post #17
- Username: Kamillho
- Rank: veteran
- Number of posts: 84
- Joined date: Sun Jan 23, 2011 1:19 am
- Post datetime: 2012-03-27T13:56:57+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

> Reply from greywaste
>
> Kamillho wrote:
   fmt = noesis.NOESISTEX_DXT5

Here's some info about .dds compression types
Play around with the value I left alone in your quote.

Thanks!
It works on some textures!
## Post #18
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-22T18:58:51+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

Сhrrox, could you please add support for NeverDead .xpr transparency textures? .xpr normal maps works great, don't know why these ones are not. Here are some samples.
[xpr.7z](https://xentaxbackup.github.io/file/6347_xpr.7z)
## Post #19
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-09-28T04:51:40+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

chrrox - I would be very grateful if you could add support for the xpr2 files from EA MMA for xbox. 

Here are some samples: [http://www.mediafire.com/?a8nj6ms8c64fd4x](http://www.mediafire.com/?a8nj6ms8c64fd4x)
## Post #20
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-09-28T13:59:05+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

> Reply from dragbody
>
> chrrox - I would be very grateful if you could add support for the xpr2 files from EA MMA for xbox. 

Here are some samples: http://www.mediafire.com/?a8nj6ms8c64fd4x

Rename that crap as xpr and use tecmo360texturesExtractorV15 by bony, It supports xpr. Then the files exported just add a .dds extension and you're done. 

[viewtopic.php?f=16&t=6392&start=600](http://forum.xentax.com/viewtopic.php?f=16&t=6392&start=600)

Edit: the normal bump is an ati2 dds texture, convert it to whatever you want with noesis if you have some problems.
[EmelianenkoFedor_head_COL.7z](https://xentaxbackup.github.io/file/6652_EmelianenkoFedor_head_COL.7z)
## Post #21
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-09-28T16:37:06+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

Darko - Thank you and AceWell so much for the help! It's working perfectly. Really, I can't thank you enough. I'm a modder, but I also train jiu-jitsu so most of these MMA guys are people I've met and look up to! For example, Fabricio Werdum and Roger Gracie are heroes of my sport   

You've made my weekend! I hope yours is great too.
## Post #22
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-18T11:31:46+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

Strange errors

I also cannot use the tecmo extractor cos i don't have tkinter
Here is its own error

```
File ....tecmo360texturesExtractorV14.py", line
16, in <module>
    from tkinter import *
importError: No module named tkinter

```

[noesis_error.png](https://xentaxbackup.github.io/file/8299_noesis_error.png)
## Post #23
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-18T12:12:52+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

This doesn't happen with every file
The offending files are way to big to upload here
I don't know if I can use drop box on this site but  [here it is](https://www.dropbox.com/s/23ig8l3bomzvse0/CHR_HORIBE_1P.XPR?dl=0).
## Post #24
- Username: flowersongs
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2016 2:40 am
- Post datetime: 2016-02-11T09:24:32+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

I'm trying the xpr script on NBA Jams On Fire textures (xbox360), but its not working. It makes a file, but its just all black with a few random artifacts. I extracted the graphic files from an AST file with quickbms and NBA Jam AST script that aluigi wrote: [http://aluigi.altervista.org/bms/nbajamfire.bms](http://aluigi.altervista.org/bms/nbajamfire.bms)

It wont let me attach anything bigger than 200kb, so I uploaded an example file to my work server here:
[http://premieronlinevideo.com/stuff/nbajam-graphix.zip](http://premieronlinevideo.com/stuff/nbajam-graphix.zip)
. Looking at the header in Hex, it shows XPR2. I'm real close here and very interested in finally adding some new skins to NBA Jam. Any help is greatly appreciated.
## Post #25
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2016-10-01T11:02:53+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

hi chroxx, 
 Can you check this type of xpr? its from EA game Fight Night Champion, i used your script to open the file in Noesis, it can open but the result is just single color.
 Please help me with this.
 Thanks a lot
 File link: [https://www.dropbox.com/s/i5vyy9mk00u16q0/test.xpr?dl=0](https://www.dropbox.com/s/i5vyy9mk00u16q0/test.xpr?dl=0)
## Post #26
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-01T16:02:29+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

i think chrrox abandoned support for this script years ago    

i made an adjustment to it on line 49 that uses the header size so it 
will go to the start of image data, before it was just using a fixed value
and started reading at the wrong offset when there is different header length.


 fmt_XBOX_360_XPR.zip
(1.3 KiB) Downloaded 144 times



this script will open the sample from Yuredacy2311 and flowersongs  
JohnHudeski's sample link was dead i got no clear image yet from zaramot's samples
## Post #27
- Username: Yuredacy2311
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Aug 31, 2011 8:36 am
- Post datetime: 2016-10-02T05:29:12+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

Thanks a lot bro ^^
 I got it worked now. Cheer!!
## Post #28
- Username: jeter17
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 26, 2016 4:34 am
- Post datetime: 2016-10-25T22:35:04+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

> Reply from AceWell
>
> i think chrrox abandoned support for this script years ago    

i made an adjustment to it on line 49 that uses the header size so it 
will go to the start of image data, before it was just using a fixed value
and started reading at the wrong offset when there is different header length.
The attachment fmt_XBOX_360_XPR.zip is no longer available

this script will open the sample from Yuredacy2311 and flowersongs  
JohnHudeski's sample link was dead i got no clear image yet from zaramot's samples
it's also for nbajam but can't be opened..hep me plz..thx
[43675468.zip](https://xentaxbackup.github.io/file/11840_43675468.zip)
## Post #29
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-26T09:38:55+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

> Reply from jeter17
>
> it's also for nbajam but can't be opened..hep me plz..thx
NBA Jam on what platform? 
that doesn't look like a xpr2 format, looks more like the PS3 gtf format i just made a script for here   
[viewtopic.php?p=123791#p123791](http://forum.xentax.com/viewtopic.php?p=123791#p123791)

add a gtf extension to your texture files and use that "Shift 2" gtf script.
## Post #30
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2016-12-25T21:24:05+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

The script has a bug when using large files from ImportTunerChallenge



This is an example file that produces the error: [https://www.dropbox.com/s/rtheafi4y8399 ... 5.xpr?dl=0](https://www.dropbox.com/s/rtheafi4y8399ki/000007e5.xpr?dl=0)

Please help to resolve this.
## Post #31
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-25T22:31:11+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

the script works with your sample it just chokes on the comma and quotation mark at 0x361
and 0x362 when reading the string names, you can just open the sample in a hex editor and
replace those characters with an actual letter to allow the script to keep running.
## Post #32
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2016-12-26T11:01:13+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

Many thanks   
But it is possible to fix Noesis Script some way to all the textures of the game, there are too many files that have an error ...
It would be too difficult to correct each one manually.
## Post #33
- Username: SteamyJ
- Rank: beginner
- Number of posts: 38
- Joined date: Thu May 16, 2019 4:44 am
- Post datetime: 2022-06-11T14:24:10+00:00
- Post Title: Re: Xbox 360 XPR2 (noesis plugin)

Does this script work with Bomberman Act Zero?
