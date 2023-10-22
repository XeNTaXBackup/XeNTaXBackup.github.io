## Post #1
- Username: chtiplayer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jun 15, 2010 3:52 am
- Post datetime: 2013-08-10T11:59:29+00:00
- Post Title: Need help to convert xma to mp3 or wave.

Hi all,

I've seen that one tool existed to convert xma to wav called ToWav but he doesn't work with xma's Injustice God among us Xbox 360 files.
Also the russian website seems to be dead.
So is there another way to convert this audio file type into wav file or MP3 file?

I've got a project, convert all voices clash battle into sounds playable.

THanks a lot for your help and sorry for my poor english.
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-08-11T02:34:27+00:00
- Post Title: Need help to convert xma to mp3 or wave.

You need to adjust the header of the files before ToWAV will convert it from XMA to WAV.

You will need the following:
[1. QuickBMS from Aluigi](http://aluigi.altervista.org/papers/quickbms.zip)
[2. AlphaTwentyThree's XMA Transform Script](http://forum.xentax.com/download/file.php?id=5968)
[3. XMA Parse from HCS](http://hcs64.com/files/xma_parse011.zip)

Download QuickBMS/XMA Transform script/XMA Parse and extract them into the same folder.

Run QuickBMS, select the XMA transform script, choose all of the files you wish to convert, choose where you want the XMAs to be placed.

The script will then run and manipulate the files and produce new XMA files that can be decoded with ToWAV.
## Post #3
- Username: chtiplayer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jun 15, 2010 3:52 am
- Post datetime: 2013-08-13T17:12:53+00:00
- Post Title: Need help to convert xma to mp3 or wave.

Thanks to you.

I ve discovered today that Zod will have a new skin because there is file into Zatanna DLC's files called CHAR_Zod_A.xxx
I wish to extract all textures to see the skin.

Or if i let u the xxx file, is there a way that u make a render of this New Zod SKin?
[https://mega.co.nz/#!GEhylJJQ!OE29CEfeN ... acL5mDtsoA](https://mega.co.nz/#!GEhylJJQ!OE29CEfeNH8HQuZTLIrEBXWSYhEck7GFZacL5mDtsoA) in upk
or
[https://mega.co.nz/#!DEBxXRgb!OnEDD2wdc ... FftNhA5ND8](https://mega.co.nz/#!DEBxXRgb!OnEDD2wdcu1qi7pKH1-bQj00nVJJhKw6ZFftNhA5ND8) in XXX

I ve tried to follow your steps for xma files but i ve got an error with all xma injustice files:
[http://www.hostingpics.net/viewer.php?i ... 1error.jpg](http://www.hostingpics.net/viewer.php?id=715881error.jpg)
## Post #4
- Username: SSBMagy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 22, 2021 6:09 pm
- Post datetime: 2021-07-27T07:39:34+00:00
- Post Title: Need help to convert xma to mp3 or wave.

> Reply from brendan19 ↑Sun Aug 11, 2013 10:34 am at Sun Aug 11, 2013 10:34 am
>
> 
You need to adjust the header of the files before ToWAV will convert it from XMA to WAV.

You will need the following:
1. QuickBMS from Aluigi
2. AlphaTwentyThree's XMA Transform Script
3. XMA Parse from HCS

Download QuickBMS/XMA Transform script/XMA Parse and extract them into the same folder.

Run QuickBMS, select the XMA transform script, choose all of the files you wish to convert, choose where you want the XMAs to be placed.

The script will then run and manipulate the files and produce new XMA files that can be decoded with ToWAV.

2nd link is dead, got another link to that download?
## Post #5
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2021-07-31T12:06:32+00:00
- Post Title: Need help to convert xma to mp3 or wave.

Good news, vgmstream now supports XMA natively.

The test.exe included can decode XMA files to WAV without any issue.

Get it here
[https://vgmstream.org/downloads](https://vgmstream.org/downloads)
