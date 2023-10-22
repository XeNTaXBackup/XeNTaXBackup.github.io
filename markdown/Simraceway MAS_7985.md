## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-04T07:56:27+00:00
- Post Title: Simraceway MAS

I have updated my mas.bms script to support also the mas archives of the [Simraceway](http://www.simraceway.com/) game (a collection of mods):
[http://aluigi.org/papers/bms/mas.bms](http://aluigi.org/papers/bms/mas.bms)

remember that the script works with ANY mas archive of the games based on the ISI gmotor engine like ACTC, rFactor, ARCA, BMW M3, Sports Cart GT, NASCAR SimRacing/Thunder, F1 Challenge and so on.

and yes, it works correctly and doesn't have the bugs of the ISI public tools.
## Post #2
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2012-07-23T09:43:57+00:00
- Post Title: Simraceway MAS

Thank you for this script aluigi!

I think the key may have changed in v28.71 build 322 - latest build as of today.
First I used simraceway.bms to decrypt some MAS files (they had SRW00002 header). Then I tried to extract the resulting files with mas.bms, but I get errors:

```
------------------------------
- SCRIPT's MESSAGE:
  set MAS_TYPE 2


Error: incomplete input file number 0, can't read 1298055708 bytes.
       anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted
```
or

```
Error: the requested amount of bytes to allocate is negative (-1720700288)
```
Using quickbms 0.5.13

Could you please look into this? I can send you any files you may need.

Thanks!
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-23T13:00:04+00:00
- Post Title: Simraceway MAS

give me the name of one of these MAS, I have tried with evox.mas and everything worked correctly.
I'm using the latest simraceway.bms released some days ago: 0.2
## Post #4
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2012-07-23T16:03:41+00:00
- Post Title: Simraceway MAS

I re-downloaded everything, game included, on my home computer and it seems to work now.
No idea what went wrong before 

Sorry to bother you, thanks again!
## Post #5
- Username: RCFortyFive
- Rank: VIP member
- Number of posts: 6
- Joined date: Wed Mar 01, 2006 4:11 pm
- Post datetime: 2013-08-02T08:45:27+00:00
- Post Title: Simraceway MAS

This script does not seem to work on the newest version of simraceway files.

Any suggestions?
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-08-03T06:45:47+00:00
- Post Title: Simraceway MAS

Simraceway files must be handled in the following way:
[http://aluigi.altervista.org/misc/simra ... wfiles.txt](http://aluigi.altervista.org/misc/simraceway_newfiles.txt)
## Post #7
- Username: RCFortyFive
- Rank: VIP member
- Number of posts: 6
- Joined date: Wed Mar 01, 2006 4:11 pm
- Post datetime: 2013-08-03T07:19:48+00:00
- Post Title: Simraceway MAS

OK, so the real time capture of the machine unique key is no longer a required step?
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-08-03T16:38:41+00:00
- Post Title: Simraceway MAS

exactly, it's more convenient and easy to download the original files and decrypting them (without unique key).
## Post #9
- Username: RCFortyFive
- Rank: VIP member
- Number of posts: 6
- Joined date: Wed Mar 01, 2006 4:11 pm
- Post datetime: 2013-08-04T08:45:47+00:00
- Post Title: Simraceway MAS

> Reply from aluigi
>
> exactly, it's more convenient and easy to download the original files and decrypting them (without unique key).

Excellent. I managed to use this method to decrypt the files already installed by the game.
## Post #10
- Username: splintert92
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 15, 2011 6:56 am
- Post datetime: 2013-08-10T23:21:25+00:00
- Post Title: Simraceway MAS

Is anyone else having problems unzipping the cars? I have tried many different things, winrar, winzip, downloading from multiple browsers but I still get error messages when I try to extract them.
## Post #11
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2013-08-10T23:33:32+00:00
- Post Title: Simraceway MAS

First you have to decrypt them with aluigi's script: [http://aluigi.altervista.org/papers/bms/simraceway.bms](http://aluigi.altervista.org/papers/bms/simraceway.bms)
## Post #12
- Username: splintert92
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 15, 2011 6:56 am
- Post datetime: 2013-08-10T23:55:59+00:00
- Post Title: Simraceway MAS

You have to decrypt the zip file downloaded from the web? I.E. - [http://cdn.simraceway.com/mods/1933_SRW ... Hotrod.zip](http://cdn.simraceway.com/mods/1933_SRW_Custom_Hotrod.zip) I tried and it still will not unzip.

EDIT- Got it, thanks! You cannot save the decrypted zip over the original.
## Post #13
- Username: RCFortyFive
- Rank: VIP member
- Number of posts: 6
- Joined date: Wed Mar 01, 2006 4:11 pm
- Post datetime: 2013-08-17T00:03:57+00:00
- Post Title: Simraceway MAS

Anyone have any luck extracting the SRW.MAS and SRW_ANT.MAS files? Or any of the MAS files in the vehicle root?
## Post #14
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2014-06-01T15:11:49+00:00
- Post Title: Simraceway MAS

> Reply from RCFortyFive
>
> Anyone have any luck extracting the SRW.MAS and SRW_ANT.MAS files? Or any of the MAS files in the vehicle root?

Those files just have common textures like cubemaps, tires textures etc.. So you can use other one for example from shift 2 is what i do on all the conversions.
## Post #15
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-05T10:46:30+00:00
- Post Title: Simraceway MAS

Hi 

Here is  importer for simraceway mods.
It requiers Blender version 249 and Python 26.

Steps.
1.download mods from [viewtopic.php?p=87061#p87061](http://forum.xentax.com/viewtopic.php?p=87061#p87061)
2.decrypt zip files [viewtopic.php?p=87226#p87226](http://forum.xentax.com/viewtopic.php?p=87226#p87226)
3.unpack mas archive [viewtopic.php?p=64614#p64614](http://forum.xentax.com/viewtopic.php?p=64614#p64614)
4.unpack importer
5.run Blender249.blend
6.press in Blender Text Window alp+p and select gmt files

[http://www.imagebam.com/image/37c007369421367](http://www.imagebam.com/image/37c007369421367)
[Blender249[Simraceway][gmt][2014-12-05].zip](https://xentaxbackup.github.io/file/8201_Blender249[Simraceway][gmt][2014-12-05].zip)
## Post #16
- Username: Ha3aP
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Sep 02, 2013 1:40 am
- Post datetime: 2015-10-17T14:42:58+00:00
- Post Title: Re: Simraceway MAS

> Reply from Szkaradek123
>
> 2.decrypt zip files viewtopic.php?p=87226#p87226 Don't work ((( Hepl pls!
## Post #17
- Username: God Of Gaming
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 13, 2015 4:47 am
- Post datetime: 2015-12-12T20:51:51+00:00
- Post Title: Re: Simraceway MAS

The script doesn't seem to work for the latest version anymore. Even after running the simraceway_getkey script and copying the key into the simraceway.bms script, it still doesn't work. And I need it now more than ever, since the game appears to be on the brink of death...
## Post #18
- Username: bugmenever
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2016-02-13T05:48:07+00:00
- Post Title: Re: Simraceway MAS

> Reply from aluigi
>
> Simraceway files must be handled in the following way:
http://aluigi.altervista.org/misc/simra ... wfiles.txt

all links - InvalidCust ? Why
Can u Update links ?
Thx
## Post #19
- Username: xrahhfgjb
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 28, 2016 10:32 pm
- Post datetime: 2016-06-28T14:46:49+00:00
- Post Title: Re: Simraceway MAS

DELETED
## Post #20
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-01-08T18:38:00+00:00
- Post Title: Re: Simraceway MAS

> Reply from Szkaradek123 ↑Fri Dec 05, 2014 6:46 pm at Fri Dec 05, 2014 6:46 pm
>
> 
Hi 

Here is  importer for simraceway mods.
It requiers Blender version 249 and Python 26.

Steps.
1.download mods from http://forum.xentax.com/viewtopic.php?p=87061#p87061
2.decrypt zip files http://forum.xentax.com/viewtopic.php?p=87226#p87226
3.unpack mas archive http://forum.xentax.com/viewtopic.php?p=64614#p64614
4.unpack importer
5.run Blender249.blend
6.press in Blender Text Window alp+p and select gmt files

http://www.imagebam.com/image/37c007369421367

I know it's old, but this is a neat way of getting models of Simraceway, but things age over time and I had to install an older version of Blender which was a bit uncomfortable for me. Is there a way to get the models of SRW into the latest version of Blender or 2.79?
## Post #21
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-01-08T18:38:16+00:00
- Post Title: Re: Simraceway MAS

> Reply from Szkaradek123 ↑Fri Dec 05, 2014 6:46 pm at Fri Dec 05, 2014 6:46 pm
>
> 
Hi 

Here is  importer for simraceway mods.
It requiers Blender version 249 and Python 26.

Steps.
1.download mods from http://forum.xentax.com/viewtopic.php?p=87061#p87061
2.decrypt zip files http://forum.xentax.com/viewtopic.php?p=87226#p87226
3.unpack mas archive http://forum.xentax.com/viewtopic.php?p=64614#p64614
4.unpack importer
5.run Blender249.blend
6.press in Blender Text Window alp+p and select gmt files

http://www.imagebam.com/image/37c007369421367

I know it's old, but this is a neat way of getting models of Simraceway, but things age over time and I had to install an older version of Blender which was a bit uncomfortable for me. Is there a way to get the models of SRW into the latest version of Blender or 2.79? (ignore this I just bought 3DSimED, worth it)
