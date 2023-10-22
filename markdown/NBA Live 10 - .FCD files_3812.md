## Post #1
- Username: nickcollison
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 27, 2009 12:45 pm
- Post datetime: 2009-10-27T17:54:32+00:00
- Post Title: NBA Live 10 - .FCD files

Hello,

I'm a sound editor that makes patches for the NBA Live series, and some comics-related games.

From NBA Live 01, the series has compressed their audio into .fcd files. I can read them with a tool called ASF Exporter. This works for all PC (NBA Live 01 up to 08), PS2 and PSP versions.

The thing is, PS2 NBA Live 09 and PSP NBA Live 10 both have outdated speech files, which means that some rookies are missing. At nba-live.com, we are trying to provide a PC replacement for Live 10 by patching NBA Live 06.

The only option left is to extract the files from the next gen versions (Xbox 360 or PS3). Xbox 360 works with the same .fcd files, but the ASF can't get anything out of them. So, it's obvious that the audio files have modified their extension.

Would you be able to tell me the extension of those audio files? And if they can be extracted at all?

Another question: Regarding MUA2, has anybody been able to extract anything out of their audio files? I reckon it's almost impossible, but I had to ask.

Thanks in advance.
## Post #2
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-27T19:44:38+00:00
- Post Title: NBA Live 10 - .FCD files

Mua2 360 version uses multichannel mp3 in a bigfile, scan for fsb4 headers, extract all of the fsb's, and run a tool called mp3extract on the fsb's (google it). This will give you 3 layers of mp3 music for each fsb.
## Post #3
- Username: nickcollison
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 27, 2009 12:45 pm
- Post datetime: 2009-10-27T20:13:21+00:00
- Post Title: NBA Live 10 - .FCD files

> Reply from pietastesgood
>
> scan for fsb4 headers, extract all of the fsb's

Excuse me for my ignorance, but how do you actually do that? I assume you must work with a hex editor, and my knowledge is fairly rudimentary in that area.

Of course, feel free to explain it to me as long as it doesn't take too much time and effort. I don't want to waste your time.
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2009-10-27T22:08:28+00:00
- Post Title: NBA Live 10 - .FCD files

a tool called FSBii can scan for embedded fsbs

edit: found a link: [http://hcs64.com/files/fsbii00.zip](http://hcs64.com/files/fsbii00.zip)
## Post #5
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-27T23:44:13+00:00
- Post Title: NBA Live 10 - .FCD files

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: nickcollison
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 27, 2009 12:45 pm
- Post datetime: 2009-10-28T17:32:58+00:00
- Post Title: NBA Live 10 - .FCD files

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-11-01T10:09:02+00:00
- Post Title: NBA Live 10 - .FCD files

fsbii is up to 0.6: [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)
In case you had any trouble, bugs may be fixed.
## Post #8
- Username: nickcollison
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 27, 2009 12:45 pm
- Post datetime: 2009-11-03T10:00:13+00:00
- Post Title: NBA Live 10 - .FCD files

Didn't have any trouble, but thanks anyway. Always nice to have an up-to-date version.

Did anybody got anything out of that xarndat.pcd file? Could you extract the sound files?

From what I've gathered so far, each and every PA Announcer sound file is in there. I need a way to extract those sounds, and then, find out if they are playable right away, or if they need to be converted.
## Post #9
- Username: nickcollison
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 27, 2009 12:45 pm
- Post datetime: 2009-11-20T00:36:36+00:00
- Post Title: NBA Live 10 - .FCD files

> Reply from nickcollison
>
> 
Did anybody got anything out of that xarndat.pcd file? Could you extract the sound files?

Sorry, but that was incorrect. It's xarndat.FCD, not .pcd

Any news regarding this?
## Post #10
- Username: nickcollison
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 27, 2009 12:45 pm
- Post datetime: 2010-01-13T19:30:35+00:00
- Post Title: NBA Live 10 - .FCD files

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-13T20:37:40+00:00
- Post Title: NBA Live 10 - .FCD files

These files have XMA2 at offset 0xa0. Use xma_parse to extract them ([http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)):

```
xma_test embedded_00000800.fsb -o a0 -x out
```

then prepend a 22050 Hz mono header ([http://hcs64.com/files/header2_22050_mono.zip](http://hcs64.com/files/header2_22050_mono.zip)):

```
copy /b header2_22050_mono + out out.xma
```

then run the resulting out.xma through toWav:

```
towav out.xma
```

Note that 22050 Hz is not a valid XMA samplerate (I assume it's decoded with the 24000 Hz profile), but apparently that's what the fsb specifies.  I didn't listen to the resulting out.wav to see if the pitch was right.  The xma_parse step isn't necessary, you could just cut the first 0xa0 bytes off the file instead, but might be helpful as it checks everything out, I only tested the first few files.
## Post #12
- Username: nickcollison
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 27, 2009 12:45 pm
- Post datetime: 2010-01-13T21:21:48+00:00
- Post Title: NBA Live 10 - .FCD files

> Reply from hcs
>
> These files have XMA2 at offset 0xa0. Use xma_parse to extract them (http://hcs64.com/vgm_ripping.html):
Code: Select allxma_test embedded_00000800.fsb -o a0 -x out
then prepend a 22050 Hz mono header (http://hcs64.com/files/header2_22050_mono.zip):
Code: Select allcopy /b header2_22050_mono + out out.xma
then run the resulting out.xma through toWav:
Code: Select alltowav out.xma
Note that 22050 Hz is not a valid XMA samplerate (I assume it's decoded with the 24000 Hz profile), but apparently that's what the fsb specifies.  I didn't listen to the resulting out.wav to see if the pitch was right.  The xma_parse step isn't necessary, you could just cut the first 0xa0 bytes off the file instead, but might be helpful as it checks everything out, I only tested the first few files.

Thanks for your reply, but I got one problem. I'm assuming the ToWav Music Converter is the right program, is it correct? Because I'm not able to convert the out.xma file into .wav. When I enter:

towav out.xma

the response is:

access denied.

Up to that point, everything seems to work just fine. Am I doing something wrong?
## Post #13
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-13T22:07:18+00:00
- Post Title: NBA Live 10 - .FCD files

Hm, it is called the "ToWav Music Converter", but I've never seen an access denied error from it... Have you converted XMA with it before?
## Post #14
- Username: nickcollison
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 27, 2009 12:45 pm
- Post datetime: 2010-01-13T22:54:43+00:00
- Post Title: NBA Live 10 - .FCD files

No worries, I worked it out. I downloaded toWav from another place, and now it works.

In fact, if you use convall, the files are converted from .fsb to .wav directly, with almost any difference. The direct convertions are barely quicker (I'm fairly sure that's the 22050 to 24000 Hz correlation you mentioned), but apart from that, they are the same.

Thanks for your reply, it has been more than helpful.
## Post #15
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-13T23:24:48+00:00
- Post Title: NBA Live 10 - .FCD files

Heh, for whatever reason I completely forgot that ToWav supports fsb natively. Glad you got it worked out.
## Post #16
- Username: nickcollison
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 27, 2009 12:45 pm
- Post datetime: 2010-10-08T10:54:12+00:00
- Post Title: Re: NBA Live 10 - .FCD files

The contents of this post was deleted because of possible forum rules violation.
