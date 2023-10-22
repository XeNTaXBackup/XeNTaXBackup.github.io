## Post #1
- Username: blbltheworm
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 13, 2005 9:01 pm
- Post datetime: 2005-09-27T18:21:42+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

Hi together,
I plaied Broken Sword 3 - the Sleepe Dragon and if I have finished the game I had heard this nice Song "Love Us" by "We Love You". I tried to find it on the Intenet, I tried to extract the "data.pak" with DragonUnpacker/GameExtractor I searched for tools or a wikidescription, but I hardly haven't found anything.
I also found a file named "glob_credits.rws" maybe the Song is inside this 14MB big file or the "data.pak", I don't know.

I don't know how to find and extract the song. Can somebody help me??
Do anybody know a Tool to extract the music of Broken Sword 3??
## Post #2
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2005-09-27T19:54:29+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

> Reply from blbltheworm
>
> I also found a file named "glob_credits.rws"
That rws-file might be a raw wav-file (no wav header included). Perhaps some music-player will be able to play it.. Otherwise, you can try encoding it to ogg and then decode it back to wav.

Download [http://www.crsn.com/hc/ff/oggvorbis/vor ... -win32.zip](http://www.crsn.com/hc/ff/oggvorbis/vorbis-tools-1.0.1-win32.zip)
Unzip and put oggenc.exe and oggdec.exe in the same directory as "glob_credits.rws". Run cmd, change directory to the correct directory. Enter:

```
oggdec glob_credits.ogg
```

Try to play glob_credits.wav now!
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2005-09-28T04:17:35+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

The problem is extracting it in the first place.

But maybe if you provided an example of this PAK file or a link to the demo?
## Post #4
- Username: blbltheworm
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 13, 2005 9:01 pm
- Post datetime: 2005-09-28T15:47:56+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

Well this file is no raw wave-file. Converting with oggenc faild.
I also tried to open it with GoldWave and tried every possible raw-type, but there is no right one.

@Darkfox you wanted to have a link to a Demo-Version. Here is one:
[http://www.ferrago.com/downloads/file/283](http://www.ferrago.com/downloads/file/283)

good luck,
  blbltheworm
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2005-09-28T23:21:57+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

You were able to extract the file? But I thought you said you could not extract anything?
## Post #6
- Username: blbltheworm
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 13, 2005 9:01 pm
- Post datetime: 2005-09-29T10:07:47+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

No no, I didn't extract this file.
There is one big "data.pak" file with 751.3 MB and there is a folder named "data\streams" where you can find a file many *.rws-files and one of them is named "glob_credits.rws" which has 14.9 MB.
I don't know in which file I can find the music and hoped somebody can tell me in which the music is and how I can extract it.
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-29T13:57:50+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

Hi mate,

Could you please send us some pieces or the archives to look at. You can use our File Cutter tool from [http://www.watto.org/extract/download/cutter.zip](http://www.watto.org/extract/download/cutter.zip) to do the job - just run the program, choose the archive, and click the OK button. This will create a zip with some pieces of the archive in it - then you just have to attach them to the forums here or email them to us. It will probably be the most use to look at the *.pak file, but if you want we can have a look at the other files too.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-09-30T15:53:53+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

hello

you can unpack *.pak file with tools below
## Post #9
- Username: blbltheworm
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 13, 2005 9:01 pm
- Post datetime: 2005-09-30T20:36:08+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

Oh, great.
I'll try this tool.
I'll tell you if it doesn't work    .

If it works thanks a lot.
## Post #10
- Username: blbltheworm
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 13, 2005 9:01 pm
- Post datetime: 2005-09-30T21:37:24+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

OK, I extracted all the files.
There were many *.bmp with the textures and some *.txt with the subtitles.
The rest (over 30 000 files!!) are *.dat and 45 of them are bigger than 1 MB.
Most of this files could be identified as *.ogg, but 8 of them are no *.ogg.
I don't know what format they have and what they store.

Or is the music stored in another file??
## Post #11
- Username: blbltheworm
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jun 13, 2005 9:01 pm
- Post datetime: 2005-10-01T08:08:01+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

> Reply from blbltheworm
>
> 
Most of this files could be identified as *.ogg

I'm sorry but these files are no *.ogg-Files these files are regular Wave-files with the sfx.
## Post #12
- Username: SilentHill
- Rank: VIP member
- Number of posts: 16
- Joined date: Sun Feb 05, 2006 6:18 pm
- Post datetime: 2006-03-13T07:03:56+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

Could you manage to figure out what program the *.rws files can be opened with?

I'd like to find the speeches, but up to now I had no luck.

I unpacked the data.pak files but all I found was text files, voices, and textures.
## Post #13
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-24T09:22:08+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

As I am constantly trying to get more threads from the "Research" section to the "Completed" section, I am now bumping this thread more than a full year after its last post. 

A tool to extract the audio tracks out of the Broken Sword 3 RWS files can be found [here](http://oezmen.eu/gameresources/). I will see to add the specifications to the Wiki as soon as possible.
## Post #14
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-25T01:36:04+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

[As promised](http://wiki.xentax.com/index.php/Broken_Sword_-_The_Sleeping_Dragon_RWS). Whoever designed that format was either a genius or a madman. But probably both.

Proofreaders are welcome ...
## Post #15
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-25T01:52:20+00:00
- Post Title: Broken Sword 3 (Baphomets Fluch 3) Musicextractor

What i can say?   amazing!!!

PS: is not like fsb, xbw and similars? i mind fsb it's ima-adpcm without header and xbw it's xboxadpcm with some zlib (i remember this) and both are multitrack
## Post #16
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-25T09:56:43+00:00
- Post Title: 

I have not looked into XWB and FSB before, so I cannot tell for sure, but from what I have just read, none of these format matches the header structure found in the RWS files. It might still be based on these, there are many unknown fields left ...

You are right, however, that there is at least one similarity: The sample data uses the same organization as the XBOX ADPCM codec (36 bytes per channel including header, sample codes organized in 4 byte blocks etc. pp.). That would make sense, I guess, since the game was also published for the XBOX platform. Yet I do not know whether or not the same file types were used in that port.
## Post #17
- Username: swathack
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Mar 21, 2021 10:13 pm
- Post datetime: 2021-11-11T18:08:52+00:00
- Post Title: 

> Reply from sajad ↑Fri Sep 30, 2005 11:53 pm at Fri Sep 30, 2005 11:53 pm
>
> 
hello

you can unpack *.pak file with tools below

where is the tools
## Post #18
- Username: srcs34k
- Rank: n00b
- Number of posts: 14
- Joined date: Wed May 23, 2012 11:45 pm
- Post datetime: 2022-06-25T19:42:01+00:00
- Post Title: 

[http://www.ctpax-x.org/?goto=files&show=57](http://www.ctpax-x.org/?goto=files&show=57)
this tool work, only for music, not for voice
