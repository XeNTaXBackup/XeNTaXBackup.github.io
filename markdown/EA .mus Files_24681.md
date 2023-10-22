## Post #1
- Username: WolfyBuilder
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Nov 03, 2021 6:35 am
- Post datetime: 2021-11-02T22:45:02+00:00
- Post Title: EA .mus Files

Hello! I am trying to extract music from the Wii game "Boom Blox Bash Party", but the audio files are in the .mus format. I have looked around for any way to play/extract these files, and even tried playing them in Audacity, but haven't had any luck. From what I've heard, they contain many split .asf files that are stitched together in real-time. I'm assuming this is how the game can dynamically switch songs on the fly, the best example being the main menu's various themed tunes.

Here is a link to one of the files in question: [https://drive.google.com/file/d/1tAO7dW ... sp=sharing](https://drive.google.com/file/d/1tAO7dWx8HknSYcw9WR0CK484SJe1mLqM/view?usp=sharing)
## Post #2
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-11-03T00:01:29+00:00
- Post Title: EA .mus Files

> Reply from WolfyBuilder ↑Wed Nov 03, 2021 6:45 am at Wed Nov 03, 2021 6:45 am
>
> ...I have looked around for any way to play/extract these files,... ...but haven't had any luck...
Step 1:
[https://sourceforge.net/projects/vgmtoolbox/](https://sourceforge.net/projects/vgmtoolbox/)



test.png (116.59 KiB) Viewed 154 times


Step 2:
[https://www.foobar2000.org/download](https://www.foobar2000.org/download)
Step 3:
[https://github.com/vgmstream/vgmstream/releases](https://github.com/vgmstream/vgmstream/releases)

have fun
## Post #3
- Username: WolfyBuilder
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Nov 03, 2021 6:35 am
- Post datetime: 2021-11-03T00:19:03+00:00
- Post Title: EA .mus Files

Thanks for the info!
## Post #4
- Username: WolfyBuilder
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Nov 03, 2021 6:35 am
- Post datetime: 2021-11-03T07:25:59+00:00
- Post Title: EA .mus Files

Is there any way to figure out the proper order of the files? Some of the files seem to have some sort of pattern, but then others are scattered randomly, and there seems to be duplicate files as well
## Post #5
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-11-03T19:18:12+00:00
- Post Title: EA .mus Files

There are exactly 91 of them based on their header as you see in screenshot.
As you can see after they are exported in the *_CUT folder, they're exported in the the exact order that they are packed, you can see based on their HEX values in the name.
A lot of the times game assets have duplicates.
## Post #6
- Username: Nicknine
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Oct 04, 2015 3:29 am
- Post datetime: 2022-04-28T16:53:10+00:00
- Post Title: EA .mus Files

> Reply from mono24 ↑Wed Nov 03, 2021 8:01 am at Wed Nov 03, 2021 8:01 am
>
> 
WolfyBuilder wrote: ↑Wed Nov 03, 2021 6:45 am...I have looked around for any way to play/extract these files,... ...but haven't had any luck...
Step 1:
https://sourceforge.net/projects/vgmtoolbox/
test.png
Step 2:
https://www.foobar2000.org/download
Step 3:
https://github.com/vgmstream/vgmstream/releases

have fun

Why would you do this barbarism? If it's a .mus file in EA game that means it's actually a part of mpf/mus combo in which case you can just open .mpf with vgmstream and get all audio samples as subsongs.

> Reply from WolfyBuilder ↑Wed Nov 03, 2021 3:25 pm at Wed Nov 03, 2021 3:25 pm
>
> 
Is there any way to figure out the proper order of the files? Some of the files seem to have some sort of pattern, but then others are scattered randomly, and there seems to be duplicate files as well

The proper order for the segments as well as various scripting data is stored inside .mpf file but its format is unfortunately rather convoluted.
## Post #7
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-04-28T20:26:33+00:00
- Post Title: EA .mus Files

> Reply from Nicknine ↑Fri Apr 29, 2022 12:53 am at Fri Apr 29, 2022 12:53 am
>
> ...Why would you do this barbarism? If it's a .mus file in EA game that means it's actually a part of mpf/mus combo in which case you can just open .mpf with vgmstream and get all audio samples as subsongs...

Well aware of that, been specifying that info in the forum before, BUT the samples i had where just .mus, no .mpf to associate with foobar/vgmstream combo in order to load it properly, so that was/is just a work around since there's no other way for non reverse people, like myself
