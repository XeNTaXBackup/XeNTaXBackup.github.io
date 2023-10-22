## Post #1
- Username: Cmdr
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 05, 2013 10:06 pm
- Post datetime: 2013-07-05T20:38:00+00:00
- Post Title: Eve Online and ogg/wav

Hello,

I would like to unzip eve online's sound/voice files, but revorb.exe fails every time I try to run it. 
I am aware that this topic has been covered often in this forum, so here are the steps I've already taken in order to get where I am now:
1. I unpacked Eve's voice.bnk-files using bnkextr.exe
2. I ran wave2ogg.exe with the "packed_codebooks_aoTuV_603.bin" through the command line.
3. I tried to run revorb, however the program crashes all the time.

I followed the steps in this threat: [viewtopic.php?p=85044#p85044](http://forum.xentax.com/viewtopic.php?p=85044#p85044)
These are the files I used: [https://www.dropbox.com/sh/titfwocclsxxkwj/KbL3KLDLpn](https://www.dropbox.com/sh/titfwocclsxxkwj/KbL3KLDLpn)

I've got to admit that I not familiar with this sort of "sorcery" at all, so I tried to find whatever I can in order to make it work. 
Can anyone help me please?

Thank you very much for your help in advance.
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-07-07T23:59:43+00:00
- Post Title: Eve Online and ogg/wav

Normally revorb crashing means the previous step was done wrong, I'm not familiar with the game in particular, but it seems like the commandline is the problem for starters, you shouldn't be typing out the path to the codebooks, it should literally just all be in the same directory, and then you add "--pcb packed_codebooks_aoTuV_603.bin" it's a nice bat file, but ww2ogg is literally just expecting a string of a codebook name, which it then finds in it's own path.
## Post #3
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2013-07-15T12:26:27+00:00
- Post Title: Eve Online and ogg/wav

You don't need the new packed_codebooks_aoTuV_603.bin for Eve, ww2ogg 0.19 works fine on this file with the old packed_codebooks.bin. Just change that name in your .bat and it should work.

ww2ogg is very lazy about trying to open the codebook, if it doesn't find packed_codebooks.bin in the working directory it won't find it, so specifying the full path in --pcb can sometimes be helpful.
## Post #4
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-07-27T16:42:27+00:00
- Post Title: Eve Online and ogg/wav

I was wondering if somebody could help me out, because I'm sorta stumped on this one. I've extracted and converted most of the sounds from eve already, however when I try to convert the turret sounds, only some of them convert from wav to ogg. When I try to convert a single turret sound (turrets.005.wav for example) ww2ogg gives me a parse error unknown chunk type and won't convert it. 

Can anyone tell me what I'm doing wrong? and how to properly convert these files.
## Post #5
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-07-30T04:57:18+00:00
- Post Title: Eve Online and ogg/wav

Upon further inspection, I think most of the turret sounds use Wwise ADPCM encoding, question is what do I use to convert it? Everything I tried didn't work.

Here is a sample if it helps. [http://www.mediafire.com/?zdx3l6yua61gwp4](http://www.mediafire.com/?zdx3l6yua61gwp4)

I appreciate any help.
## Post #6
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-07-30T18:04:16+00:00
- Post Title: Eve Online and ogg/wav

hcs has a tool called ima rejigger, or something like that. I cant find the default version but here's one that works with payday's ima adpcm which also used ww2ogg for most of it's other audio (voices) hcs64.com/files/ima_rejigger2.zip see if this works?

edit- worked on the linked file for me! sounds like fizzing cannons and fireworks-ish noise.
## Post #7
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-07-30T18:34:23+00:00
- Post Title: Eve Online and ogg/wav

> Reply from Pepper
>
> hcs has a tool called ima rejigger, or something like that. I cant find the default version but here's one that works with payday's ima adpcm which also used ww2ogg for most of it's other audio (voices) hcs64.com/files/ima_rejigger2.zip see if this works?

edit- worked on the linked file for me! sounds like fizzing cannons and fireworks-ish noise.

EDIT: Never mind I got it working thank you so much pepper I really appreciate it.

For anybody who comes across this thread looking to convert ADPCM .wav sounds from EVE: 
once you drop the wav file into ima_rejigger2, just open up audacity, make sure you have the FFmpeg import/export library installed and do file > import > audio in the drop down box select FFmpeg-compatible files and simply load the .wav you want import it and you should now have a playable file.
