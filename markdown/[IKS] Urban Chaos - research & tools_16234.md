## Post #1
- Username: Acewell
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-05-02T09:56:00+00:00
- Post Title: [IKS] Urban Chaos - research & tools

Hello. It is a great day to share my knowledge about modding and translating Urban Chaos. Thanks to me and Fire_head now this is now possible. He created a tool for extracting graphics from TXC files and I created a Python script for replacing texts in UCM files.


* Graphics edit\replace *

As I said, modding is now possible. Thanks to Fire_head's tools ([http://www.neoseeker.com/forums/710/t17 ... #m39705162](http://www.neoseeker.com/forums/710/t1793865-mucky-foot-times-speedrunning/5.htm#m39705162)) I managed to unpack all graphics from txc files to "server" folder which is replacement for TXC files and this game may use TXC files or graphics in this folder. It depends how we set option "enable_clumps" in config.ini file.

If you have "server" folder with graphics which have correct filenames and config.ini file with option "enable_clumps" set to 0, you re able to edit\replace graphics and fonts in game without editing TXC files. Fixed server folder you can download here --> [http://ikskoks.pl/wp-content/uploads/20 ... _patch.zip](http://ikskoks.pl/wp-content/uploads/2017/05/urban_chaos_modding_patch.zip) or you can create this folder by yourself using Fire_head tools (but in that case you'll have to fix some of the graphics, because one tool is exporting graphics with correct filenames, but with messed up alpha channel and other tool is exporting graphics with correct alpha channel, but wrong filenames :p). Just copy server folder to the main folder of the game "Urban Chaos\server\".

* BIK movies replace *

Everything is described here [viewtopic.php?f=36&t=16180](http://forum.xentax.com/viewtopic.php?f=36&t=16180)
You just need to create BIK using old radtools.
I have even written tutorial in polish about that [http://ikskoks.pl/podmiana-starych-filmow-bik-w-grach/](http://ikskoks.pl/podmiana-starych-filmow-bik-w-grach/)

* Save Editor *
I have found a nice tool for editing WAG save files --> [http://ikskoks.pl/wp-content/uploads/20 ... csedit.zip](http://ikskoks.pl/wp-content/uploads/2017/05/ucsedit.zip)

* Cars handling *
[http://www.neoseeker.com/forums/710/t17 ... #m39481906](http://www.neoseeker.com/forums/710/t1793865-mucky-foot-times-speedrunning/5.htm#m39481906)

* Model viewer *
Here is a online model viewer --> [http://code.vonc.fr/?a=60](http://code.vonc.fr/?a=60)
And PRM file format --> [http://code.vonc.fr/details/60/code_1.txt](http://code.vonc.fr/details/60/code_1.txt)

* Translating info *

You can check out polish translation here [http://ikskoks.pl/urban-chaos-spolszczenie/](http://ikskoks.pl/urban-chaos-spolszczenie/)

Text to translate is in "text" folder, "levels" folder and urban.sty file. Fonts are in Urban Chaos\server\textures\extras\ folder.
You don't need to translate text in all UCM files. Some of them are alfa releases and game don't use them at all.

List of files that you have to translate:

```
Assault1.ucm AWOL1.ucm Baalrog3.ucm Bankbomb1.ucm bball2.ucm botanicc.ucm carbomb1.ucm e3.ucm estate2.ucm factory1.ucm fight1.ucm fight2.ucm Finale1.ucm FTutor1.ucm Gangorder1.ucm Gangorder2.ucm Gordout1.ucm MIB.ucm mission2.ucm park2.ucm police1.ucm police2.ucm police3.ucm police4.ucm semtex.ucm skymiss2.ucm snow2.ucm Stealtst1.ucm testdrive1a.ucm testdrive2.ucm testdrive3.ucm westcrime1.ucm wstores1.ucm
```

* Translating Tool *

To unpack and repack UCM files you need to use my script. Just declare valid paths at the end of this script, uncomment functions you want to use and comment other functions.
Warning! For repacking always use original UCM files, so buckup them first.

You need Python 2.7 to run this script.


 Urban_Chaos_Tool_7.zip
(1.99 KiB) Downloaded 50 times



There is also implemented char replacer for UCM files and TXT files, sou you can edit this script for your needs.



Enjoy.
## Post #2
- Username: Fire Head
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 03, 2017 11:47 pm
- Post datetime: 2017-05-03T22:27:09+00:00
- Post Title: [IKS] Urban Chaos - research & tools

untxc and tex2tga sources: [https://github.com/Fire-Head/UCTxcTools](https://github.com/Fire-Head/UCTxcTools)
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-05-20T07:50:53+00:00
- Post Title: [IKS] Urban Chaos - research & tools

> Mike Diskett just released a bunch of UC code for "historical purposes".
>
> github(dot)com/dizzy2003/MuckyFoot-UrbanChaos
>
> 
>
> "I am making this code public mainly out of historical interest, I doubt theres anything of any actual use to anyone, allthough people do occasionally still ask me about data formats so they can dig them out themsleves now..."

Whoah! Urban Chaos sources!  
[https://github.com/dizzy2003/MuckyFoot-UrbanChaos](https://github.com/dizzy2003/MuckyFoot-UrbanChaos)
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-10-18T21:33:25+00:00
- Post Title: [IKS] Urban Chaos - research & tools

Hello. I have added some Urban Chaos file formats to Xentax wiki
[https://wiki.xentax.com/index.php/Urban_Chaos](https://wiki.xentax.com/index.php/Urban_Chaos)

I have also updated my UC python tools on github
[https://github.com/bartlomiejduda/Tools ... an%20Chaos](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/Urban%20Chaos)
