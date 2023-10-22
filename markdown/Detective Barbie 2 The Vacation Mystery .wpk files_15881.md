## Post #1
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2017-02-16T14:59:41+00:00
- Post Title: Detective Barbie 2: The Vacation Mystery .wpk files

I am very confused about the *.wpk files found in Detective Barbie 2: The Vacation Mystery (I don't have a copy of the first game, but I assume it uses the same format). Looking at them, there appear to be data for actual .wav files (the RIFF header and so on), but extraction tools don't seem to detect the audio, and extracting them manually, they sound extremely distorted.

(EDIT: Huh. The files don't attach. "The extension wpk is not allowed.")
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2017-02-17T07:33:18+00:00
- Post Title: Detective Barbie 2: The Vacation Mystery .wpk files

> Reply from HeadsetGuy
>
> (EDIT: Huh. The files don't attach. "The extension wpk is not allowed.") Either zip the file before you upload it (for smaller files) or use a file hoster (e.g. mediafire) and post the link here.
## Post #3
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2017-02-17T19:06:49+00:00
- Post Title: Detective Barbie 2: The Vacation Mystery .wpk files

Apologies for the (somewhat) late response, as I've been pretty busy. I have attached a zip file containing 8 .wpk files here.
[wpk examples.zip](https://xentaxbackup.github.io/file/12466_wpk examples.zip)
## Post #4
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2017-08-07T13:12:43+00:00
- Post Title: Detective Barbie 2: The Vacation Mystery .wpk files

Well, it's been a while, but I've actually figured out a few things about this. I can't figure out most of the header, but that 2C 00 00 00 actually refers to the length of the normal RIFF header. The 4 bytes after that header are the file length, minus 0x44 for the information prior to the data. As for everything else, I'm still confused.

Also, I discovered a WPK file and a WAV file with the same name on the CD, so I've attached those here.
[wpk and wav.zip](https://xentaxbackup.github.io/file/13174_wpk and wav.zip)
## Post #5
- Username: Pingu
- Rank: veteran
- Number of posts: 116
- Joined date: Sat Apr 16, 2016 10:15 am
- Post datetime: 2017-08-08T16:29:18+00:00
- Post Title: Detective Barbie 2: The Vacation Mystery .wpk files

This QuickBMS script will parse the RIFF Wav files out of the *.wpk files. I don't know what's up with the actual audio though. It sounds to be just a sample rate problem, which I don't know why is happening. That part I can't help you with sorry :/. 
QuickBMS Script:

```
savepos OFFSET
get BASENAME basename
set NAME string BASENAME
string NAME += ".wav"
get SIZE asize
math SIZE - 0x14
log NAME OFFSET SIZE

```
## Post #6
- Username: HeadsetGuy
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Feb 16, 2017 10:51 pm
- Post datetime: 2017-08-09T04:02:33+00:00
- Post Title: Detective Barbie 2: The Vacation Mystery .wpk files

> Reply from Anexenaumoon
>
> I don't know what's up with the actual audio though. It sounds to be just a sample rate problem, which I don't know why is happening. That part I can't help you with sorry :/.
It's more than just the sample rate; the data itself is completely different, if you look at the two files in a hex editor. It seems to be encoded and/or compressed. Thanks for trying, though.
