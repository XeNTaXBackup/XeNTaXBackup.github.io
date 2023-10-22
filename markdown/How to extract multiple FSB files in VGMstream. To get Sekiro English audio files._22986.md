## Post #1
- Username: VirtCon
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 10, 2020 3:14 pm
- Post datetime: 2020-11-10T07:32:04+00:00
- Post Title: How to extract multiple FSB files in VGMstream. To get Sekiro English audio files.

This gonna be my first post here. I'd also like to apologize if I don't understand some these concepts or if the solution is really easy because I'm very new to this.

SoI've been trying to get the English audio files from the game Sekiro which are labeled as "enu" in the sound folder if they're English. An example would be "vm15_enu.fsb"

I've tried using VGMstream to extract these files FSB files but the problem is that the FSB has multiple sound files inside it. But when I extract it, only one of these files appear! 

Researching into it, it seems like the FSB is being overwritten or something like that. (I'm not really sure.)

Can anybody can help me find a way to extract the FSB and get all the files instead of just one?
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-10T08:21:13+00:00
- Post Title: How to extract multiple FSB files in VGMstream. To get Sekiro English audio files.

If these are standard FSB files, then you can use some other tools like fmod_extr, fsb_aud_extr, FMOD Designer, FSB Extractor etc.
## Post #3
- Username: VirtCon
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 10, 2020 3:14 pm
- Post datetime: 2020-11-10T08:42:08+00:00
- Post Title: How to extract multiple FSB files in VGMstream. To get Sekiro English audio files.

fmod_extr, fsb
Says "Unsupported file or audio format."

 fsb_aud_extr
Says "Unsupported file or audio format."

FMOD Designer
Didn't use that yet.

FSB Extractor
Says "Failed to open file. Content may be encrypted, or it's not a valid FSB file format."
## Post #4
- Username: VirtCon
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-10T08:46:05+00:00
- Post Title: How to extract multiple FSB files in VGMstream. To get Sekiro English audio files.

> "Unsupported file or audio format."
So NO, they are not standard FSB files probably. 

You can upload sample file to service like mega.nz, google drive and someone may look on your sample and help you figure it out.
## Post #5
- Username: VirtCon
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 10, 2020 3:14 pm
- Post datetime: 2020-11-10T08:59:27+00:00
- Post Title: How to extract multiple FSB files in VGMstream. To get Sekiro English audio files.

[https://mega.nz/file/1f4inbyB#4e6M_OV3_ ... m_WdZDSE8U](https://mega.nz/file/1f4inbyB#4e6M_OV3_jsBxNHYLsb1JtG34PP3vvM28m_WdZDSE8U)

Okay, got it. Here's one of the files.
## Post #6
- Username: VirtCon
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-11-10T10:07:05+00:00
- Post Title: How to extract multiple FSB files in VGMstream. To get Sekiro English audio files.

Ok, I have checked your sample and it seems that foobar + vgmstream is working fine. [https://imgur.com/a/cUu1zMe](https://imgur.com/a/cUu1zMe)

You need to select all files (CTRL+A) and then go to Convert > Quick convert and then select WAV output to extract all files without issues.
## Post #7
- Username: VirtCon
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 10, 2020 3:14 pm
- Post datetime: 2020-11-11T04:59:17+00:00
- Post Title: How to extract multiple FSB files in VGMstream. To get Sekiro English audio files.

Works like a charm! Thanks dude!
