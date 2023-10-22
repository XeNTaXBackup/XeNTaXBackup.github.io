## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2017-09-05T21:14:09+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

Hello, Xentax! I have gone back to ripping files from an adored classic of my childhood, Brute Force. The weapons sounded really memorable, however I simply cannot find where the sound folder/archive for the weapon/misc sound effects is... The ones I suspected that contained them cannot be opened despite being .xwb or .bin. Please check the files I have uploaded on [Dropbox](https://www.dropbox.com/s/7y5h1970hwl0292/Brute%20Force%20Sounds.rar?dl=0) and give me a heads up! Thank you in advance!  

P.S: If anyone knows where the models are stored and how to extract them, please let me know!
## Post #2
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2017-11-07T20:25:10+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

Still no idea, anyone? :c
## Post #3
- Username: Protocol X27
- Rank: ultra-veteran
- Number of posts: 341
- Joined date: Thu Dec 15, 2011 12:46 am
- Post datetime: 2017-11-27T19:33:10+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

Sorry that I can't shed much light on the subject. I don't know jack outside of the couple of formats that I've worked with least of all audio.  

From the samples, I'm guessing that the bulk of the data is inside the mp_common folder.  All of the other sound folders have files too small for anything relevant, but they could be just file headers.  Maybe combining those with the other xwb files may yield something.

The info in the mp_common folder comes in pairs, so one file could be index while the other is actual data. For example the sound files are paired as mem/xwb.  I initially though one of the two may still be compressed, but I don't know compression well enough to say that with certainty.

Files in the character folder may be indexes as well if not the specific actual data if not in the mp_common folder.  

Are there tools for xwb files that I could test?  Hopefully there is some knowledge out there somewhere because this was totally an underrated game, and the OG Xbox could always use some extraction love.
## Post #4
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-01-28T10:58:16+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

> Reply from Protocol X27
>
> Sorry that I can't shed much light on the subject. I don't know jack outside of the couple of formats that I've worked with least of all audio.  

From the samples, I'm guessing that the bulk of the data is inside the mp_common folder.  All of the other sound folders have files too small for anything relevant, but they could be just file headers.  Maybe combining those with the other xwb files may yield something.

The info in the mp_common folder comes in pairs, so one file could be index while the other is actual data. For example the sound files are paired as mem/xwb.  I initially though one of the two may still be compressed, but I don't know compression well enough to say that with certainty.

Files in the character folder may be indexes as well if not the specific actual data if not in the mp_common folder.  

Are there tools for xwb files that I could test?  Hopefully there is some knowledge out there somewhere because this was totally an underrated game, and the OG Xbox could always use some extraction love.

Hey! Sorry I didn't answer... I assumed this thread was dead and nothing could possibly be done for this anymore.. The best tool for .xwb files is definitely EkszBox-ABX. Thanks for helping out!
## Post #5
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2018-01-30T01:52:55+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

Generally, XWB banks can be played directly with vgmstream due to a neat feature incorporated not too long ago that can do “subsongs” so don’t forget to grab the latest release.

But if you must split the XWB into smaller files, bnnm created a tool for such purposes: [https://github.com/bnnm/vgmstream-build ... _split.zip](https://github.com/bnnm/vgmstream-builds/blob/master/bin/xwb_split.zip)
## Post #6
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-01-31T19:47:12+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

Thank you! I tried using it, but nothing happens, at least for me...
## Post #7
- Username: bnnm
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Nov 10, 2017 6:43 am
- Post datetime: 2018-02-01T18:29:55+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

The XWB are empty. Sound data is in those sounds-xxxxx.mem while sounds-xxxxxx.xmb has the index to individial sounds.

Here is a quick way to play them: to unzip [this file](https://www.sendspace.com/file/p5jmb1) in the folder, rename the .mem to .vgmstream and play with vgmstream.

Extracting individual sounds would need for somebody to create a .bms parsing the .xmb, I think this is adecuate for now as you can convert to wav and edit.

I guessed the sample rate, you can change it in the unzipped .txth (open as a text file).
## Post #8
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-02-01T22:55:07+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

Wow, thanks, I'm trying to figure it out and it's really tricky... I wish I could just get all the files in .wav format and get it over with..
## Post #9
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2018-02-03T18:30:50+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

Sorry for the double post, but can you post a detailed step by step tutorial of how to get the files? Where do I get vgmstream and what version do I need, what else is needed to download, how do I use the program and rip the files, etc. It'd be much appreciated
## Post #10
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-07-13T10:46:30+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

> Reply from bnnm ↑Fri Feb 02, 2018 2:29 am at Fri Feb 02, 2018 2:29 am
>
> 
The XWB are empty. Sound data is in those sounds-xxxxx.mem while sounds-xxxxxx.xmb has the index to individial sounds.

Here is a quick way to play them: to unzip this file in the folder, rename the .mem to .vgmstream and play with vgmstream.

Extracting individual sounds would need for somebody to create a .bms parsing the .xmb, I think this is adecuate for now as you can convert to wav and edit.

I guessed the sample rate, you can change it in the unzipped .txth (open as a text file).

Could you repost the file if you still have it, please?
## Post #11
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-10T05:38:49+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

All you need is this to completely get every single audio file from the game's levels and characters. Extract it, and then run the .exe
From there, you just go into the game files and extract the .xwb from the archive of your choosing. 

For example, the COMMON folder simply contains the .xwb for Brute Force squad.
Drag the .xwb from COMMON into the program's window once it's open. And you should be able to listen/convert/extract any of the lines or sounds you want from the characters. They're all named as well. Alot of unused sound files are in them. This should work completely. 
Not all the .xwb files in the game are able to be read by the program, and as such if you try to go inside one that doesn't work the program will give errors. Restart the program if this happens.

[https://drive.google.com/file/d/13IPG08 ... sp=sharing](https://drive.google.com/file/d/13IPG08-bXrnstOLkABDxFTBXiRQ7DXDl/view?usp=sharing)
[anyofthem.png](https://xentaxbackup.github.io/file/20767_anyofthem.png)
## Post #12
- Username: manbig343
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Aug 31, 2021 3:54 pm
- Post datetime: 2021-09-10T05:49:35+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

I must note that you need to make sure you go to 
"ML-SOUNDS" for the .xwbs, and they have to be extracted outside of their archive first. And then dragged into the program.
[scree.jpg](https://xentaxbackup.github.io/file/20770_scree.jpg)
## Post #13
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-09-18T12:07:10+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

> Reply from manbig343 ↑Fri Sep 10, 2021 1:49 pm at Fri Sep 10, 2021 1:49 pm
>
> 
I must note that you need to make sure you go to 
"ML-SOUNDS" for the .xwbs, and they have to be extracted outside of their archive first. And then dragged into the program.

I knew about the XWB archives and how to rip from them, but none of them give you weapon sounds..
## Post #14
- Username: snowbie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 28, 2021 10:39 am
- Post datetime: 2023-05-04T05:10:27+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

obligatory bump since I'm after all the sounds. weapons, menus, misc sounds, stuff like that

recap of everything that's been done:
using EkszBox-ABX, all files from data/sounds/***.xwb were able to be extracted. looks like these are the music files for various missions, which includes ambient stuff. vgmstream also works but outputs one file. EkszBox-ABX outputs separated *named* files.

data/ml-sounds/en/***.xwb yielded the voice files and ambient sounds

seems like the .mem/xwb files in data/ are what I'm after, but that's the complicated bit I don't quite get. the previously mentioned suggestion doesn't work, assuming the file linked was vgmstream. latest version won't read either of the files
## Post #15
- Username: imagine
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 23, 2021 3:31 pm
- Post datetime: 2023-05-11T01:55:54+00:00
- Post Title: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

> Reply from Pepsee ↑Sat Sep 18, 2021 8:07 pm at Sat Sep 18, 2021 8:07 pm
>
> 
manbig343 wrote: ↑Fri Sep 10, 2021 1:49 pm
I must note that you need to make sure you go to 
"ML-SOUNDS" for the .xwbs, and they have to be extracted outside of their archive first. And then dragged into the program.


I knew about the XWB archives and how to rip from them, but none of them give you weapon sounds..

Hey, since you've posted the Garry's Mod models with sounds does that mean you have those sounds available in a standard format now? And could they be shared here separate from that?
## Post #16
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2023-05-14T14:40:08+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

I have figured where the sounds were being stored. They're in the .mem files. You can convert them using the XMA-to-Wav Tool. Here is a link with all the sounds I could rip. <link removed by moderator>
## Post #17
- Username: imagine
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 23, 2021 3:31 pm
- Post datetime: 2023-05-15T04:54:55+00:00
- Post Title: Re: Brute Force (XBOX 2003) - Where are the weapon/misc sounds?

> Reply from Pepsee ↑Sun May 14, 2023 10:40 pm at Sun May 14, 2023 10:40 pm
>
> 
I have figured where the sounds were being stored. They're in the .mem files. You can convert them using the XMA-to-Wav Tool. Here is a link with all the sounds I could rip. <link removed by moderator>

<link removed by moderator>
