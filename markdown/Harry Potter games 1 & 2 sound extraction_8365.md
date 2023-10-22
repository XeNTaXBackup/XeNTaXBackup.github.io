## Post #1
- Username: x6herbius
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 03, 2011 6:00 pm
- Post datetime: 2012-02-21T14:54:33+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

I've been scouring the internet for multiple days trying to find a way to extract the .uax sound files from the first and/or second Harry Potter games but as of yet haven't had much luck. What I'm attempting to do is to is retrieve the various environmental sound effects from either of the games; my preference would be the Chamber of Secrets game but my CD for that has a nasty scratch on the topside and won't install. Good news is copies are cheap as dirt on Amazon nowadays, but until that arrives I have the Chamber of Secrets demo to work with, whose only audio file (not music file, they're .oggs and they're fine) is called AllDialog.usa_uax. I also have the CD for the first game, which has multiple .uax files, but I'd prefer the sounds from the second game because they seem to be of better quality and there are a lot of elements in the second game that weren't present in the first.

This is what I know so far:

- Both games were built on the Unreal 1.0 engine, according to Wikipedia. I have downloaded the Unreal 2.0 runtime (can't find the 1.0 runtime anywhere) but the sound extractor crashes on a large percentage of the HP1 files, and also on the sizeable HP2 file. The latest UDK doesn't recognise .uax files as far as I can see.

- Winamp can play some of the .uax files from the first game, but refuses to play the AllDialog file from the second. The files are comprised of lots of sounds stacked one after another.

- Importing raw data into audacity reveals the sound waves, sped up and interspersed with large amounts of static.

- Game extractor ([http://watto.org/extract](http://watto.org/extract)) can see the individual files inside the .uax files, but when I right-click and choose "extract files" it says "Files extracted!" but gives no indication of where they are. As far as I can tell the sounds should be extracted to the same directory as the .uax but there are none to be seen. Coupled with a log file that contains a lot of "ERROR: java.lang.NullPointerException ... ERROR: java.lang.ArrayIndexOutOfBoundsException: 2048 ... ERROR: java.io.FileNotFoundException: C:\Program Files\EA GAMES\Harry Potter TM\Sounds\s_kit_loop\Ambient\S_GEN_torch2.Sound", I'm suspecting the extractor is unable to actually extract the files.

- This is what the beginning of the AllDialog.usa_uax file looks like:



Any info on what to do next would be much appreciated.
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-03-05T09:59:12+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

.UAX, as with most Unreal files, is a standard Unreal Engine archive. Have you tried opening it up with the UT99/Unreal Gold Editor? And as far as I know, the audio files used in the early Potter PC games by KnowWonder used Bink audio for dialogue. Not sure in the first two, but Azkaban and the PC version of Lemony Snicket made use of such a system.
## Post #3
- Username: x6herbius
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 03, 2011 6:00 pm
- Post datetime: 2012-03-05T15:45:22+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

I've since found that the HPSounds.c file in the system folder of the game contains a lot of the general game noises (ie. jump sounds, pickup sounds, etc.) as wave files, and Dragon Unpacker's HyperRipper can look through it and identify the wave files from the RIFF header, but after listening to all the wave files there still seem to be a lot of sounds unaccounted for. It's possible that they may be binks, then, but I'm not familiar with that file format.
## Post #4
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-03-07T11:13:44+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

> Reply from x6herbius
>
> I've since found that the HPSounds.c file in the system folder of the game contains a lot of the general game noises (ie. jump sounds, pickup sounds, etc.) as wave files, and Dragon Unpacker's HyperRipper can look through it and identify the wave files from the RIFF header, but after listening to all the wave files there still seem to be a lot of sounds unaccounted for. It's possible that they may be binks, then, but I'm not familiar with that file format.

Try using RAD Video Tools.
## Post #5
- Username: x6herbius
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 03, 2011 6:00 pm
- Post datetime: 2012-03-07T17:12:28+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

> Reply from huckleberrypie
>
> Try using RAD Video Tools.

Doesn't seem to like the .uax file.
## Post #6
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2015-09-10T16:46:34+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

Where is the music archive and how to extract?
## Post #7
- Username: x6herbius
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 03, 2011 6:00 pm
- Post datetime: 2015-09-10T17:21:13+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

The music archive should just be within the music subfolder. In one of the games I think the music is all in OGG format (in which case VLC player will play them no problem), and in another they're UAX files. I'm not sure how I originally extracted them but I'm sure there are some game media players out there that will handle them.
## Post #8
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2015-09-10T18:08:03+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

I'm talking Chamber of Secrets and Prisoner of Azkaban, specifically. And which UAX file?
## Post #9
- Username: x6herbius
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 03, 2011 6:00 pm
- Post datetime: 2015-09-11T06:24:06+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

The Chamber of Secrets I think uses OGGs, but I'm not sure about the Prisoner of Azkaban. Try opening some archives with Dragon Unpacker. The root folder is Program Files (x86)/EA Games/Harry Potter <and something>/game if I remember correctly, so have a look in some of the sub-folders for archives. They might be .uax files or .u files.
## Post #10
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2015-09-11T19:50:52+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

If I just put the PS2 disc in the computer, would I find it?
## Post #11
- Username: x6herbius
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jun 03, 2011 6:00 pm
- Post datetime: 2015-09-11T19:54:18+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

I have absolutely no experience with the PS2 version, I'm afraid. I've only messed around with the Windows games.
## Post #12
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2015-09-11T20:02:18+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

They're usually the same, so I'll just try DU like you said.
## Post #13
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2015-09-12T18:23:05+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

In the SOUND.BIG file, I've got .sdt, .mpf, .mus, and .map files. I do not know which one contains the music you speak of.
## Post #14
- Username: Cameron007
- Rank: advanced
- Number of posts: 48
- Joined date: Thu Aug 06, 2015 7:12 pm
- Post datetime: 2015-09-12T19:47:58+00:00
- Post Title: Harry Potter games 1 & 2 sound extraction

Okay, I was finally able to extract the .mus files, but now don't know how to convert all the .asf files. Here's one:

[https://mega.nz/#!clM1zSRK!MSHvvIH_PhDk ... -YWkTf9Qx4](https://mega.nz/#!clM1zSRK!MSHvvIH_PhDkh-z6EC8c6UQuUN-U8eGC8-YWkTf9Qx4)
