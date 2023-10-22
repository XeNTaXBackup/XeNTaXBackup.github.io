## Post #1
- Username: Jinzor
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Feb 06, 2010 4:45 am
- Post datetime: 2016-02-22T16:56:25+00:00
- Post Title: Rome II - Movie Audio .WEM

Hi there,

I'm trying to figure out how to export a .wem file from Wwise to the same type as the one included below. This .wem file plays once a .bik movie file has triggered (for the Caesar in Gaul introduction .bik video specifically). When I also tried to convert it using ww2ogg.exe + revorb.exe, it gives off an error message stating:

> Parse error: expected 0x42 fmt if vorb missing

Would anyone know what's different about it, and maybe even how I would convert it (save me time)? If I manage to replace this file with my own and have it actually play the audio when the .bik file triggers, then I may have finally figured out a way to get custom .bik files to play with custom audio in Rome II - could be a massive potential for mod making there (and audio .wems have always been the issue, not the movie .bik file).

.WEM File Link:
[http://www.mediafire.com/download/ywmnc ... 385186.wem](http://www.mediafire.com/download/ywmncab0rpbg99d/684385186.wem)

Thanks,

Jin
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-02-29T20:18:38+00:00
- Post Title: Rome II - Movie Audio .WEM

This is VERY easy.

This file is plain uncompressed PCM file. You can easily make such file with wwise, if you choose "PCM" type of compression (which means not compressed).
## Post #3
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2016-03-01T02:52:51+00:00
- Post Title: Rome II - Movie Audio .WEM

[viewtopic.php?p=113253#p113253](http://forum.xentax.com/viewtopic.php?p=113253#p113253)
## Post #4
- Username: Jinzor
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Feb 06, 2010 4:45 am
- Post datetime: 2016-03-02T22:05:37+00:00
- Post Title: Rome II - Movie Audio .WEM

Hey guys, thanks for the replies.

I tried converting it to PCM just now. To test whether or not I'd done it right, I tried to convert the .WEM file i'd just made and it gave off the same error (woohoo!). However, when I replace the audio file in the "music_en_shared_rome2.pack" to replace the .WEM file that is meant to be triggered to play when this specific .bik movie plays, the audio still doesn't play when I test it ingame. I've got a feeling it's impossible, or I've missed a step (for the record - I don't know anything about Wwise, I'm only using this thing because I seemingly have to in order to get any audio modding done with this game - I'm more about creating 3D art assets / animations). Perhaps I need an event trigger? If so, I wouldn't know what the name of that trigger should be since I don't think I can go in and find it myself. I'd need to contact the developers (like what the Total War community did with their "Rome: Total War - Soundtrack" mod, which replaced the Rome II soundtrack with Rome's - they had an inside contact who helped them make the mod I think).
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-03T15:51:13+00:00
- Post Title: Rome II - Movie Audio .WEM

> Reply from Jinzor
>
> I've got a feeling it's impossible

I repeat: this is very easy. The file is not even encoded or compressed. This is PCM file. Don't try decoding it with ww2ogg, because it's not encoded.

How did you make a new file? What options did you use? Original was stereo, 44khz, 16 bit.
## Post #6
- Username: Jinzor
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Feb 06, 2010 4:45 am
- Post datetime: 2016-03-06T21:32:21+00:00
- Post Title: Rome II - Movie Audio .WEM

> Reply from daemon1
>
> How did you make a new file? What options did you use? Original was stereo, 44khz, 16 bit.

I imported my audio file into a default work unit, clicked on the imported file, went to the "Source Settings" tab, clicked on "Edit..." in the "Conversion Settings" box, set the format to "PCM" + the SR to "44100" and then converted it.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-07T06:51:06+00:00
- Post Title: Rome II - Movie Audio .WEM

> Reply from Jinzor
>
> daemon1 wrote:How did you make a new file? What options did you use? Original was stereo, 44khz, 16 bit.

I imported my audio file into a default work unit, clicked on the imported file, went to the "Source Settings" tab, clicked on "Edit..." in the "Conversion Settings" box, set the format to "PCM" + the SR to "44100" and then converted it.

hmm. It must work. Can you send me the file you got after that?
## Post #8
- Username: Jinzor
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Feb 06, 2010 4:45 am
- Post datetime: 2016-03-07T21:46:35+00:00
- Post Title: Rome II - Movie Audio .WEM

Sure, here's the download link to the file:

[http://www.mediafire.com/download/6ovrr ... 86_new.wem](http://www.mediafire.com/download/6ovrr4s270ruue1/684385186_new.wem)
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-08T06:33:57+00:00
- Post Title: Rome II - Movie Audio .WEM

The files are absolutely identical. If this file doesn't work, this means something's wrong with the way you put it back into the game.
