## Post #1
- Username: NLA
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 22, 2006 2:36 am
- Post datetime: 2006-07-02T01:48:38+00:00
- Post Title: Breakdown

Sometime early this morning to late this afternoon I found out several interesting things about this game, Breakdown, for the XBOX. To begin with, I'm very confused as to why no one has paid any attention to extracting things from this game. In terms of the archives that hold the sounds/music/voices, there are three - se.stw, bgm.stw, and voice.stw, with their respective external .sth directory files. Below are 250 KB cut versions of se/bgm/voice stw archives and their adjacent .sth name files.

EDIT: The .stw archives can be extracted with Nova Software Extractor, and can be listened to with various multi-media players after installing a special audio codec on the internet.

EDIT2: Updated.

bgm.sth:
[http://nesslookalike.googlepages.com/bgm.sth.zip](http://nesslookalike.googlepages.com/bgm.sth.zip)

bgm.stw:
[http://nesslookalike.googlepages.com/bgm.stw.zip](http://nesslookalike.googlepages.com/bgm.stw.zip)

se.sth:
[http://nesslookalike.googlepages.com/se.sth.zip](http://nesslookalike.googlepages.com/se.sth.zip)

se.stw:
[http://nesslookalike.googlepages.com/se.stw.zip](http://nesslookalike.googlepages.com/se.stw.zip)

voice.sth:
[http://nesslookalike.googlepages.com/voice.sth.zip](http://nesslookalike.googlepages.com/voice.sth.zip)

voice.stw:
[http://nesslookalike.googlepages.com/voice.stw.zip](http://nesslookalike.googlepages.com/voice.stw.zip)

After examining the internal workings of the .sth files, I can see that these are all the background, sound effect, and voice tracks of the whole game, complete with names.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-07-02T22:35:49+00:00
- Post Title: Breakdown

Sorry for the late response, but other chores are taking up all of my time. 

See [http://www.xentax.com/?p=90](http://www.xentax.com/?p=90)

But when I'm done with that, I will go through the requests and check if I can help out.
## Post #3
- Username: NLA
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 22, 2006 2:36 am
- Post datetime: 2006-07-05T21:00:22+00:00
- Post Title: Breakdown

*bump*

Just kidding, I actually do have a reason to post, not just to bump it.

Using Microsoft Excel, I created a .bat file to use with that program, "xbadpdec", so that the extraction process isn't such a pain for the three sound archives (click the bat as opposed to typing it all out in command prompt).

There are three sound archives - bgm.stw, se.stw, and voice.stw. Do not change the names of these archives, for any of you that want to follow the following steps to extract and fix the wave headers. Everyone should follow these steps until official support is implemented in MultiEx or WATTO's Extractor (which I hope is soon ;D).

BGM Wave Header Fix Batch File:
[http://nesslookalike.googlepages.com/bgmfix.bat](http://nesslookalike.googlepages.com/bgmfix.bat)

VOICE Wave Header Fix Batch File:
[http://nesslookalike.googlepages.com/voicefix.bat](http://nesslookalike.googlepages.com/voicefix.bat)

SE Wave Header Fix Batch File:
[http://nesslookalike.googlepages.com/sefix.bat](http://nesslookalike.googlepages.com/sefix.bat)

1.) Download Nova Software Extractor (google it).
2.) Run Nova Software Extractor over the .stw archive (bgm, se, or voice).
3.) Extract all the files into a new folder on your desktop (or anywhere else really).

You'll notice that the wave files won't play in any media player. This is because they're missing their appropriate wave header, which tells media players how to play the files.

4.) Put xbadpdec.exe in the directory.
5.) Put the appropriate .bat file into the directory with all the wave's and xbadpdec, depending on which archive (bgm, se, or voice) you extracted from.
6.) Double click the .bat file and give it a few minutes to work.
7.) Delete all the files named "voice_XXXXX.wav" or "se_XXXXX.wav" or "bgm XXXXX.wav" and keep all the files that are just "XXXX.wav" (X's representing the number of the file).

Now you can listen to all the sounds in high quality of any of the three archives. Right now, all you'll have to go on to identify which file is which is its number, but hopefully soon, if it is supported by MultiEx or WATTO Extract, the file names (and possibly folder directories where they are stored) will be read from the archives' similarly named .sth file.

Have fun
## Post #4
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2006-07-05T21:18:43+00:00
- Post Title: Breakdown

Instead of just using that program to convert your wavs, you can easily just install the Xbox audio codec to your system, and play the files without conversion in any media player you have.  Or if you like, since you have the codec installed on the system, ANY audio editor can convert the format to any other format that you choose.
## Post #5
- Username: NLA
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 22, 2006 2:36 am
- Post datetime: 2006-07-06T05:46:55+00:00
- Post Title: Breakdown

I must disagree! 

a.) Because they're not being truly converted, as in being reencoded at all. The program is simply fixing their wave header information to be correctly read (no actual touching of the music data), and
b.) That's far too easy. (  )

EDIT: It might be re-encoded, I'm unsure. But its not like its losing much quality at 141.1KB/s. Still, I'd like it in a common format, one that doesn't require an additional codec that isn't automatically included with an operating system.
## Post #6
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2006-07-06T18:34:45+00:00
- Post Title: Breakdown

The biggest difference between the Xbox audio and "standard" formats, is that the Xbox format is 4bit.  

No matter what you do, the quality won't be any better than that, so what's the difference of installing the codec or not?  It doesn't interfere at all with the OS, plus it allows you to re-encode stuff to Xbox format, so you can REPLACE other audio on the Xbox.
## Post #7
- Username: NLA
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 22, 2006 2:36 am
- Post datetime: 2006-07-10T17:05:38+00:00
- Post Title: Breakdown

Ok fine, lets all use an xbox codec to listen to xbox adpdec sound. :B

It'd still be nice if either WATTO Extractor or MultiEx would correctly extract the files (and directories?) from the archive with their correct names, which are in the archives.
## Post #8
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-07-11T02:57:25+00:00
- Post Title: Breakdown

The pak files also have the .wav header split and list the data part of the header in a lookup table. You should be able to spot it.

Codec - short
Number of Channels -short
Sample Rate - int

For the compression code/codec the ID will be 105 = xbadpcm.
## Post #9
- Username: NLA
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 22, 2006 2:36 am
- Post datetime: 2006-07-26T18:41:18+00:00
- Post Title: Breakdown

Because I love the game BREAKDOWN so much, I've decided to do two things:

1.) I have carefully sorted through all 224 music tracks that I've extracted from bgm.stw with Nova Software Extractor and found the soundtracks that can be officially accessed via the in-game audio player menu. I have listed these tracks below.

EDIT: For the sake of completeness and to be true to the game, the names of the soundtracks below are EXACTLY as they appear in the game, down to the case of the letters. Please don't change them, I think they should stay exactly as they are named in the game to be more genuine.

2.) I am currently re-playing BREAKDOWN on Hard Mode (a challenge after completing Normal mode last year), and am planning to create an unofficial track listing (in order of music track encountered in game, complete with short name describing situation) for all the background music that plays throughout the game that is inaccessible via the in-game menu.

Quite a monumental task I've set for myself. :B Now, onto the important stuff:

-Menu Music-
2 - BREAKDOWN
3 - BREAKDOWN Extras Menu
4 - BREAKDOWN Main Menu

-Officially Accessible Tracks (via menu)-
17 - 01 The Adventure Begins
18 - 02 Battle!
24 - 03 Facing the T'lan
47 - 04 Solus
58 - 05 Rooftop Battle
59 - 06 Hanging by a Thread
67 - 07 Onwards!
75 - 08 Assault T'lan
77 - 09 ÃŸ-Project
86 - 10 Stealth T'lan
87 - 10 Stealth T'lan
89 - 11 Ogawa
103 - 08 Assault T'lan
105 - 12 Gianni
107 - 13 Deep into the Tunnels
118 - 04 Solus
119 - 14 Escape from Solus
121 - 15 Mayday
123 - 16 Cornered
129 - 17 Rescue
133 - 18 A Path to Ruin
136 - 19 Sunday Drive
137 - 12 Gianni
147 - 20 Intrigue
153 - 21 Silo
159 - 22 VS Solus - Round 1
163 - 23 This Is My Fate
171 - 24 Post-Apocalypse
176 - 25 Ultra Acceleration
184 - 20 Intrigue
185 - 17 Rescue
187 - 26 Parting
195 - 22 VS Solus - Round 1
199 - 27 Victory[Question Mark]
201 - 28 A Change of Fate
212 - 25 Ultra Acceleration
216 - 29 Final Escape

Note that there are multiples of the same track in there. This strikes me as odd, and I'm confused as to why they are there. There is no difference between the two identical tracks, each set of duplicate tracks have the same CRC-32/MD5 checksum.

Post merging:

The schedule of the analyzation and renaming of the soundtracks in BREAKDOWN was temporarily put on hold for me to finally (after many attempts) render this footage from my BREAKDOWN Hard Mode escapade.

[http://video.google.com/videoplay?docid ... 9207037047](http://video.google.com/videoplay?docid=-2063297789207037047)

In the mean time, I will be indeed reviewing my tapings from my Hard Mode BREAKDOWN adventure to analyze the soundtracks and give them proper names, which will be posted here. Should they be posted here? Probably not, but I feel the topic is still valid until the time comes that the BREAKDOWN archives are analyzed and fully supported by either or both Game Extractor and MultiEx. Aside from that, however, I know that I found this forum via Google, it would not be unlikely someone searching to do the same thing that I've done might come across this post as well. I think later I'll publish these findings to Datacrystal.
## Post #10
- Username: NLA
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 22, 2006 2:36 am
- Post datetime: 2006-08-29T21:02:36+00:00
- Post Title: Breakdown

Is there any work still being done on archive extraction? I know I've gotten off topic, and this thread shouldn't serve as my data log. Extracting and renaming things from the archive is a pain, can some support for the archive types be given?
