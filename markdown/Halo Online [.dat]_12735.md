## Post #1
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-04-01T17:21:28+00:00
- Post Title: Halo Online [.dat]

Hi guys, I was wondering if anyone would help me in getting these .dat files from Halo Online unpacked. the game uses a mixture of .Map and .Dat files. Typically the .map archives would contain all of the games resources, however Saber Interactive decided to mix this all up by making the .map files a cache for the .dat files. 

What i'm honestly after is the sound effects in the game, so far digging through the hex I've been unable to figure out what type of format the audio may be in which has lead me here to first crack the .dat archive. 

Here is a screenshot of the audio.dat hex, here is a small sample also.  

[http://i.imgur.com/Pnp7Ukq.png](http://i.imgur.com/Pnp7Ukq.png)
[dat sample.zip](https://xentaxbackup.github.io/file/8919_dat sample.zip)
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-04-02T08:21:26+00:00
- Post Title: Halo Online [.dat]

Its compressed

32byte header followed by compressed chunk data
00 00 00 00 E0 65 DC 11 01 07 00 00 00 00 00 00
1B 93 92 CC 1B 63 D0 01 00 00 00 00 00 00 00 00

-edit-
ill see what else i can dig up shortly

```
{
    uint32  blankMagic;
    uint32  dTOC_ptr;
    uint32  dTOC_entryCount;
    uint32  unkVarA;
} datHeader;

typedef struct
{
    uint32  toc_entryPtr;
} toc_entry;

typedef struct
{
    local int i;
    for(i = 0; i < f_header.dTOC_entryCount; i++)
    {
        toc_entry   entry;
    }
} datTOC;

```


Toc is at the bottom of the file for audio.dat its at DEC (299656672)
toc = table of content


k got em fsb banks dat tool coming soon
## Post #3
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-04-03T10:48:37+00:00
- Post Title: Halo Online [.dat]

Crude release for quick unpack
[http://dev.cra0kalo.com/?p=315](http://dev.cra0kalo.com/?p=315)
## Post #4
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-04-03T16:39:14+00:00
- Post Title: Halo Online [.dat]

You are a scholar and a saint my friend THANK YOU! Ill be waiting for that FSB tool!
## Post #5
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-04-05T04:12:42+00:00
- Post Title: Halo Online [.dat]

I've been looking though the dat chuck files since yesterday but something eludes me. Are the FSB files still compressed? I thought until the tool was release I might be able to convert sounds the hard way by hex searching, but upon scanning through the files... I can't seem to find the FSB hex tag normally seen in FSB archives.
## Post #6
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-04-05T04:31:23+00:00
- Post Title: Halo Online [.dat]

> Reply from durandal217
>
> I've been looking though the dat chuck files since yesterday but something eludes me. Are the FSB files still compressed? I thought until the tool was release I might be able to convert sounds the hard way by hex searching, but upon scanning through the files... I can't seem to find the FSB hex tag normally seen in FSB archives.

If you extract audio.dat there are FSB files in there just open the outputted .dat files in a hex editor u will see a FSB signature at the top
## Post #7
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-04-06T03:18:35+00:00
- Post Title: Halo Online [.dat]

Thank for that, I found them, however I've gone through all 1700 files from audio.dat and I've only found less then a quarter of FSB files. It doesn't seem like everything is there, is there perhaps another format i'm missing, or could the rest of the sound files be in resources.dat?
## Post #8
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2015-04-06T04:00:00+00:00
- Post Title: Halo Online [.dat]

No they are there just there is another layer of compression ontop of that will have a look later this week.

notice the 0xFF in all the files


It's prob lzma or xmem or something
## Post #9
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-04-15T16:46:42+00:00
- Post Title: Halo Online [.dat]

Hello just wondering if there has been any progress on the tools yet?
## Post #10
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2015-04-16T21:09:55+00:00
- Post Title: Halo Online [.dat]

Alot of the files that arent fsb are mpeg (v1, not mp3) audio, rename .mpg and open in almost anything

[http://i.imgur.com/D6PnrVi.jpg](http://i.imgur.com/D6PnrVi.jpg)

infact, seems to be one of the standard fsb audio format compression used, but without fsb header.
## Post #11
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-04-17T05:02:49+00:00
- Post Title: Halo Online [.dat]

WOW. I can't believe I missed that thanks Pepper.
## Post #12
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2015-04-17T23:30:14+00:00
- Post Title: Halo Online [.dat]

> Reply from durandal217
>
> WOW. I can't believe I missed that thanks Pepper.

yup. one of the reasons I always just try to import as raw data and see if it looks right-ish. It's an easy step to not do, because almost all common audio files have a legible header. RIFF, VORBIS, LAME, etc. but when I dragged it into goldwave to test as rawdata it just instantly recognized it without even asking for playback rate and etc
