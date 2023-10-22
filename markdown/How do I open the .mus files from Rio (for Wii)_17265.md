## Post #1
- Username: Mickyelloow
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 08, 2017 8:59 am
- Post datetime: 2017-11-08T03:00:43+00:00
- Post Title: How do I open the .mus files from Rio (for Wii)???

After many, many, MANY research, tests and failures, I give up. I've searched around Google for almost a whole week to try and figure this out, but it seems for me that the .mus files in the Rio (for Wii) game's files are very unique. VGSC didn't work, Winamp with vgsm could not read the files as well as Finale Notepad, MFAudio doesn't recognise the files and there are many more softwares that didn't work and/or are junkware (I can't even count them).

I am so desperate to find how (and even IF) I can open those files. If not, it's not a big deal. But I would really like an answer to this burning question stuck in my head.

If I can open them, I would like to be able to convert them from .mus to a more conventional format (like .wav or .mp3) and be able to create .mus files from custom music with the same settings of the original files (in other words, rebuild the .mus files from mp3, wav or any other conventional format with custom sounds).

Since I am worried with copyrights, I won't host the file(s) I want to open. At least, with how far I got, I can give you a step by step on how to extract the .mus files of Rio for Wii, since this ISO is particular to extract and that information about this is extremely rare (the only topic I found about this is on this website):
   1- It is important to check if you have Rio for Wii on a legitimate CD first. Else, you could be in big legal trouble by proceeding with the ISO process. If you do not have the legitimate CD, DO NOT CONTINUE.
   2- Get Rio's game's ISO for wii (from the CD or from the internet if, like I said earlier, you have the legitimate CD)
   3- Extract it with an ISO extractor and use QuickBMS with [this bms script (clic here to download)](http://aluigi.altervista.org/bms/rio.bms) to extract the .000 files in the DATA folder (the ones that are combined with .bin files. thanks to [this post](http://forum.xentax.com/viewtopic.php?f=10&t=8026) that originally found how to extract those .000 files). I recommend you only extract FILE_COM.000 since it contains the main sounds (I think since I can't open them).
   4- You will see all the .mus files mixed in the folder you extracted the .000 (except if you extracted filelist.000 that contains no .mus files). THOSE are the one I want to open, convert and even edit if possible.

I'm doing this only to put my own soundtrack and/or voice acting and be able to play the custom game on Dolphin. I also want to put custom cinematics. At least, those are thp files, so I can edit them pretty easily (even if the resolution of them are 640x448 and not 640x480 like many other games. If you want to help me about that, [check my post here](http://forum.xentax.com/viewtopic.php?f=36&t=17280)).

By the way, I am pretty new to game file extraction, so I don't know much about some things. I've learned during my research though. But it wasn't enough for me to be able to open those .mus files... I just hope to get an answer soon...
## Post #2
- Username: Mickyelloow
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 08, 2017 8:59 am
- Post datetime: 2018-05-27T05:33:09+00:00
- Post Title: How do I open the .mus files from Rio (for Wii)???

Still no reply after right about 6 months..... seems like what I expected.

I had a lot of things happening in my life since and I wasn't able to continue my expedition trough this rabbit hole that I call the ".mus" hole. Now, I've been able to search a bit more..... and I've made some progress.

I was (FINALLY) able to read some of the .mus files using Audacity by importing RAW. Bad news: only a couple of them are readable that way and they are all inside the "FILE_USA" folder. If I use a specific set of settings (that I can't really tell since they vary except for the PCM encoding), some are crystal clear, others are a messy pile of noise with some gibberish voices behind. I've tried most the others without success (including most of the other folders). Though, in the "FILE_COM" folder, I faintly hear the rhythm of the songs (for example, the "00000074.mus" file contains the song you can hear during the "Music Mayhem" mini-game)

As of right now, I am on the right track for the extraction. On the other hand, I fear the re-export of the .mus I want to do with custom sounds. If anyone, but ANYONE, have a part of the answer that I could try out, please share it here. I am still looking regularly on this post to see if someone replied.
## Post #3
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-05-28T03:31:05+00:00
- Post Title: How do I open the .mus files from Rio (for Wii)???

> Reply from Mickyelloow
>
> Still no reply after right about 6 months..... seems like what I expected.

I had a lot of things happening in my life since and I wasn't able to continue my expedition trough this rabbit hole that I call the ".mus" hole. Now, I've been able to search a bit more..... and I've made some progress.

I was (FINALLY) able to read some of the .mus files using Audacity by importing RAW. Bad news: only a couple of them are readable that way and they are all inside the "FILE_USA" folder. If I use a specific set of settings (that I can't really tell since they vary except for the PCM encoding), some are crystal clear, others are a messy pile of noise with some gibberish voices behind. I've tried most the others without success (including most of the other folders). Though, in the "FILE_COM" folder, I faintly hear the rhythm of the songs (for example, the "00000074.mus" file contains the song you can hear during the "Music Mayhem" mini-game)

As of right now, I am on the right track for the extraction. On the other hand, I fear the re-export of the .mus I want to do with custom sounds. If anyone, but ANYONE, have a part of the answer that I could try out, please share it here. I am still looking regularly on this post to see if someone replied.

If it's by Eurocom, you and I have a lot in common, I want to extract the .SFX files from Robots: [https://drive.google.com/open?id=1drSCL ... TQnguUTmLz](https://drive.google.com/open?id=1drSCL6cMCLUE4Q6KjsDJc8TQnguUTmLz)
