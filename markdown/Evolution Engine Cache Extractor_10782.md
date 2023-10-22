## Post #1
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-09-17T14:25:22+00:00
- Post Title: Evolution Engine Cache Extractor

[Download from Tools Blog](http://forum.xentax.com/blog/?p=1081) (Source code included)

This program allows you to extract cache files (.toc/.cache) from games using Digital Extremes' Evolution Engine. Just drag and drop a cache file on to the program and it will extract it into a subdirectory containing the file name. Make sure both .toc and .cache files are in the same folder. You can also specify where you want the files to be extracted using the /d switch.

Why use this instead of the Darkness II BMS? Because this keeps the proper directory structure and actually properly decompresses all the files. If you tried to extract the caches from any recent Evolution Engine games, the BMS script will produce junk.

Note: This extractor only works on version 20 caches. If you have a different version cache, send me a PM.

Other notes: 'H' caches contain file headers, 'B' caches contain the corresponding binary files (except for sounds, and maybe textures), and 'F' caches contain full sound files and textures. Also note that file extensions typically don't mean anything in these cache files. Those extensions are from before the files were cooked and compiled, so .fbx files are not in Autodesk FBX format, .wav files don't have WAVE headers, and .png files are not PNGs.

Version history:
[1.0.1.0 09/18/2013]
- Changed boilerplate console app text left over from app template (oops)
- Optimized LZ coder decoding (just a little bit, maybe)
- Writes file date from the TOC on to the extracted file
- Added some debugging workarounds (won't affect operation)
- Added cache version 16 to extractable versions (not fully tested; PM if you have any problems)
- Extractor can take filenames without the extension (e.g. "H.Font" instead of "H.Font.cache" or "H.Font.toc")

[1.0 09/17/2013]
- Initial release
## Post #2
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2013-09-17T17:02:52+00:00
- Post Title: Evolution Engine Cache Extractor

Trying the extractor but cannot get it to work. I use it on the latest update and on an old version I kept on the harddrive. Folders are there but no png can be seen. Most pngs in different folders are named like this:

0_I_l1.png
0_l0.png
0_l1.png
1_l0.png
1_l1.png
## Post #3
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-09-17T19:02:26+00:00
- Post Title: Evolution Engine Cache Extractor

What game are you extracting from? The files I've extracted from Warframe seem to have intelligible names. Also look at what I've mentioned in the first post. The .pngs are probably not PNGs. The ones in Warframe look like they could be uncompressed ARGB. When the extractor is working, check the console to see if it's giving any errors.
## Post #4
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-09-18T19:50:15+00:00
- Post Title: Evolution Engine Cache Extractor

I've posted an update at the tools blog. It has a couple of new features, as outlined in the first post.
## Post #5
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2013-09-18T22:39:52+00:00
- Post Title: Evolution Engine Cache Extractor

Yeah I think I missed that small text about the fbx, pngs etc  It is warframe I have and probably extracts exactly how it should. So what do we do with the files to make them work? Some more codedigging?
## Post #6
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2013-09-21T15:52:37+00:00
- Post Title: Evolution Engine Cache Extractor

Um, is The Darkness 2 supported? Because the program keeps telling me that it can't read the archive.
## Post #7
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-09-21T22:10:02+00:00
- Post Title: Evolution Engine Cache Extractor

I apparently forgot to move the latest build to the zip, so if you're seeing the program making new ".cache.cache" and ".cache.toc" files, download it again (from the same post). Also, make sure you have write access to both the cache files and the path you're extracting files to.

> Reply from hoodlum47
>
> Um, is The Darkness 2 supported? Because the program keeps telling me that it can't read the archive.
It probably has a different cache version. If the BMS script is to be trusted, this version could be using a different compression algorithm than later games. Send me a sample.
## Post #8
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2013-09-21T23:24:31+00:00
- Post Title: Evolution Engine Cache Extractor

> It probably has a different cache version. If the BMS script is to be trusted, this version could be using a different compression algorithm than later games. Send me a sample.

Actually, your "fixed" version seems to be doing the trick now.
## Post #9
- Username: musterfox
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 08, 2010 5:30 pm
- Post datetime: 2013-10-26T08:11:45+00:00
- Post Title: Evolution Engine Cache Extractor

Hi.

Trying to find some way to extract the music from Dark Sector (Steam Version). 

I tried using the "Evolution Engine Cache Extractor 1.0.1.0" tool but I ran into a couple of issues.

1) The Steam ver of DS does not have any .toc files, just .cache files whereas your first post says "Make sure both .toc and .cache files are in the same folder."

2) When I drag a .cache file onto EvolutionUnpack.exe, all it does it create a .toc file with the same name and its always a zero byte file. There is no sign of the extracted data.

Please tell me what I am doing wrong so I can extract the music files from DS.

Thanks in advance.
## Post #10
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-11-11T01:23:43+00:00
- Post Title: Evolution Engine Cache Extractor

> Reply from musterfox
>
> 1) The Steam ver of DS does not have any .toc files, just .cache files whereas your first post says "Make sure both .toc and .cache files are in the same folder."

Interesting. Could you PM me a sample?
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-11-29T18:58:54+00:00
- Post Title: Evolution Engine Cache Extractor

Hi GMMan. I'm trying to write maxscript to import models from Warframe online, and it seems that textures aren't extracted correctly from this game with Evolution Extractor, maybe you could fix this issue in future? It will help me greatly, thanks for great tool!
## Post #12
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2013-11-30T19:30:54+00:00
- Post Title: Evolution Engine Cache Extractor

> so .fbx files are not in Autodesk FBX format, .wav files don't have WAVE headers, and .png files are not PNGs.

The next thing to do is to figure out these new files that are spitted out but that is same amount of work again 

I am also hoping because they keep adding cooler and cooler robots in warframe but lets see
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-11-30T22:12:30+00:00
- Post Title: Evolution Engine Cache Extractor

I have some progress with meshes, it's will be great if textures will extract fine and we could convert them.
[warfrm.jpg](https://xentaxbackup.github.io/file/6812_warfrm.jpg)
## Post #14
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-12-03T15:54:22+00:00
- Post Title: Evolution Engine Cache Extractor

> Reply from zaramot
>
> Hi GMMan. I'm trying to write maxscript to import models from Warframe online, and it seems that textures aren't extracted correctly from this game with Evolution Extractor, maybe you could fix this issue in future? It will help me greatly, thanks for great tool!
I actually don't know what format textures are in. As far as I can tell they look like some sort of raw file. It's been a long time since I've touched any Revolution Engine stuff, but I think the extractor's working properly, since there were no warnings from the decompressed size check the last time I extracted various caches.

If I can find time I might add repacking into the program. If anyone needs it fast, I'll make a new version that will pack uncompressed.
## Post #15
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-12-04T10:20:00+00:00
- Post Title: Evolution Engine Cache Extractor

Hello GMMan. Thanks a lot for support and info. To say truth, I really hoped it's some issues from Cache Extractor side  Because in this case there was hope, that you can fix this. If textures extracted right, I have no idea what to do with them to convert into any known format.
## Post #16
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2013-12-04T21:50:01+00:00
- Post Title: Re: Evolution Engine Cache Extractor

hm, most of the image files spitted out are 42.6kb each no matter if it is diffuse, normal or specular, and no matter in what folder, so I am unsure if that is correct
## Post #17
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-12-04T23:09:35+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from pixellegolas
>
> hm, most of the image files spitted out are 42.6kb each no matter if it is diffuse, normal or specular, and no matter in what folder, so I am unsure if that is correct
Which cache type did you extract? The actual textures should be in the F cache, while the B caches may contain just the beginning of the files.
## Post #18
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-12-05T00:27:25+00:00
- Post Title: Re: Evolution Engine Cache Extractor

I have looked at some of the textures it looks like the textures are only getting half extracted.
If you add a normal DDS header on the images you will see the image go in and out like only half is there. Mabee there is some more compression on the textures.
But I am also not the best on image formats so I am not sure.
## Post #19
- Username: Rogue
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 21, 2013 6:32 am
- Post datetime: 2013-12-24T01:08:18+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from GMMan
>
> 
Other notes: 'H' caches contain file headers, 'B' caches contain the corresponding binary files (except for sounds, and maybe textures), and 'F' caches contain full sound files and textures. Also note that file extensions typically don't mean anything in these cache files. Those extensions are from before the files were cooked and compiled, so .fbx files are not in Autodesk FBX format, .wav files don't have WAVE headers, and .png files are not PNGs.

So I ended up using the extractor, however I do not quite understand how to make them fully usable files. I can make guesswork at what should be fbx/wav files, however it seems that when I extract an archive, it's only a partial file. As you stated, H is the header files, and 'F' is the full file, however in opening the files from the 'F' cache I'm not seeing any distinguishable headers that are similar across files. Do I need to combine the header and full files in some way? If so, how?

I'm mostly just interested in working with the textures/models/animations, so the fbx files are all I'm really interested in. I assume that when the main program unpacked the archive files it would have to have some sort of key to distinguish what files are what, if they are not defined beforehand? Could that key be usable in some form?

The only other (simple) issue is that I don't know the versioning behind caches (and if my version is indeed version 20).

Lastly, thanks for the current work you've already put into the extractor. Hopefully I can get all my questions out of the way, and happy holidays!
## Post #20
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-01-09T02:26:57+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Just noticed: there's a new Darkness 2 BMS script for an updated version of QuickBMS if you'd like to use QuickBMS for extraction instead. It looks like it has the path building down right, plus my decompression code is in there. Link: [http://aluigi.altervista.org/papers/bms ... kness2.bms](http://aluigi.altervista.org/papers/bms/others/darkness2.bms)
## Post #21
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2014-01-26T01:35:49+00:00
- Post Title: Re: Evolution Engine Cache Extractor

hello,GMMan
Sample .cache File [http://www.uploadmb.com/dw.php?id=1390185969](http://www.uploadmb.com/dw.php?id=1390185969)
Please test it,Pc game:Urban Trial Freestyle.
thanks,
## Post #22
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-01-28T15:24:39+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from reznov
>
> hello,GMMan
Sample .cache File http://www.uploadmb.com/dw.php?id=1390185969
Please test it,Pc game:Urban Trial Freestyle.
thanks,
That's not a game made by Digital Extremes. It probably doesn't use the same format.
## Post #23
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2014-01-28T20:39:29+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Dear Friend,Do you know of a way to do it?
## Post #24
- Username: toogte
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 11, 2012 8:57 pm
- Post datetime: 2014-02-01T20:49:15+00:00
- Post Title: Re: Evolution Engine Cache Extractor

will this help for dds header ? 
[http://msdn.microsoft.com/en-us/library ... ure_Arrays](http://msdn.microsoft.com/en-us/library/windows/desktop/bb943991%28v=vs.85%29.aspx#Texture_Arrays)

GMMan Thanks for ur hard work
## Post #25
- Username: reznov
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Dec 17, 2010 6:24 pm
- Post datetime: 2014-02-11T23:09:02+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from GMMan
>
> reznov wrote:hello,GMMan
Sample .cache File http://www.uploadmb.com/dw.php?id=1390185969
Please test it,Pc game:Urban Trial Freestyle.
thanks,
That's not a game made by Digital Extremes. It probably doesn't use the same format.
GMMan,you do not want to help me!
## Post #26
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2014-02-12T17:10:45+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from reznov
>
> GMMan wrote:reznov wrote:hello,GMMan
Sample .cache File http://www.uploadmb.com/dw.php?id=1390185969
Please test it,Pc game:Urban Trial Freestyle.
thanks,
That's not a game made by Digital Extremes. It probably doesn't use the same format.
GMMan,you do not want to help me!

Hm, I think after comments like that you will never get any help man. Maybe its translation problem but it does not sound nice
## Post #27
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-02-18T02:44:43+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from reznov
>
> GMMan wrote:reznov wrote:hello,GMMan
Sample .cache File http://www.uploadmb.com/dw.php?id=1390185969
Please test it,Pc game:Urban Trial Freestyle.
thanks,
That's not a game made by Digital Extremes. It probably doesn't use the same format.
GMMan,you do not want to help me!
You've already received a reply in your [other thread](http://forum.xentax.com/viewtopic.php?p=91716#p91716), which stated the sample file you sent only contained thumbnails of other files. As the other person said, there's not much point repacking unless you can find the archive where the actual data is stored. If you have, send another sample. Also, as I've said before, the game's not by Digital Extremes, and my unpacker probably won't help.
## Post #28
- Username: simple
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Sep 29, 2007 6:52 am
- Post datetime: 2014-04-03T19:51:24+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Hi,

I tried this with my non-steam version of Warframe and it is giving out error everytime I tried to extract the .cache files.
I keep getting the following error:

> Error opening archive. Please make sure that you can read the archive, and that
>
> it is actually an Evolution Engine cache.

My current Warframe Launcher and Engine version is following:

Launcher: 2014.03.06.12.06
Engine: 2014.03.26.11.53

Any help is much appreciated.
## Post #29
- Username: edge810446511
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 20, 2014 3:41 am
- Post datetime: 2014-09-19T19:43:15+00:00
- Post Title: Re: Evolution Engine Cache Extractor

This is really useful!
## Post #30
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2014-09-19T22:40:17+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Could it be as simple that your path is strange with strange characters?
## Post #31
- Username: tatodias
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 09, 2014 8:15 pm
- Post datetime: 2014-12-09T13:07:35+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Hi GMMan,

I downloaded the latest version of Evolution Engine Cache Extractor today dec, 9, 2014, and used it as you ordered, .cache and .toc at same folder (in fact I used the original game folder). The game I extracted is the Star Trek (2013 videogame) from Digital Extremes. However, the extracted files (.png, .fbx, .wav, etc.) aren't in the correct format, since they don't open at all. Your tool is generating the same garbage generated by QuickBMS?
## Post #32
- Username: Naftius
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 07, 2014 4:28 pm
- Post datetime: 2014-12-21T08:56:21+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Hi all, i' ve tried the extractor aswell. For me it did its job great thanks for that^^. I know you are not the creator of the importer, but perhaps you are (or even another member here) able to help me.
As in the guide i import the bones no problems so, but when i want to import the geometry data i mean the model i get a garbage triangle.

I am using 3DS Max 2010, could this be the Problem? What versions are you successors using to import the models?
Or is it related to the Cache version i read a few days ago about?
## Post #33
- Username: antoineflemming
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 01, 2014 11:50 am
- Post datetime: 2015-01-07T05:35:25+00:00
- Post Title: Re: Evolution Engine Cache Extractor

So, I'm new here and have tried this extractor on Warframe files to test it out. Is there a way to concatenate all these files with the same name? If there is a way to do that, then there may be a way to get these files working.
## Post #34
- Username: Rydian
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 25, 2015 5:12 am
- Post datetime: 2015-01-25T11:38:07+00:00
- Post Title: Re: Evolution Engine Cache Extractor

So in an attempt to view the textures, I've tried...

A - Extracting the F.x caches as-is to check the files inside them.
B - Extracting both the H.x and B.x copies, then concatenating the B.x files to the end of the matching H.x files with a hex editor.
C - Doing B, but adding a DDS (DXT3) header onto them instead of the H.x header.
D - Opening textures from the B.x and F.x copies as RAW images in common sizes (powers of 2) and common bit depths.

None of these have yielded anything that looks like a proper texture.  Any hints?
## Post #35
- Username: Coverop
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jun 17, 2014 5:41 pm
- Post datetime: 2015-03-10T13:52:01+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Okay so I extracted files, sounds and music but I can't open them.

It says "Cannot Render The File". So I decided to import to Audacity but it says this.


Does anyone know how to compile/open a sound/music from Evolution Engine?
It would greatly help me!
## Post #36
- Username: VoidsShadow
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 29, 2014 5:49 am
- Post datetime: 2015-05-30T02:28:41+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from Coverop
>
> Okay so I extracted files, sounds and music but I can't open them.

It says "Cannot Render The File". So I decided to import to Audacity but it says this.


Does anyone know how to compile/open a sound/music from Evolution Engine?
It would greatly help me!

You might need the Shark007 codec pack. Specifically the LAV decoder. The open in WMP just fine for me (Just in case, send me a sample.)
## Post #37
- Username: StrikerMan780
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 29, 2014 2:45 pm
- Post datetime: 2015-06-09T05:51:47+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Shark007 codec pack doesn't work.
## Post #38
- Username: FineNerds
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 16, 2015 5:54 pm
- Post datetime: 2015-08-24T07:10:06+00:00
- Post Title: Re: Evolution Engine Cache Extractor

I was wondering if there would ever be an update for a repacker?
## Post #39
- Username: Kamrad
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 19, 2015 6:01 pm
- Post datetime: 2015-08-31T15:05:49+00:00
- Post Title: Re: Evolution Engine Cache Extractor

The extracted sound files don't work (Warframe), same situation as Coverop. Do those wavs require a specific codec or something? Also, Shark007 doesn't work on it.
## Post #40
- Username: benwong01f611
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 05, 2015 6:05 pm
- Post datetime: 2015-10-04T04:15:16+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Why I cannot open the file after extraction?
## Post #41
- Username: antoineflemming
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jun 01, 2014 11:50 am
- Post datetime: 2015-10-23T04:31:27+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Will there ever be an update to this extractor? Seems like DE has updated the file format again, as the extracted fbx files aren't able to be imported with zaramot's current MaxScript.
## Post #42
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2015-10-24T15:14:26+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Just quickly popping in. Digital Extremes has made a Steamworks submitter for skins and whatnot, could be interesting. See [https://forums.warframe.com/index.php?/ ... aunch-faq/](https://forums.warframe.com/index.php?/topic/549103-steam-workshop-launch-faq/), install at [url=steam://install/396050]steam://install/396050[/url].
## Post #43
- Username: EinarTheRed
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 22, 2015 5:00 am
- Post datetime: 2015-11-24T16:32:45+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Alright, I will bring this thing to light after 2 years. I have the tool and it extracts everything fine, but nothing can read the files (anymore?). Is it something I am doing wrong, or did the change their files from what this tool is creating now?
## Post #44
- Username: xbeton0L
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Dec 16, 2011 10:40 pm
- Post datetime: 2015-12-02T03:15:52+00:00
- Post Title: Re: Evolution Engine Cache Extractor

While still new to this, I am not entirely lost. Is there a type of known pattern we can use to figure out the correct headers for the textures? Or if there's a way to sample some of the data into an image format using an arbitrary header? If it's all compression however, I'm not sure what to do about that.

I could be entirely wrong about this too.
## Post #45
- Username: AnonymousDinosaur
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 15, 2016 6:32 pm
- Post datetime: 2016-01-15T11:12:00+00:00
- Post Title: Re: Evolution Engine Cache Extractor

I am working on a project and want to extract a specific model for something. I know no one got anywhere with the textures, but is there anyone who has been able to get the .fbx files to work in 3DS Max or some other program?
## Post #46
- Username: AnonymousDinosaur
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 15, 2016 6:32 pm
- Post datetime: 2016-01-15T11:13:30+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from zaramot
>
> Hello GMMan. Thanks a lot for support and info. To say truth, I really hoped it's some issues from Cache Extractor side  Because in this case there was hope, that you can fix this. If textures extracted right, I have no idea what to do with them to convert into any known format.

Did you ever finish this script?
I don't know if you still hang around this forum, but I am looking for a way to get a hold of the void key model from Warframe.

The .fbx files just don't seem to work in 3DS max for me.
## Post #47
- Username: HBOSS81
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 22, 2015 9:48 am
- Post datetime: 2016-02-16T06:03:42+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Great Tools. After some tinkering, troubleshooting, and refreshing my brain on this stuff..I managed to extract absolutely everything from the game (Up to the latest update) as far as the models go, minus the textures. But I did learn how to read the fragmented files in order to reassemble them on the models inside 3DS MAX or Maya (much easier to re-texture).

Using the Evolution Engine unpack-er, you create (extract) the "H/B.Misc.cache/" folders separately from the Warframe directory, allowing you to have the "H.Misc" folder with the smaller files and the "B.Misc" with the larger. (This is how you import content into 3ds max with the importer tool). 

Now you just follow this: (replace Inugami_skel.fbx with the actual file you're importing)

1. Load Warframe_Bones.ms
2. Point it to a H.misc.cache file like Inugami_skel.fbx
3. A new dialogue shows up, this time choose Inugami_skel.fbx in B.misc.cache
Bones will be loaded

4. Load Warframe_Online.ms
5. Point it to H.misc.cache file Inugami_skel.fbx
6. A new dialogue shows up, this time choose Inugami_skel.fbx in B.misc.cache
Model will be loaded above bones

If you also want sounds, use this: (Google the link, I'm just providing instructions)

Evolution engine sound convertor (for games like Warframe, Darkness II, Star Trek, Dark Sector...)

Tested with Darkness II, Star Trek, Warframe, but may work with all other games.

How to use it:
- Extract all sound files to separate folders with "EvolutionUnpack" tool.
- Choose the game from the dropdown list;
- Choose 3 misc audio folders: H, B, F, those named like H.Misc, e.t.c
- choose an new empty folder for extracted sound.
- Click "convert all".
- Choose 3 language audio folders (if present), those named like H.Misc_en (for english), or your language
- choose another folder for extracted sound if you wish.
- Click "convert all".

Most music files will be in WAV with plain PCM.
Most SFX files will be in WAV files with Microsoft ADPCM codec.
Most voice files will be in .XWMA format. You can play those if you have proper codecs installed, otherwise use xWMAEncode.exe to convert those to WAV.

Important notes:
- No progress bar. Just wait for the end message.
- No error handling! Be careful.

I can improve the tool later (add progress bar, error handling, support all games, etc) if there will be interest in this.

Once I finish my master collection and complete re-applying textures on the models I'll post the goodies online for the community  The models will eventually be rigged ready to use for animations using the original bones from the game (just need to solve the issue about some bones not loading properly and staying in the place they were supposed to be in the first place. I do this as a fan and gain no money from any of this, just putting out there. I'm just trying to make some animations and give the community something we've all been asking for but noone has deemed able to deliver. I intend on making some action packed webisodes for WF so stay tuned.
## Post #48
- Username: mae1storm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 12, 2016 7:27 pm
- Post datetime: 2016-03-12T12:45:32+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Hello, cant import any model (maybe i do something wrong?). I need Valkyre hersemi skin with bastet helmet. But when i try to import files by description above script says "unable to convert: undefined to type: integer" on 68 line of the Warframe_bones.cs... what can be done with this problem?

P.S. Sorry for my bad english.
## Post #49
- Username: Coverop
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jun 17, 2014 5:41 pm
- Post datetime: 2016-04-16T01:12:37+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Hello.
I come with a problem.
I've decided to extract and convert the audio files of Warframe, but Form1 gives me a headache.

> See the end of this message for details on invoking 
>
> just-in-time (JIT) debugging instead of this dialog box.
>
> 
>
> ************** Exception Text **************
>
> System.ArgumentException: The path is not of a legal form.
>
>    at System.IO.Path.NormalizePathFast(String path, Boolean fullCheck)
>
>    at System.IO.DirectoryInfo..ctor(String path)
>
>    at Evolution_sound_convertor.Form1.button5_Click(Object sender, EventArgs e)
>
>    at System.Windows.Forms.Control.OnClick(EventArgs e)
>
>    at System.Windows.Forms.Button.OnMouseUp(MouseEventArgs mevent)
>
>    at System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
>
>    at System.Windows.Forms.Control.WndProc(Message& m)
>
>    at System.Windows.Forms.ButtonBase.WndProc(Message& m)
>
>    at System.Windows.Forms.Button.WndProc(Message& m)
>
>    at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
>
>    at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)
>
> 
>
> 
>
> ************** Loaded Assemblies **************
>
> mscorlib
>
>     Assembly Version: 2.0.0.0
>
>     Win32 Version: 2.0.50727.5485 (Win7SP1GDR.050727-5400)
>
>     CodeBase: file:///C:/Windows/Microsoft.NET/Framework64/v2.0.50727/mscorlib.dll
>
> ----------------------------------------
>
> Evolution_sound_convertor
>
>     Assembly Version: 1.0.0.0
>
>     Win32 Version: 1.0.0.0
>
>     CodeBase: file:///D:/YOUTUBE/SFX/WARFRAME/NEW/Evolution_sound_convertor.exe
>
> ----------------------------------------
>
> System.Windows.Forms
>
>     Assembly Version: 2.0.0.0
>
>     Win32 Version: 2.0.50727.5491 (Win7SP1GDR.050727-5400)
>
>     CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Windows.Forms/2.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
>
> ----------------------------------------
>
> System
>
>     Assembly Version: 2.0.0.0
>
>     Win32 Version: 2.0.50727.5485 (Win7SP1GDR.050727-5400)
>
>     CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System/2.0.0.0__b77a5c561934e089/System.dll
>
> ----------------------------------------
>
> System.Drawing
>
>     Assembly Version: 2.0.0.0
>
>     Win32 Version: 2.0.50727.5495 (Win7SP1GDR.050727-5400)
>
>     CodeBase: file:///C:/Windows/assembly/GAC_MSIL/System.Drawing/2.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
>
> ----------------------------------------
>
> 
>
> ************** JIT Debugging **************
>
> To enable just-in-time (JIT) debugging, the .config file for this
>
> application or computer (machine.config) must have the
>
> jitDebugging value set in the system.windows.forms section.
>
> The application must also be compiled with debugging
>
> enabled.
>
> 
>
> For example:
>
> 
>
> <configuration>
>
>     <system.windows.forms jitDebugging="true" />
>
> </configuration>
>
> 
>
> When JIT debugging is enabled, any unhandled exception
>
> will be sent to the JIT debugger registered on the computer
>
> rather than be handled by this dialog box.

Note that I selected in Form1, Warframe not any other game.
It doesn't want to proceed anymore.
## Post #50
- Username: Borker
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 05, 2016 12:37 pm
- Post datetime: 2016-08-05T06:46:51+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Any chance anyone has a mirror for this since it seems to be impossible to login to the blog area?
## Post #51
- Username: gormonn
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 07, 2016 7:26 am
- Post datetime: 2016-08-07T00:21:29+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Hi! I am interested at localization files.
Do you have any idea where and what format they are stored in .cache?
Everything else, do not know how to download the program, as Registration of forum does not approach to a blog page:
[blog/?p=1081](http://forum.xentax.com/blog/?p=1081)
## Post #52
- Username: tathannibal
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jun 16, 2015 7:05 am
- Post datetime: 2016-10-02T13:46:05+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Download link not Working Pls help me.
## Post #53
- Username: Frage
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 26, 2016 11:55 pm
- Post datetime: 2016-11-12T13:07:48+00:00
- Post Title: Re: Evolution Engine Cache Extractor

I don't wish to annoy anyone, but as several others already pointed out, there does note seem to be a way to download it.
## Post #54
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-13T01:06:38+00:00
- Post Title: Re: Evolution Engine Cache Extractor

seems working fine once you log in to the tools blog  
here is local copy


 evolutionunpack101_fixed.zip
(57.83 KiB) Downloaded 269 times
## Post #55
- Username: Night Terror
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 13, 2016 12:49 am
- Post datetime: 2016-11-16T10:21:28+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from AceWell
>
> seems working fine once you log in to the tools blog  
here is local copy
evolutionunpack101_fixed.zip

Good to see my first post is one of thanks! 

Thanks AceWell for posting this! And what timing too, I was getting desperate 

I've searched earlier today and it looks like the Tools Login issue is something that the admins are aware of, but I guess takes some time to change (or they think it's changed, and no one has reported otherwise).

Anyways, thanks again!
## Post #56
- Username: khambattaproject
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 22, 2017 4:26 am
- Post datetime: 2017-02-20T02:42:08+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Hi I am trying to access the FBX models for Star Trek the video game that do not have bones, is there anyway that I can do that at all?
## Post #57
- Username: artchitect
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 28, 2017 2:13 pm
- Post datetime: 2017-05-19T06:29:19+00:00
- Post Title: Re: Evolution Engine Cache Extractor

2017 and trying this, how does one combine H and F texture files so they can be usable?
## Post #58
- Username: barquetin16
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Mar 21, 2017 12:16 am
- Post datetime: 2018-01-08T04:53:23+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Can someone tell me a way to open the textures from the game Star Trek plz, how do i combine the H with the F and the B too
## Post #59
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-08T22:33:57+00:00
- Post Title: Re: Evolution Engine Cache Extractor

you need to post some samples for examination.
## Post #60
- Username: barquetin16
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Mar 21, 2017 12:16 am
- Post datetime: 2018-01-10T23:47:29+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from AceWell
>
> you need to post some samples for examination.
Here are some samples
[Kirk.rar](https://xentaxbackup.github.io/file/13777_Kirk.rar)
## Post #61
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-11T03:03:56+00:00
- Post Title: Re: Evolution Engine Cache Extractor

thanks, i don't see any of these that you mentioned  

> Reply from barquetin16
>
> .... how do i combine the H with the F and the B too
also what platform did your samples come from?
google says it was released on PC, PS3 and X360

your samples are headerless and possibly paletted data,
i guess i need to read through the whole thread for some clues.
## Post #62
- Username: barquetin16
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Mar 21, 2017 12:16 am
- Post datetime: 2018-01-12T16:04:22+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from AceWell
>
> thanks, i don't see any of these that you mentioned  
barquetin16 wrote:.... how do i combine the H with the F and the B too
also what platform did your samples come from?
google says it was released on PC, PS3 and X360

your samples are headerless and possibly paletted data,
i guess i need to read through the whole thread for some clues.
This is the pc version of star trek, and about the H,F,B thing there are 3 textures folders in the game each one with same file name but with different size.
## Post #63
- Username: barquetin16
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Mar 21, 2017 12:16 am
- Post datetime: 2018-01-12T17:22:08+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from AceWell
>
> thanks, i don't see any of these that you mentioned  
barquetin16 wrote:.... how do i combine the H with the F and the B too
Here are the 3 folders samples:
[https://drive.google.com/file/d/15BSja5 ... g4VO-/view](https://drive.google.com/file/d/15BSja5i27Q2CuFBJGfV_MtC_I_sg4VO-/view)
## Post #64
- Username: WaterBlade
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 27, 2018 8:05 pm
- Post datetime: 2018-01-27T12:17:18+00:00
- Post Title: Re: Evolution Engine Cache Extractor

I get the files but they are all corrupt and useless (png, wav etc..), plus I need a repack. If anyone could make a simple unpack/repack tool where just drag and drop for the unpack/repack I could pay it (I do not know where to apply the demand so I put it here)
(For evolution engine, warframe)
## Post #65
- Username: xbeton0L
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Dec 16, 2011 10:40 pm
- Post datetime: 2018-06-15T10:28:43+00:00
- Post Title: Re: Evolution Engine Cache Extractor

I'm actually just interested in extracting the files. How do I learn how to make this work?
## Post #66
- Username: Valkorion
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 6:30 am
- Post datetime: 2018-08-23T21:30:55+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Note: This extractor only works on version 20 caches. If you have a different version cache, send me a PM.
I have the recent hotfix version 23, is this one still ok or in every update you also have to update? Man, kinda of a bump then.

Thanks in advance.
## Post #67
- Username: flyingfolk27
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 25, 2018 2:05 am
- Post datetime: 2018-12-24T18:12:18+00:00
- Post Title: Re: Evolution Engine Cache Extractor

I'm wanting to 3d Print Captain Kirk's Phaser from the 2013 Star Trek game and cannot find any files of this anywhere! Any help would be greatly appreciated.

Thanks
## Post #68
- Username: MikaKyubi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 20, 2013 10:06 pm
- Post datetime: 2019-03-08T20:19:28+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Pardon, and I do hope this isn't the wrong place to put this, but has anyone yet successfully managed to translate the models and textures extracted from the cache files the Unpacker decrypts?  If there's a specific tool for doing so, I'd appreciate hearing about it, as the most recent update for Warframe (March 7, 2019) has broken the ability to do captures from it using NinjaRipper.  If there's some way of directly decrypting these files into a usable format, it would be most appreciated.

Many thanks in advance.
## Post #69
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-24T15:13:32+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Could you upgrade this tool? Thank you
## Post #70
- Username: Gbronski
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 30, 2019 8:26 am
- Post datetime: 2019-07-30T00:31:04+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Probably a shout, I've extracted all the sounds from "The Darkness 2" and they've came out as .wav. But they're all unplayable in any software/player I use. Any help? I know this is old and all
## Post #71
- Username: MikaKyubi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 20, 2013 10:06 pm
- Post datetime: 2019-07-30T14:55:55+00:00
- Post Title: Re: Evolution Engine Cache Extractor

There's a fair likelihood that the so-called ".wav" files are actually something else entirely.  I know I had to use a sound extractor program (from somewhere here on the forums, though I have forgotten where) in order to decode them into proper, usable .wav files, and .xwma files.  Some of those latter, note, might not be readable, especially if they use a different format.  There's a few not commonly used that the xwma conversion software just won't parse.  My guess is that the encoding for those specific ones is included only in the developer's version of the tool.
## Post #72
- Username: Gbronski
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 30, 2019 8:26 am
- Post datetime: 2019-07-30T21:43:13+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from MikaKyubi ↑Tue Jul 30, 2019 10:55 pm at Tue Jul 30, 2019 10:55 pm
>
> 
There's a fair likelihood that the so-called ".wav" files are actually something else entirely.  I know I had to use a sound extractor program (from somewhere here on the forums, though I have forgotten where) in order to decode them into proper, usable .wav files, and .xwma files.  Some of those latter, note, might not be readable, especially if they use a different format.  There's a few not commonly used that the xwma conversion software just won't parse.  My guess is that the encoding for those specific ones is included only in the developer's version of the tool.

Gotcha, so there is nothing I can do to get around this or no tools I can find? Really hoping I could get access to all the sounds files
## Post #73
- Username: MikaKyubi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 20, 2013 10:06 pm
- Post datetime: 2019-07-30T21:47:38+00:00
- Post Title: Re: Evolution Engine Cache Extractor

The sound converter tool should be somewhere here on the Xentax forums.  I merely do not remember where precisely.  I recommend doing some looking about here, and judicious use of the Search function for the tool in question (Evolution Sound Convertor).

The download is found here:

[viewtopic.php?f=17&t=13701](https://forum.xentax.com/viewtopic.php?f=17&t=13701)

in the first post.
## Post #74
- Username: Gbronski
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 30, 2019 8:26 am
- Post datetime: 2019-07-30T22:03:57+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Will check thank you, some sounds can be heard in it's raw form but gonna guess most is unreadable without this tool ect.
## Post #75
- Username: jetomawolf
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 10, 2019 9:04 pm
- Post datetime: 2020-01-26T00:00:13+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Hi guys,

how can I open fbx and work with these?

Every time I opened an fbx file, blender or 3ds said that 
"couldn't open ... (invalid header)".

Thanks to all!
## Post #76
- Username: MikaKyubi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 20, 2013 10:06 pm
- Post datetime: 2020-01-26T18:07:07+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from jetomawolf ↑Sun Jan 26, 2020 8:00 am at Sun Jan 26, 2020 8:00 am
>
> 
Hi guys,

how can I open fbx and work with these?

Every time I opened an fbx file, blender or 3ds said that 
"couldn't open ... (invalid header)".

Thanks to all!

The extracted files are not in an actual .fbx format, but instead are, at a guess, some other form.  I am not enough of an expert to be able to give further guidance past that simply information, though.  I do believe, however, that there may be some mention of this somewhere in this thread.
## Post #77
- Username: vertigocrisis
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 15, 2019 8:08 am
- Post datetime: 2020-06-24T06:05:05+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Hey! It seems like something has changed on Warframe's side of things within the last 6-12 months. EvolutionUnpack is able to successfully convert the contents of the .Misc.cache files, but not the .Misc_en.cache files! This leaves a lot of files inaccessible! I love being able to use this program, and I dearly hope that GMMan is still around in some form, so that he might agree to take a look and hopefully identify where it's failing.
## Post #78
- Username: Aetheric
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon May 04, 2020 2:03 am
- Post datetime: 2020-10-25T01:34:13+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Sorry for potentially trying to necromance this topic, but does anyone have contact with GMman or know if he is still working on the extractor?
## Post #79
- Username: Valkorion
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 6:30 am
- Post datetime: 2020-11-11T23:13:43+00:00
- Post Title: Re: Evolution Engine Cache Extractor

Can't access Tools Blog, says its forbidden
EDIT:
"You don't have permission to access this resource.Server unable to read htaccess file, denying access to be safe"
## Post #80
- Username: Aetheric
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon May 04, 2020 2:03 am
- Post datetime: 2020-11-14T03:06:36+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from Valkorion ↑Thu Nov 12, 2020 7:13 am at Thu Nov 12, 2020 7:13 am
>
> 
Can't access Tools Blog, says its forbidden
EDIT:
"You don't have permission to access this resource.Server unable to read htaccess file, denying access to be safe"

I believe you can still find a download to it on someone's GitHub however the extractor is no longer able to produce data other than a toc for the caches. I think this might be due to Digital Extremes trying to compress the game down because whenever you try to extract a cache every file that is attempted to be extracted fails with the error: "Error extracting file: Attempting to index below decompression buffer" This error is resulting from the LZCoder class in which throws the exception when a variable called decompDistBeginPos is less than zero.
## Post #81
- Username: Aetheric
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon May 04, 2020 2:03 am
- Post datetime: 2020-11-14T03:07:57+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from Aetheric ↑Sat Nov 14, 2020 11:06 am at Sat Nov 14, 2020 11:06 am
>
> 
Valkorion wrote: ↑Thu Nov 12, 2020 7:13 am
Can't access Tools Blog, says its forbidden
EDIT:
"You don't have permission to access this resource.Server unable to read htaccess file, denying access to be safe"


I believe you can still find a download to it on someone's GitHub however the extractor is no longer able to produce data other than a toc for the caches. I think this might be due to Digital Extremes trying to compress the game down because whenever you try to extract a cache every file that is attempted to be extracted fails with the error: "Error extracting file: Attempting to index below decompression buffer" This error is resulting from the LZCoder class in which throws the exception when a variable called decompDistBeginPos is less than zero.

This makes me think that digital extremes has changed their compression algorithm and we would have to modify our existing code to decompress it.
## Post #82
- Username: MikaKyubi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 20, 2013 10:06 pm
- Post datetime: 2020-11-14T03:11:49+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from Aetheric ↑Sat Nov 14, 2020 11:07 am at Sat Nov 14, 2020 11:07 am
>
> 
This makes me think that digital extremes has changed their compression algorithm and we would have to modify our existing code to decompress it.

Whilst I am by no means a programmer nor coder, this sounds reasonable from the error message generated.  sadly, unless someone has the source code for the tool, it might be dead at this point, which is quite sad.
## Post #83
- Username: Aetheric
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon May 04, 2020 2:03 am
- Post datetime: 2020-11-14T23:44:05+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from MikaKyubi ↑Sat Nov 14, 2020 11:11 am at Sat Nov 14, 2020 11:11 am
>
> 
Aetheric wrote: ↑Sat Nov 14, 2020 11:07 am
This makes me think that digital extremes has changed their compression algorithm and we would have to modify our existing code to decompress it.


Whilst I am by no means a programmer nor coder, this sounds reasonable from the error message generated.  sadly, unless someone has the source code for the tool, it might be dead at this point, which is quite sad.

I have a copy of the source code which I downloaded from the tools blog when it was still accessible that I could upload to my GitHub account.
## Post #84
- Username: MikaKyubi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Sep 20, 2013 10:06 pm
- Post datetime: 2020-11-15T02:18:39+00:00
- Post Title: Re: Evolution Engine Cache Extractor

> Reply from Aetheric ↑Sun Nov 15, 2020 7:44 am at Sun Nov 15, 2020 7:44 am
>
> 
I have a copy of the source code which I downloaded from the tools blog when it was still accessible that I could upload to my GitHub account.

I fear I wouldn't know the first thing to do with it.  Though, if you feel you're up to the task, I wish you luck!  I'll definitely pay attention!
## Post #85
- Username: yasumoru
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 10, 2021 5:22 pm
- Post datetime: 2021-10-10T10:02:44+00:00
- Post Title: Re: Evolution Engine Cache Extractor

i can't downloading it, how should i do it ?
## Post #86
- Username: alien6
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 03, 2021 12:57 am
- Post datetime: 2021-11-20T01:19:18+00:00
- Post Title: Re: Evolution Engine Cache Extractor

When trying to decompress the files presents this error! Does anyone know how to fix?





 WF-Evolution-Unpack-master.zip
Source Code + exe (61.99 KiB) Downloaded 89 times
