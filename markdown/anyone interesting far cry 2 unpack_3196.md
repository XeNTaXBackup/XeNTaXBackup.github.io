## Post #1
- Username: titanic
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Nov 30, 2006 4:58 am
- Post datetime: 2008-10-27T08:12:38+00:00
- Post Title: anyone interesting far cry 2 unpack

all biger than 100MB, sorry cant upload file.
## Post #2
- Username: solecist
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 27, 2008 6:27 am
- Post datetime: 2008-10-27T15:16:56+00:00
- Post Title: anyone interesting far cry 2 unpack

i actually registered to request that this game in particular be looked at. seeing this thread, i wish i got to it first. you could be a little more descriptive than this, man (the mistake in the title doesn't help our cause, either ).

anyway, the game uses DAT and FAT files like the last two far cry games, but attempts to open these files using the GE far cry instincts/evolution plugins does not work. this game DESEPERATELY needs to be fixed, and given ubisoft's track record that task is probably going to fall into the hands of the community (god willing). 

just looking at the far cry 2 general forums you can see the desire for a tool to unpack the dat files, so any attention that can be given to this would be much appreciated.
## Post #3
- Username: solecist
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 27, 2008 6:27 am
- Post datetime: 2008-10-28T03:19:46+00:00
- Post Title: anyone interesting far cry 2 unpack

i swear to god i will pay for this program TWICE if you guys get me unpacked far cry 2 DAT files. heeelp!
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-10-28T12:57:00+00:00
- Post Title: anyone interesting far cry 2 unpack

I will donate like $25 I swear (when i get the money, gah, just spent it on far cry 2).  i'll upload some examples too, i know off a few larger hosting sites. it'll be a little while though, i have school in an hour.
## Post #5
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-10-28T22:29:50+00:00
- Post Title: anyone interesting far cry 2 unpack

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: Zatch
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 27, 2008 3:07 am
- Post datetime: 2008-10-28T22:32:52+00:00
- Post Title: anyone interesting far cry 2 unpack

As far as audio goes, using audiorip (as well as Jaeder Naub & DecUbiSnd), I've been able to successfully extract all Ogg Vorbis music and voice files from Far Cry 2's sound.dat files. Unlike it's predecessor, however, simply using a common extraction tool to extract the entire archive has proved futile. I've scanned all the .dat files with audiorip (along with the other two programs listed above) and haven't been able to locate any environment, character, weapon, or vehicle sounds. Would these possibly be encoded in a different format not recognized? I've also scanned for .wav files to no avail. Has anyone else had better luck?
## Post #7
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-10-28T22:48:50+00:00
- Post Title: anyone interesting far cry 2 unpack

ubisnd detects some more of them, but not nearly all, still no weapon sounds or alot of the vehicle sounds.

I had to split the world file before scanning as it's too big for everything i tried.
## Post #8
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-10-29T23:39:32+00:00
- Post Title: anyone interesting far cry 2 unpack

These files are whack. The fat archives are the same, maybe they don't have the crc though. But none of the offsets point to any valid data. I cant figure out where 1 file begins and another starts. These files must be compressed or archived in some wierd way.

Also the fat file is telling me there are 5 files?
## Post #9
- Username: solecist
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 27, 2008 6:27 am
- Post datetime: 2008-10-29T23:42:33+00:00
- Post Title: anyone interesting far cry 2 unpack

nooooo
## Post #10
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-10-30T00:01:49+00:00
- Post Title: anyone interesting far cry 2 unpack

there are 6 dats and fats in the data_win32 directory. sound, sound_english, shadersobj, common, worlds and worlds_english with the last two being in a worlds subfolder.

just looking in the different files with a hex editor shows quite a few different structures between the common, sounds, worlds, and shader ones. the dunia.dll (main engine) is 17mb.  i can easily upload that if it would help.
## Post #11
- Username: solecist
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 27, 2008 6:27 am
- Post datetime: 2008-11-02T00:27:52+00:00
- Post Title: anyone interesting far cry 2 unpack

sooo....no official word on this yet?
## Post #12
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2008-11-14T10:11:23+00:00
- Post Title: anyone interesting far cry 2 unpack

I did some work some time ago for FC2.

[http://blog.gib.me/2008/10/28/unstable- ... evision-4/](http://blog.gib.me/2008/10/28/unstable-fc2-tool-binaries-from-svn-revision-4/) (see also [my SVN](http://svn.slurm.us/public/farcry2/trunk/)).
## Post #13
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2012-11-29T13:07:33+00:00
- Post Title: anyone interesting far cry 2 unpack

Any possibility in supporting Dunia 2.0 or well Far Cry 3 to use the games name directly?

It's still the .Dat and .Fat format albeit I would guess it's further updated along with the rest of the engine, would be interesting to have access to the contents of some of those files or in my case the various xml's therein to further configure the game, maybe eventually finding a way to re-enable the console prompt though I believe it's fully disabled in the normal builds so the chance of that happening is probably minimal.
(Without messing with the core Dunia .dll file at least, that's nothing I can do.)

There's no demo unfortunately so getting a example file that way is impossible and uploading files directly here is now against the forum rules as well (Causing problems by uploading copyrighted content I guess.) so all I can do at the moment is to ask and see what happens, game just came out too but it's not like I'm in a hurry or anything, US release date is also a bit different here and it won't be released until next Tuesday which probably also complicates things a bit.
(EU release date was today officially, normally it would have been this Tuesday for the US and then Friday for EU if I remember correctly.)

At worst they might be encrypted or some such to prevent this kind of action, unsure what other changes the format might have undergone, or the engine itself for that matter aside from very basic commonly available info.
(EDIT: Actually I guess the worst is if the core files are packed into the engine .dll files.)

I don't think there's anything else I can provide, might be possible to use Offzip to rip the files that way, bit crude perhaps but it would work for now, will have to try that and see what happens.

Engine isn't very mod friendly either from what I remember, then again the only tool for Far Cry 2 was the MP map editor which is likely one reason why, heh.


EDIT: Oh, decided to check the SVN mentioned above, seems there's already some progress with this, nice. 
[http://svn.gib.me/builds/dunia2/](http://svn.gib.me/builds/dunia2/)

EDIT: Seems to work just fine already, even better.

EDIT: Yeah this really helps, knowing the various commands, took a bit of work but it's possible to copy paste them into the default config file as long as it's under the correct section, will do for now.
(Shame it doesn't read the unpacked files, would be nice to get those logo videos out.)
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-29T15:54:07+00:00
- Post Title: anyone interesting far cry 2 unpack

Possible structure same and just need to find the correct filenames
## Post #15
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-11-29T15:59:28+00:00
- Post Title: anyone interesting far cry 2 unpack

> Reply from Ekey
>
> Possible structure same and just need to find the correct filenamesFormat is slightly different + they switched to CRC64 for filename hashes.
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-29T16:16:47+00:00
- Post Title: Re: anyone interesting far cry 2 unpack

I hope there will be no problems with the hash collision as with the FC2
## Post #17
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-11-29T17:15:35+00:00
- Post Title: Re: anyone interesting far cry 2 unpack

Filenames with CRC:

common: [https://dl.dropbox.com/u/9950356/common.txt](https://dl.dropbox.com/u/9950356/common.txt)
main: [https://dl.dropbox.com/u/9950356/main1.txt](https://dl.dropbox.com/u/9950356/main1.txt)
main: [https://dl.dropbox.com/u/9950356/main2.txt](https://dl.dropbox.com/u/9950356/main2.txt)
multi common: [https://dl.dropbox.com/u/9950356/multicommon.txt](https://dl.dropbox.com/u/9950356/multicommon.txt)
## Post #18
- Username: headrushmayor
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Nov 29, 2010 12:03 pm
- Post datetime: 2012-12-02T06:10:28+00:00
- Post Title: Re: anyone interesting far cry 2 unpack

i look at the DAT format if open in hex edit it a /UEF format i look up it come up with sum info i don't if this right thing but as most read
it a Unified Emulator Format (UEF) allows emulators of old computers to read and write files traditionally stored on cassette then found this site
it my have more info for u guys.
[http://electrem.emuunlim.com/](http://electrem.emuunlim.com/) when page load it go to new page so when it loads stop the page or will not get on it.
if go to tool page u download software for that format.
here site got website of if that helps.
[http://www.stairwaytohell.com/bbc/index ... tapeimages](http://www.stairwaytohell.com/bbc/index.html?page=tapeimages)
tool are MakeUEF
MakeUEF is a tool for creating UEF files from old tapes. The version formerly hosted here has been superseded by that available from The Acorn Preservation Project.

FreeUEF
FreeUEF is the opposite to MakeUEF. It plays back UEF files as sound waves. This program is slightly out of date and may not be able to handle the latest UEF files. All versions are used from the command line.

Windows Version (33.5 kB)
DOS Version (195 kB)
UNIX i386/ELF/glibc 2/OSS Version (7.95 kB)
Source Code (6.5 kB)

A good alternative to FreeUEF is UEFReader, a UEF reading plugin for Java Sound applications such as jlGui.
hope sumone no more about it. like open the game edit it, i use Dragon unpacker v5.6.2 on all files it found pictures, ogg, bik video from game, it found 688 ogg file in the sound DAT files u use AVS audio converter to convert to wav or mp3 play them.
## Post #19
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-12-02T06:21:46+00:00
- Post Title: Re: anyone interesting far cry 2 unpack

> Reply from headrushmayor
>
> useless information that has nothing to do with anythingNo.
