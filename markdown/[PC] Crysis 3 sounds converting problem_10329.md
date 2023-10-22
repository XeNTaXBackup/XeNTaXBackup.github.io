## Post #1
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-12T20:49:28+00:00
- Post Title: [PC] Crysis 3 sounds converting problem

Hi mates,

I would know if you can help me here.

I unpacked " Sound.pak " with the PakDecrypt from [this topic](http://forum.xentax.com/viewtopic.php?f=10&t=9818&hilit=crysis+3&start=15). Next, I extracted sounds from FSB files with [this tool](http://aezay.site11.com/aezay/fsbextractor/) but it giving me messed files ( with any arguments, surely because of ADPCM format or something ).

Later, I found something interesting by myself. Apparently, we can be able to listen the sounds by using the [FMOD Event Player](http://www.fmod.org/fmod-downloads.html#FMODDesigner) but can't convert them.

So, my question is simple: how can we convert those sounds?

PS: If you need a little sample for testing, please ask.

Thank's a lot in advance.

Vosvoy
## Post #2
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2013-04-12T21:55:42+00:00
- Post Title: [PC] Crysis 3 sounds converting problem

Already working on adding support for FSB5 to vgmstream
## Post #3
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-13T12:32:08+00:00
- Post Title: [PC] Crysis 3 sounds converting problem

> Reply from bxaimc
>
> Already working on adding support for FSB5 to vgmstream

Oh, all right. Any link to follow the development state?

EDIT: Okay, so vgmstream seems to convert some ADPCM files to correct .wav files but it doesn't convert them properly for the others ( get messed files, again ). Maybe because of stereo header or multi-stream stuff?

Thank's in advance.
## Post #4
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-10-23T11:39:41+00:00
- Post Title: [PC] Crysis 3 sounds converting problem

Hi guys,

is somebody finally find a solution about IMA ADPCM sounds into .fsb from Crysis 3 ( or Warface )?

I tried ToWav and some VLC tests on them ( 0x00000091 or 0x00000090 unknown flag, according to FsbExtractor ) but it's not working. So, any help will be appreciated.

Thanks mates.

PS: Raw samples in attachment and the result on one of those non-working files.
[WarfaceSamples.zip](https://xentaxbackup.github.io/file/6726_WarfaceSamples.zip)
## Post #5
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-05-26T19:35:55+00:00
- Post Title: [PC] Crysis 3 sounds converting problem

> Reply from Vosvoy
>
> Hi guys,

is somebody finally find a solution about IMA ADPCM sounds into .fsb from Crysis 3 ( or Warface )?

I tried ToWav and some VLC tests on them ( 0x00000091 or 0x00000090 unknown flag, according to FsbExtractor ) but it's not working. So, any help will be appreciated.

Thanks mates.

PS: Raw samples in attachment and the result on one of those non-working files.
just an update, I finally found a tool that seems to work! it's based on the concept of the witcher 2's celt unpacker, it hooks into the fmodex.dll from the game in question. it was made for league of legends but it's worked (almost) flawlessly with tons of games files that refused to decode before. [http://wiki.spectralcoding.com/info:lea ... fsbextract](http://wiki.spectralcoding.com/info:league_of_legends_sounds:lolfsbextract)


it's a commandline application put the game's fmodex.dll in the same folder as LoLFSBExtract.exe, you start cmd.exe, drag in LoLFSBExtract.exe, hit space, drag in the input fsb, hit space then drag in an output directory and hit enter. the only problem i'm having is that some files are too fast or slow. but it has a built in method to fix this that you can read about in readme.txt.
## Post #6
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2014-05-27T17:22:07+00:00
- Post Title: [PC] Crysis 3 sounds converting problem

Well, many thanks pepper. You made my day.
