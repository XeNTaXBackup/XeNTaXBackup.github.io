## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-01-22T01:02:59+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

Hey everyone! Using Watto's Game Extractor I managed to rip a lot of files, but they have no extension and don't know what to do with them... Can you help me out?

Mechassault 2 Sounds

[https://www.dropbox.com/s/8ik7rnjbu9kv1 ... o.rar?dl=0](https://www.dropbox.com/s/8ik7rnjbu9kv1pn/MA2%20audio.rar?dl=0)


Mechassault Sounds

[https://www.dropbox.com/s/60n2gay9l4mk3 ... o.rar?dl=0](https://www.dropbox.com/s/60n2gay9l4mk3xg/MA1%20Audio.rar?dl=0)

Thanks for helping!
## Post #2
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2019-02-09T04:34:52+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

What platform are these from? Make sure to specify that!
## Post #3
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-02-11T02:58:52+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

They're both on Microsoft Xbox
## Post #4
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-02-14T09:56:40+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

*bump* Any clues?
## Post #5
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-03-27T15:16:59+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

Please, I really want those amazing sounds from Mechassault 1 and 2
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-05-21T23:28:31+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

I can help you extract the voices and music from Mechassault 1.  Watto's Game Extractor doesn't seem to extract these audio files correctly at all, but luckily the d1Bank archives are not too complicated to work out the format of.

My attached program will extract the raw audio files from a .d1Bank archive.  Just run it from a command prompt and it should be fairly self-explanatory how to use.

You can then use GENH in VGMToolbox to create a playable audio file.

The speech files are all XBOX 4-bit IMA ADPCM, mono, 22050 Hz; the music files are 16-bit PCM (Little Endian), 6 channels, 48000 Hz
[mech1.zip](https://xentaxbackup.github.io/file/16274_mech1.zip)
## Post #7
- Username: binarybailey
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 02, 2016 11:35 am
- Post datetime: 2020-03-30T01:49:09+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

Hello,

Thank you for your tool 

I used to extract the files from the .d1bank and came out as .raw files, tried using the GenH creator to create playable files but still getting garbled audio  I am playing them in foobar2000



My settings are attached and wondered if you might be able to specify further? It says file size is optional but doesn't convert without keying in a value.

Have also tried in xbadpdec.exe as well but still creates garbled audio.

Thanks in advance!
[vgmtoolbox.png](https://xentaxbackup.github.io/file/17837_vgmtoolbox.png)
## Post #8
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-03-30T15:45:22+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

I'm not sure why you can't get it to work.  Try this QuickBMS script instead - it's much easier!
[mech1.zip](https://xentaxbackup.github.io/file/17844_mech1.zip)
## Post #9
- Username: binarybailey
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 02, 2016 11:35 am
- Post datetime: 2020-03-30T18:42:17+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

You sir are a legend 

Started over from scratch and used your attachments and worked like a charm! 

Thank you so much
## Post #10
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-01-25T16:41:29+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

Is there still no way to properly extract SFXStream from Mechassault 2: Lone Wolf and find all the missing sound effects?
## Post #11
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-01-25T17:41:50+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

Yes, use this script and the attached .txth file for the sfxstream file.
[MA2_sfxstream.zip](https://xentaxbackup.github.io/file/19394_MA2_sfxstream.zip)
## Post #12
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-01-25T23:35:20+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

> Reply from DKDave ↑Tue Jan 26, 2021 1:41 am at Tue Jan 26, 2021 1:41 am
>
> 
Yes, use this script and the attached .txth file for the sfxstream file.

Sorry to bother, how do I uses the .txth file? I used the BMS script and got a collection of .vgmstream files extracted.
EDIT: I figured it out, still no sign of the those sounds... Maybe they're stored in the level files as well? I can't figure out where they could be saved...
## Post #13
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-01-27T02:44:36+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

Okay, I found out where the rest of the sounds are hidden, they're all in "movies.mgf". It contains two .xwb archives I cannot extract due to them being corrupted and not allowing me to extract or preview any sounds within them. One is 1 kb large and the other is 3,400 kb. 
Here: 
[https://mega.nz/file/0ZIRQSxD#GpSnWfqou ... d1jjSU8sVg](https://mega.nz/file/0ZIRQSxD#GpSnWfqouZp3qU20I6RTwR1Ehp3TffZtAd1jjSU8sVg)

I uploaded my findings so maybe someone else has better luck cracking them open..
## Post #14
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-01-27T12:59:12+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

The .xwb files are fine.  You can extract mgf archives with my attached script, and then you can drop the xwb files into Foobar to get the sounds.
[mgf.zip](https://xentaxbackup.github.io/file/19400_mgf.zip)
## Post #15
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-01-27T15:02:48+00:00
- Post Title: Mechassault 1 and 2 Extracted Audio Problems

Thanks a ton! Works like a charm!
## Post #16
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-01-27T19:26:43+00:00
- Post Title: Re: Mechassault 1 and 2 Extracted Audio Problems

I hadn't extracted that movies.mgf previously, but it does have some .xsb files that match those .hdxwb files - so you can get the filenames for the sfxstream and voice - if you rename those other .hdxwb files to just .xwb you can drop them straight into Foobar instead.  I'd already written my scripts a while ago, so you can use either method!
## Post #17
- Username: Predator459
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 05, 2021 8:16 pm
- Post datetime: 2021-03-05T13:09:28+00:00
- Post Title: Re: Mechassault 1 and 2 Extracted Audio Problems

I really hope you get this figured out, I've been looking for a number of the sound effects from Mechassault 1 for years, especially the mech destruction sound.
## Post #18
- Username: forwarded
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 28, 2023 1:56 am
- Post datetime: 2023-04-27T19:38:15+00:00
- Post Title: Re: Mechassault 1 and 2 Extracted Audio Problems

> Reply from Pepsee ↑Tue Jan 26, 2021 7:35 am at Tue Jan 26, 2021 7:35 am
>
> 
DKDave wrote: ↑Tue Jan 26, 2021 1:41 am
Yes, use this script and the attached .txth file for the sfxstream file.


Sorry to bother, how do I uses the .txth file? I used the BMS script and got a collection of .vgmstream files extracted.
EDIT: I figured it out, still no sign of the those sounds... Maybe they're stored in the level files as well? I can't figure out where they could be saved...

Is there a way to make it work with winamp? I don't know what to do with the vgmstream files, or the two txth files.
