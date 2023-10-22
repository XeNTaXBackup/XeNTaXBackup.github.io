## Post #1
- Username: akudaijin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 26, 2019 2:10 am
- Post datetime: 2023-08-22T23:10:17+00:00
- Post Title: BlazBlue Entropy Effect .acb/.awb

Hello. I'm trying to see if it's possible to do anything with this format that the game BlazBlue Entropy Effect is using for their music. Seems like no existing tools that can work with these formats can properly read/extract these specific ones here. vgmstream plugin plays the .awb files but it's just raw garbled sound, although it shows how many files are in the archive however and the length of said music files.

Here's sample files: [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/19dPSz-2xEYP0VPb-JcEOY_kwdsWfCiQJ?usp=sharing)
## Post #2
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-08-22T23:37:44+00:00
- Post Title: BlazBlue Entropy Effect .acb/.awb

Your files is encrypted and you didn't supply the right HCA key needed to play the files (That's why you only heard the noise).
To obtain the said keys, you have to reverse-engineer the game for now since the game was rather newish or you can ask the vgmstream folks on github or hcs64 forums.
## Post #3
- Username: akudaijin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 26, 2019 2:10 am
- Post datetime: 2023-08-22T23:54:25+00:00
- Post Title: BlazBlue Entropy Effect .acb/.awb

I see, makes sense, thank you for the information and suggestions provided.
## Post #4
- Username: xgecemx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 15, 2023 11:49 pm
- Post datetime: 2023-09-15T15:54:21+00:00
- Post Title: BlazBlue Entropy Effect .acb/.awb

Hi there! Dealing with proprietary audio formats like the .acb and .awb files from BlazBlue can be frustrating. Unfortunately without official tool support, options are [limited](https://www.typecalendar.com/limited-partnership-agreements.html). But here are some thoughts:

As you mentioned, vgmstream can at least detect the number and length of tracks within the .awb files, even if the audio is garbled. That's a good start.
There may be certain sound bank offsets or encryption applied that vgmstream doesn't account for. Sometimes these can be figured out via trial & error or looking at diffs in a hex editor.

Checking if any fan projects have made progress with these formats could provide leads. The BlazBlue modding community may have useful insights.
As a last resort, see if there are any audio ripping tools that can extract the sounds directly from the game [calendar 2024 pdf](https://www.typecalendar.com/printable-yearly-calendar) executable while it's running.

Game audio formats are designed to be secure, so cracking them open takes time. But with some digital archaeology it's often possible to make progress. Let me know if you have any breakthroughs! Game audio preservation is important.
