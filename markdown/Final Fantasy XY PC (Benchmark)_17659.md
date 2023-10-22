## Post #1
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2018-02-04T15:10:30+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

Noesis supports models from this game (at least the benchmark):



The textures are not working.

[http://www.mediafire.com/file/luwawwi6i ... eimages.7z](http://www.mediafire.com/file/luwawwi6ixx8p92/sourceimages.7z)
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-02-04T19:49:26+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

updated: currently should support dxt1, dxt3, dxt5, bc4, bc5, bc6, bc7. i don't have samples, so... dxt3 and bc6 formats are just good guesses.
[tex_FFXV_PCbench_btex_v3.rar](https://xentaxbackup.github.io/file/14289_tex_FFXV_PCbench_btex_v3.rar)
## Post #3
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2018-02-05T14:42:08+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

Thanks @episoder ! 
It worked so far with every texture I tried.

I was wondering if there's any chance to make the materials also compatible with the pc (benchmark) version? Right now you have to export the textures out of noesis and load them in an external 3d app to see them applied to the meshes.
Example of the error noesis throws in the debug log (very basic):

```
Reading 'xxx\... \\character\nh\nh00\model_000\\nh00_000_skin_00_mat.gmtl'...Failed.
```


Some material examples attached.


 xvbch_mats.rar
(205.3 KiB) Downloaded 162 times
## Post #4
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-02-05T17:52:47+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

ehh. well... ofc you can't read those materials with the texture loader. and you gotta remove the "noesis.logPopup()" line. seems i forgot that. 

and... no... i won't puzzle materials. are they even usable or extractable by noesis? i dunno. i don't care. those files are shader blah. no reproducing that. they got the texture names, but... screw it. the guy who did the model loader should add this parser. i don't even have any of this model data or scripts. i don't need either. seems it works just like that. the models got names? they have underscores and simple file name structure. to port or work with them you need a modelling tool anyway. so... i think i'm done.
## Post #5
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2018-02-05T18:58:22+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

Haha yeah I know materials can't be read with your texture loader plugin. Was just wondering if it was possible to do the same you did for the textures but with the materials. Abou the log I didn't realize that line was there, I have log enabled by default xD.

As far as I know they're loadable in noesis (at least the ps4 version ofc) dunno about exporting them but I can guess not xD. 
To be honest it was just to simplify the work  for just seeing models in a more recognizable way. It's not necessary at all apart from that ^^. So thank you anyway you gave us the texture tool which is more than enough with models being readable already. 

About your question on model names, nop. They have no names only "nh00" (this should be Noctis' head and one could think nh stand for that but then nh01 is gladios' head so no xD) and stuff like that.
## Post #6
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-02-05T22:48:57+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

got the files and noesis upgrade. added a format (seems to be BC7) that might come in handy.

and i still can't tackle the material assignment. closed source. 

holy sh!t. the rigs are awesome sauce. /sarcasm nice grope bones tho.
## Post #7
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-02-06T00:29:01+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

it seems that noesis can't no longer correctly export .earc files.  the exported file is less than 1 mb
## Post #8
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-02-06T01:22:31+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

yes. the noesis plugins are for the console data format. only the models work. format was not changed, obviously.

you can extract the earc files with this script -> [https://zenhax.com/viewtopic.php?f=17&t ... =80#p32136](https://zenhax.com/viewtopic.php?f=17&t=2826&start=80#p32136)
## Post #9
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2018-02-06T03:04:22+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

> Reply from tone
>
> it seems that noesis can't no longer correctly export .earc files.  the exported file is less than 1 mb

Noesis does not support pc earc files.
## Post #10
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2018-02-06T20:05:04+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

That stuff was written for PS4 data, it's a small miracle anything from a PC build loads!

I doubt it would be tough to adapt the material/texture support (or the animation support, which hasn't gone public yet), but I don't expect I'll get a chance to look at it any time soon. For the same reasons I haven't made a Noesis build in months.
## Post #11
- Username: Tohru Adachi
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 07, 2018 7:06 am
- Post datetime: 2018-02-11T03:01:38+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

Who can i extract Models, and view them in Final Fantasy 12 The Zodiac Age? It has the same phyre Engine as Final Fantasy 10 Hd.
## Post #12
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-02-11T03:18:44+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

> Reply from Tohru Adachi
>
> Who can i extract Models, and view them in Final Fantasy 12 The Zodiac Age? It has the same phyre Engine as Final Fantasy 10 Hd.
This is not the correct topic, please start a new topic for questions not related to FFXV.
## Post #13
- Username: Tohru Adachi
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Feb 07, 2018 7:06 am
- Post datetime: 2018-02-11T19:05:58+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

I Did. But it's like nobody be on this Forum like that.
## Post #14
- Username: wetbandaid
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 17, 2018 2:24 pm
- Post datetime: 2018-02-17T07:08:14+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

Anyone figure out a way to export the files back into .earc yet? Were older versions of Noesis able to do it?
## Post #15
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-02-28T22:45:50+00:00
- Post Title: Final Fantasy XY PC (Benchmark)

> Reply from wetbandaid
>
> Anyone figure out a way to export the files back into .earc yet? Were older versions of Noesis able to do it?

done it. [viewtopic.php?p=138275#p138275](http://forum.xentax.com/viewtopic.php?p=138275#p138275)

done the bms script to reimport btex files and the bms earc extractor managed to reimport the earchive. i dunno how the earc files work. i guess it is luck it could compress the file smaller to fit into the fixed chunks. this may need a fix.
## Post #16
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2018-03-05T02:01:19+00:00
- Post Title: Re: Final Fantasy XY PC (Benchmark)

Nice, finally we will be able to get our hands on it.



Tagging.
## Post #17
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2018-03-07T13:52:10+00:00
- Post Title: Re: Final Fantasy XY PC (Benchmark)

I seem to be having issues with useing the earc script with QuickBMS, this is for hte main game, and whatever I try it stops after a single file with the error message: "Error: Incomplete input file0: *file destination name here* can't read 4 bytes from offset.

Any help would be appreciated. :c
## Post #18
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-03-07T22:59:29+00:00
- Post Title: Re: Final Fantasy XY PC (Benchmark)

I have made an EARC archiver for FFXV PC: [viewtopic.php?f=10&t=17795](http://forum.xentax.com/viewtopic.php?f=10&t=17795)
## Post #19
- Username: RlySkiz
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 08, 2018 7:52 am
- Post datetime: 2018-03-08T00:30:21+00:00
- Post Title: Re: Final Fantasy XY PC (Benchmark)

> Reply from Darko
>
> Noesis supports models from this game (at least the benchmark):



The textures are not working.

http://www.mediafire.com/file/luwawwi6i ... eimages.7z

How did you even get to that part.. i have the newest Noesis version and no models can be loaded. Actually no files.. if i decide to export earc i get folders with new files that don't even show up in noesis at all anymore.
## Post #20
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2018-03-09T01:59:52+00:00
- Post Title: Re: Final Fantasy XY PC (Benchmark)

> Reply from RlySkiz
>
> Darko wrote:Noesis supports models from this game (at least the benchmark):



The textures are not working.

http://www.mediafire.com/file/luwawwi6i ... eimages.7z

How did you even get to that part.. i have the newest Noesis version and no models can be loaded. Actually no files.. if i decide to export earc i get folders with new files that don't even show up in noesis at all anymore.

Extracting everything:

[viewtopic.php?f=10&t=17645](http://forum.xentax.com/viewtopic.php?f=10&t=17645)
## Post #21
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2018-03-25T18:29:12+00:00
- Post Title: Re: Final Fantasy XY PC (Benchmark)

> Reply from episoder
>
> i assume there could be other formats from 0x19 to 0x20 that could represent dxt3 or dxt5 or bc6 and bc7 even, but... i can't guess.

decodes what you delivered.

unfortunately the Noesis-btex-plugin won't read any *_ba.btex files, which, as far as i can tell, are the textures with opacity information.
goes not only for glass but also plants (grass or leaves). so not only translucency stuff but also any texture with alpha-information aswell.
or did anyone successfully converted any of these _ba.btex files?
base/albedo, normal and metal/roughness/ao masks seem to work with no problem though.

the quickbms "btex to dds" converter also don't properly convert these.
FFXV Windows Edition obviously.

are you planing to support these filetypes?
btw. i used ffxvscout v2 for extracting.

i'm not trying to bring edited textures back into the game. 
just would like to have the alpha/opacity textures "readable" as the other ones.

here's some samples:

[https://mega.nz/#!kYZzGbxS!iTRftKe_BBal ... 9LYG655-PM](https://mega.nz/#!kYZzGbxS!iTRftKe_BBalZmy5vgfAT5KinfMejX7MO9LYG655-PM)
## Post #22
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-04-28T13:26:25+00:00
- Post Title: Re: Final Fantasy XY PC (Benchmark)

sorry for being late. plugin is now updated. 

[viewtopic.php?p=137657#p137657](http://forum.xentax.com/viewtopic.php?p=137657#p137657)

also fixed the bms script. sorry. lil mistake. 

[viewtopic.php?p=138275#p138275](http://forum.xentax.com/viewtopic.php?p=138275#p138275)
