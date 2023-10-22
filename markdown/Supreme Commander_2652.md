## Post #1
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2007-06-11T06:07:35+00:00
- Post Title: Supreme Commander

I'm hoping no one else posted this because I did searches and couldn't find any posts related to the file format or the game.  I'll post a zip file of the data file that was cut using Watto's Cutter.  
The game is Supreme Commander, the game data files are .scd   
They have numerous FMV videos but they are individual files if anyone is interested in converting them to a useable format as they are .sfd files. 
Sound archives are in a separate game data file format .xwb (the largest file sizes are these)  and .xsb (3kB or less) and then a .xgs totaling about 3k "SupCom.xgs"  (perhaps a master list of files packed in these formats?)

these are located in Supreme Commander\Sounds (and in subsequent folders):
.xwb (sound archive related)
.xsb  (sound archive related)
.xgs  (sound archive related)

these are located in Supreme Commander\gamedata:
.scd (other game data: textures, 3d models, scripts)

There is no official editor to this game and I've found some forums where people have talked about opening these formats to change the way the game plays but they don't talk about how they were able to get into the files in the first place.  I tried simply opening in winrar or changing the file extension to .rar or .zip and have had no luck.
[editor.scd.zip](https://xentaxbackup.github.io/file/1204_editor.scd.zip)
## Post #2
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2007-06-11T07:46:01+00:00
- Post Title: Supreme Commander

Here is one of the .xwb (this file was cut) archives for analysis, as well as an accompanying .xsb  (this is a full file)
[AmbientTest.xwb.zip](https://xentaxbackup.github.io/file/1205_AmbientTest.xwb.zip)
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-06-11T17:41:38+00:00
- Post Title: Supreme Commander

The sound files are XACT wave banks.
[http://en.wikipedia.org/wiki/XACT](http://en.wikipedia.org/wiki/XACT)

The XACT tool in the DirectX SDK didn't work for me I think. At least the header of the wave files was missing. So I modified unxwb a little bit (quick n dirty).
The batch file demonstrates how to extract the music.
VLC is able to play the extracted wav files (Winamp crashes). With the streaming assistent, you can convert it into other formats.
[unxwb.rar](https://xentaxbackup.github.io/file/1206_unxwb.rar)
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-06-11T17:43:13+00:00
- Post Title: Supreme Commander

The scd files are simple renamed zip files.
## Post #5
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2007-06-12T07:01:27+00:00
- Post Title: Supreme Commander

> Reply from Rheini
>
> The scd files are simple renamed zip files.
When I use the file extension .zip it says the file is corrupt, I even tried renaming the original files because the game works fine...  Not sure why I get that error.  Thanks for the info about XACT.  I just downloaded the DX SDK to install some Nvidia tools but hadn't had the chance to install yet.
## Post #6
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2007-06-12T07:04:34+00:00
- Post Title: Supreme Commander

Thanks a bunch!  I was able to successfully open the files after using the .zip extension on a completely different computer.  Don't know why I have that issue on my other computer...
## Post #7
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2007-07-22T17:50:46+00:00
- Post Title: Supreme Commander

According to Microsoft, the XACT audio tool will not open generated sound or wavebanks, it can only open project files used to compile the banks (ie: .xap).  However, they did mention a .h file that can be used to make your own code to parse the banks but they go on to say that you have to write the code yourself and that there is no documentation covering this area.
## Post #8
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2010-01-14T19:09:42+00:00
- Post Title: Supreme Commander

Thanks for posting that tool "unxwb"  It definitely extracts wave files but they are unusable!  I've tried renaming these to mp3 or any other type of compressed file as the music files in wave format are under 6 megs at most!  I know the music in the game is a lot longer than 30-40 seconds...  I'm wondering if there is a way to extract any of these audio sources?
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-14T19:47:49+00:00
- Post Title: Supreme Commander

try with the latest version of unxwb:
[http://aluigi.org/papers.htm#unxwb](http://aluigi.org/papers.htm#unxwb)

the file attached some threads before uses the microsoft adpcm codec which is not supported by winamp so you must use a better player like mplayer or ffmpeg or probably vlc.
the win32 built of mplayer is available on [http://oss.netfarm.it/mplayer-win32.php](http://oss.netfarm.it/mplayer-win32.php) (there is also the ffmpeg built, but remember that ffmpeg is a converter, not a player)
## Post #10
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2010-01-15T08:34:37+00:00
- Post Title: Supreme Commander

I see. I tried the latest build of the unxwb.  Still same issue though.  Even in Mplayer and yes if I can get ahold of FFmpeg I'll try it out,  I need to be able to open these files in a program like Sound Forge Pro 10.  I looked at the header information in the wav files being output and I get "RIFFŒ¿  WAVE"  yet none of my audio programs can seem to open it.  Typical wave files may have the headers reading "RIFFÀ:	 WAVE" or "RIFFp° WAVE" and of course my programs can open ADPCM wave files.  Not sure what's happening...
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-15T08:36:37+00:00
- Post Title: Supreme Commander

can you upload one of these extracted wave files?
just for our curiosity
## Post #12
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2010-01-16T04:55:56+00:00
- Post Title: Supreme Commander

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-16T11:57:46+00:00
- Post Title: Supreme Commander

it works perfectly with both mplayer and vlc: the sound is a wind
## Post #14
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2010-01-16T18:26:50+00:00
- Post Title: Supreme Commander

wierd.. perhaps i need to check out that converter ffmpeg.  I looked at my programs and they all support ADPCM but they don't recognize that header type.
