## Post #1
- Username: reditec
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Oct 28, 2015 11:08 pm
- Post datetime: 2016-01-11T16:41:53+00:00
- Post Title: Help needed with AWC container format (Red Dead Redemption)

Hey guys.

I'm currently working on researching the .awc container format used in Rockstar Games Advanced Engine (RAGE) based games like Red Dead Redemption, Max Payne 3 and GTA V.
I'm trying to research the version used for Red Dead Redemption.
What I know: On PC it would use .wav files (but there is no PC version), on Xbox 360 it uses xma files and on PS3 mp3 files.
I'm starting with the Play Station version, as it's easier.
From a conversation with GooD I know: "it is container with raw audio data, and yes somewhere in there also are Information about sample rate etc."
Raw data means audio files without the file header.
I can notice in my example .xma file that there is "LAME3.97" often in the file. It looks like the mp3s were created using the lame codec version 3.97. Sadly those don't seem to mark the beginning of a new audio file.
I uploaded a couple of examples:
[https://www.mediafire.com/folder/4unetwz2m7s2y/RDR](https://www.mediafire.com/folder/4unetwz2m7s2y/RDR)

Please can someone try explaining me this format or at least point me into the right direction? 
I'm a bit "overchallenged" probably :p
