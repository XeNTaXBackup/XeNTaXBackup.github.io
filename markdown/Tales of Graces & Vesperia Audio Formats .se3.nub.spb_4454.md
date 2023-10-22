## Post #1
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-05-14T14:37:46+00:00
- Post Title: Tales of Graces & Vesperia Audio Formats: *.se3/*.nub/*.spb

Hi everybody! I'm new here!  
I'm here because I need some help with some strange file extensions.
I wanted to rip some sound effects and musics from the game "Tales of Graces" for Wii. In the root directory I found a huge .cpk (CRIware) file, that I opened without problems with quickbms by aluigi.
In the "snd" folder, where the sound should be, I found some ".se3" files that are clearly compressed folders (like "STC_BTL.se3") which contain sound effects, and some ".nub" files (like "MUSIC.nub", that should contain the bgm).
I thank aluigi for making a script to unpack the ".nub" files with quickbms, but it's not over yet. I tried to uncompress the "MUSIC.nub" file, but it seems that it contains other raw files, which are impossible to read as they are.
I'd like you to help me to find a way to uncompress properly the other type of file (the ".se3"), and to decode the content of ".nub" files. If I remember well, these kind of files are used by "Tales of Vesperia" for Xbox360, too.
And, talking about the latter, I've found another type of audio container: the ".spb", that should be specific for XBox360.

Here you find two examples of the files:
STC_SYS.se3
VOSCE07.nub
US_VOSCE01.spb

And this is the bms for .nub made by aluigi:

```
get DUMMY long
get DUMMY long
get DUMMY long
get FILES long
get BASE_OFF long
math TMP = FILES
math TMP *= 4
log MEMORY_FILE 0x20 TMP
for i = 0 < FILES
    get OFFSET long MEMORY_FILE
    goto OFFSET
    getdstring DUMMY 20
    get SIZE long
    get OFFSET long
    math OFFSET += BASE_OFF
    log "" OFFSET SIZE
next i
```

Thank you very much for every solution you may find.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-05-15T19:21:48+00:00
- Post Title: Tales of Graces & Vesperia Audio Formats: *.se3/*.nub/*.spb

The .nub files are supported by manakoAT's NUBExt [http://bxaimc.hcs64.com/Tools/NUBExt%20r7.zip](http://bxaimc.hcs64.com/Tools/NUBExt%20r7.zip)
The extracted bnsf files can be played by vgmstream ([http://hcs64.com/vgmstream.html](http://hcs64.com/vgmstream.html)) since r763.
aluigi's script ignores the bnsf headers, which are essential to decoding.  The codec is G.722.1 Annex C, aka Polycom Siren 14.
## Post #3
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-05-16T07:20:55+00:00
- Post Title: Tales of Graces & Vesperia Audio Formats: *.se3/*.nub/*.spb

hcs, you're a genius!  It worked perfectly!
I unpacked the .nub with NUBExt (which I didn't know), and read the files with the vgmstream plugin for Winamp.
Thanks a lot for finding the solution! *_*
Let's see if there's something it can be done with the se3, now!

All I can say (sorry, I'm not an expert about this ><), is that looking into a .se3 with a hex editor, there is a list of filenames at the very beginning. So I suppose they are just packed folders with compressed wavs into them (you can also manage to "hear" the sounds if you open the .se3 in raw format with, eg., Adobe Audition... they are just extremely disturbed, obviously). Is there a way to create an extractor?
## Post #4
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-05-17T13:53:30+00:00
- Post Title: Tales of Graces & Vesperia Audio Formats: *.se3/*.nub/*.spb

I've edited the first post with another file type, the ".spb" and an example.
I've opened it with the usual hex editor and seen that the header is "RIFF WAVEXMA2", but there are many of them (something like 90~). According to the information I've found, it should be a specific audio format for XBox360, so I guess this ".spb" is just another archive with xma2 into it.
Maybe they can be converted if we unpack the main file... But I don't know if there's an extractor for that...

(ah, Vesperia uses ".se3" for almost all the other files, ".spb" just for music and a few other things)
## Post #5
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-05-24T11:10:26+00:00
- Post Title: Tales of Graces & Vesperia Audio Formats: *.se3/*.nub/*.spb

Found anything? ._.
Maybe, since we're talking basically about archives, this topic should stay in "Game Archive Research" or "Compressed files and methods"...
## Post #6
- Username: Romored
- Rank: beginner
- Number of posts: 20
- Joined date: Fri May 14, 2010 7:52 pm
- Post datetime: 2010-08-29T15:40:33+00:00
- Post Title: Tales of Graces & Vesperia Audio Formats: *.se3/*.nub/*.spb

Did someone find any solution?
Searching on the internet, I found some information about .se3 files: it seems that they are .nub with a different header. I found a discussion saying that deleting the header to the 0x5000 offset (even if I think this is specific of the file they were talking about, but it was always from Tales of Graces), you can transform the .se3 file in a valib .nub.
I tried it, but when I open the modified file with NUBExt, it doesn't recognize the header. I also tried deleting from 0x0 to 0x2048, like another user said, and this time it recognises the header, but doesn't extract nothing anyway.
It seems that in this kind of file there are XMA files, too (even in ToG files, which should contain dsp format) which cannot be detected by the version of NUBExt I have (r7).
