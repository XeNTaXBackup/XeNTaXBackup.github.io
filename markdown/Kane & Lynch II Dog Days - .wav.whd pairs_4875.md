## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-13T09:54:09+00:00
- Post Title: Kane & Lynch II: Dog Days - *.wav/*.whd pairs

The contents of this post was deleted because of possible forum rules violation.
[whd.png](https://xentaxbackup.github.io/file/3316_whd.png)
## Post #2
- Username: GenericRipper
- Rank: advanced
- Number of posts: 66
- Joined date: Mon Mar 22, 2010 12:41 am
- Post datetime: 2018-12-09T09:53:06+00:00
- Post Title: Kane & Lynch II: Dog Days - *.wav/*.whd pairs

I hope no one minds that I sort of hijack the thread and post a reply here; it's not a solution for his problem though, it's just a description of the difficulties with this format because OP is unavailable now.

So IOI used the same or slightly changed archive type from their numerous older titles: many Hitman installments, Freedom fighters & Kane & Lynch 1. However [this BMS](http://forum.xentax.com/viewtopic.php?f=13&p=87699#p87699) doesn't work on any K&L2 samples and reports unknown codec. Actually most archives seem to use at least 2 different codecs: PCM (10-15%) & ADPCM (it's merely a guess), that's why it's not possible to open such files in an audio editor & try to treat them as a bunch of SFX / VO glued into a single long sound.
This is why any kind of a script, program or utility would be most useful if it's able to unpack individual sounds from those *.WAV banks. Of course it'd be perfect if that solution also supported file names found in respective *.WHD files but I can't be too picky here.

There's a ZIP for each level / map which also stores an SND file, I'm not sure it can be useful in unpacking those *.WAV archives but I still included a few samples of such assets.
I even attached some screenshots of contents of those ZIPs, probably some contained files might be of some use to us? For example those LOC store subtitles for all the languages then *.TEX & *.ANM, *.HVK & *.MAT seem to have suggestive extensions (textures & animations, Havok Physics Engine files & materials) but there're many files with unknown purpose, I can post them if anyone's interested.
Finally it looks like all the banks with this name mask - either F*_Main_LS_Default.WAV or L*_Main_LS_Default.WAV - hold a single PCM-encoded track, maybe close inspection of such example files + their companion WHDs / SNDs should be a nice start?
Ultimately [this is a DL link for example files](https://drive.google.com/open?id=1C23_ln4h2auxaK3rhWCXSFIk5cRqX_5y), not any cuts but complete versions of them.

Best regards!
[1.png](https://xentaxbackup.github.io/file/15296_1.png)
