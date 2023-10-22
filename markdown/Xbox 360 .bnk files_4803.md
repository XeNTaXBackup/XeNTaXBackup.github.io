## Post #1
- Username: THX1138
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jul 25, 2010 1:00 am
- Post datetime: 2010-07-25T02:56:32+00:00
- Post Title: Xbox 360 .bnk files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-07-27T08:00:01+00:00
- Post Title: Xbox 360 .bnk files

the files are extracted perfectly, the problems are just the files:
- the headers are all in big endian so the PC tools can't work on them directly
- the smaller wav files don't specify the codec used (0xffff) so I don't know if they are xma
- I don't know if those that specify the xma2 codec (0x166) can be decoded without problems with xmaencode because I should reverse their endianess first (as you know sometimes xmaencode can't decode xma files)

so you must first reverse the endianess, then substituite RIFX with RIFF, then using 0x166 instead of 0xffff in the small files and then trying to decode them
## Post #3
- Username: THX1138
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jul 25, 2010 1:00 am
- Post datetime: 2010-08-01T21:44:07+00:00
- Post Title: Xbox 360 .bnk files

First off, thank you aluigi for taking the time to not only respond but to add some additional insight to all of this.

Second, like I stated before, this is all new to me. My skill-set is limited to researching, downloading software, and that's about it. I can follow what you are saying, understanding terms and descriptions here and there along the way, but that's about. I feel ashamed I am not able to take a more active role in figuring this out myself like reversing code, modifying headers, or decoding anything. I also hate to sit here and 'expect' anyone to do the legwork for me. I guess in a way that was the whole point of posting this, hoping someone could fiddle around with this stuff and come up with a quick solution. I am sorry for being naive in thinking it would be a quick and easy process, so forgive me for my underestimation.

With that being said, I will try to look into reversing the endianess as suggested by aluigi. I will research how that is done and hopefully come up with something. The substituiting RIFX with RIFF sounds simple enough on the surface but I will presume it's more difficult for someone like me. Using 0x166 instead of 0xffff in the small files again seems straight forward but the whole decoding them is over my head lol.

Any ways, again thank you for contributing and maybe Ill post back with any progress I make.
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-12-26T18:27:48+00:00
- Post Title: Xbox 360 .bnk files

I actually managed to get a file to playback just fine.

What I did was I opened up the .bnk file in a hex editor and scanned for the XMA Flag. I got around ~ 300 hits with the l_default.bnk (I know you get like 1700 .wav's when using Alpha's other script, but these are the files that are probably encoded with XMA)

This is what I did to achieve this:

1. Open up the l_default.bnk in a hex editor
2. Scan or find all instances of the XMA Flag "FC01C001" - these are hex values, not a text string.
3. Find the first flag, and then count six bytes back (I think that for games that use soundbanks, you have to count six bytes back. For games that don't use them, you usually only need to count 4)
4. Save everything from the six bytes before the XMA flag to the next instance of the flag.
5. Run the saved file through QuickBMS using Alpha's Add XMA RIFF Header script
6. Then run that through towav
7. You should now have a listenable file.

NOTE: Run a spectral analysis on each file and make sure that they corrospond to the set Hz rate in the Add XMA RIFF Header script. If you have a 48kHz wav file but it seems to cutoff around 22000Hz in the spectral frequency, you'll have to adjust the script.

Here's the file I got from the l_intro.bnk file.

[http://www.flameupload.com/files/KWOMGFPH/Intro.flac](http://www.flameupload.com/files/KWOMGFPH/Intro.flac)

The only problem is, this is all manual work. There isn't a script which can help you out with this task (AFAIK) so it can take some time.
## Post #5
- Username: THX1138
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jul 25, 2010 1:00 am
- Post datetime: 2011-07-17T02:52:38+00:00
- Post Title: Xbox 360 .bnk files

First off, THANK YOU brendan19!!!!

That was some great work you did there, and I am sorry it took so long for me to recognize your work; I was able to reproduce the steps you listed with some great results. However, like you noted this is done manually and will take a very long time to complete. I am pretty sure you are correct that there isn't a script out there which would speed up the process but I was thinking it could be possible if someone were to look over your steps and figure it out.

The original script I used (I forget who made it, so I apologize for not crediting the person) would extract the files to .wav which weren't playable. That is where I was left all those months ago. Here is the script:

```
idstring "BKHD"
get OFFSET long
math OFFSET += 8
goto OFFSET
idstring "DIDX"
get DIDX_SIZE long

savepos BASE_OFF
math BASE_OFF += DIDX_SIZE
math BASE_OFF += 8  # DATA chunk

math FILES = DIDX_SIZE
math FILES /= 12

for i = 0 < FILES
    get DUMMY long
    get OFFSET long
    get SIZE long

    math OFFSET += BASE_OFF
    log "" OFFSET SIZE
next i

```


Now I am sure many people will jump on me for saying this, but couldn't a similar script be made to emulate this process with the exception of extracting the chunks with the proper flags like you noted? As I said in my original post, I know next to nothing about hex-editing, decompiling, compiling, etc, so please excuse my ignorance for assuming this would work this way.

Once again, thank you for taking the time to respond and come up with a solution for this; I posted it so long ago I never thought any progress would be made, simply because of my own lack of knowledge.
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-08-22T18:49:14+00:00
- Post Title: Xbox 360 .bnk files

I think I've worked out all the formats used for this game.

Limbo on Xbox 360 Live Arcade uses a combination of Wwise, Raw PCM and XMA.

I'm currently finding all the Raw PCM files now.

Out of the 1794 .wav files that script extracts from the l_default.bnk, I've worked out the following:

101 files - Raw PCM (Big Endian - 16 Bit)
287 files - XMA - FC01C001 (XMA Flag #1)
821 files - XMA - FC038000 (XMA Flag #2)
584 files - Wwise
1 file - Raw PCM (Little Endian - 16 Bit)

Once I've converted all the raw pcm into PCM with a proper header, I'll post a link to the audio archive
## Post #7
- Username: THX1138
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jul 25, 2010 1:00 am
- Post datetime: 2011-10-16T16:40:40+00:00
- Post Title: Xbox 360 .bnk files

brendan19,

You are a saint! Thank you once again for your hard work, I truly appreciate the effort.
## Post #8
- Username: gallopinto
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jan 03, 2012 1:42 pm
- Post datetime: 2012-01-04T00:07:13+00:00
- Post Title: Xbox 360 .bnk files

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-02-16T06:37:32+00:00
- Post Title: Xbox 360 .bnk files

Here are all the Limbo audio files I have managed to extract and convert into PCM WAV.

<link removed due forum rules violation>

Enjoy
## Post #10
- Username: THX1138
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jul 25, 2010 1:00 am
- Post datetime: 2012-04-12T23:06:25+00:00
- Post Title: Xbox 360 .bnk files

brendan19,

Sorry for the delayed response but THANK YOU SO MUCH! I appreciate all the time and effort that went into this. This forum is very fortunate to have a member like you.

Thank you.
