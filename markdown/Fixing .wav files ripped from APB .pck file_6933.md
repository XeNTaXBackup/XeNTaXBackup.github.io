## Post #1
- Username: Rapid99
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 05, 2011 5:13 am
- Post datetime: 2011-07-07T23:58:40+00:00
- Post Title: Fixing .wav files ripped from APB .pck file

Hello there my friends.
I come in need of assistance! So here's the story.

I've been trying to rip the sounds from APB for the past few days. I'm a bit new to the whole audio ripping deal and i've run into a bit of a snag.
The files for the game's audio are contained in .pck files. I managed to rip the files from the .pcks (at first with Ravioli Game Tools, which pulled me 622 .wav files. After downloading and using NovaSoft, I actually managed to pull 935 .wav files)

The problem is, the .wav files are unplayable. After reading around online, mostly in past threads here, it appears that they need to be made into .ogg files using ww2ogg in order to make them into playable audio files.
My issue is this: i'm not too familiar with ww2ogg, and when I try to convert the .wav files into .ogg files, it gives me a parse error.
To be more specific, "Parse error: expected fmt, vorb, data chunks"

When I read around more, it looks more so like ww2ogg takes in .RIFF files and uses THOSE to make the .ogg
The .pcks with the .wav audio files contained nothing but .wavs, and i'm not sure where I would find said .RIFF files if that is, in fact, what I need.

Any help would be GREATLY appreciated. I've been slaving over this for a few days now with no luck, and the fact that I have the files, but just can't play them, makes it rather aggravating. It's almost like the files are taunting me, lol
And again, i'm a bit new to this, so the more explanation the better.

Thanks all,
-Rapid99
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-07-08T05:22:10+00:00
- Post Title: Fixing .wav files ripped from APB .pck file

They seem to have figured it out in [this thread](http://forum.xentax.com/viewtopic.php?f=17&t=6299&p=51705).

Though I should note that you don't need to rename the files .RIFF, ww2ogg doesn't care what the extension is.
## Post #3
- Username: Rapid99
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 05, 2011 5:13 am
- Post datetime: 2011-07-08T06:57:48+00:00
- Post Title: Fixing .wav files ripped from APB .pck file

That was one of the first threads i've tried following :/
For one reason or another, when I try to do the conversion, it gives me an error.

Example of what's happening:

ww2ogg SFX01.wav -o SFX01.ogg --full-setup
Input: SFX01.wav
Parse error: expected fmt, vorb, data chunks


It just gives me a parse error and nothing happens. 


I have the .wav files in the folder;
I have the batch file in the folder, properly set up (when I run it in a command prompt, it properly tries to convert every .wav file... and everyone one of them fails and gives the parse error);
I have ww2ogg.exe in the folder;
and I have packed_codebooks.bin in the folder;

Just as it says in the thread. There are also a number of other files in the folder that came with ww2ogg.
It just seems like it's that parse error, whatever it may mean.
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-07-08T15:40:57+00:00
- Post Title: Fixing .wav files ripped from APB .pck file

If you could post one I could take a look, but the error suggests that this file is not vorbis.
## Post #5
- Username: Rapid99
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 05, 2011 5:13 am
- Post datetime: 2011-07-08T17:25:20+00:00
- Post Title: Fixing .wav files ripped from APB .pck file

> Reply from hcs
>
> If you could post one I could take a look, but the error suggests that this file is not vorbis.
Thanks a lot 
Hopefully there's something I could end up doing...
[StreamedSFX.rar](https://xentaxbackup.github.io/file/4456_StreamedSFX.rar)
## Post #6
- Username: Rapid99
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 05, 2011 5:13 am
- Post datetime: 2011-07-17T03:34:38+00:00
- Post Title: Fixing .wav files ripped from APB .pck file

No luck I assume?
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-07-25T02:10:08+00:00
- Post Title: Fixing .wav files ripped from APB .pck file

That particular file at least is now supported in ww2ogg 0.13.
