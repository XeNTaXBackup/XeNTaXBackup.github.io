## Post #1
- Username: DarkStar18
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 24, 2019 3:58 am
- Post datetime: 2021-09-12T03:27:14+00:00
- Post Title: Extracting .mod music from Global Defense Network

This was an obscure rhythm shooter for Windows, made by Jeff Evertt in 2004 

Has some sweet .mod music files locked most likely somewhere in one of two ".pck" files and I haven't a clue where to start.    And I need to rip them from the game because while Jeff listed the emails and websites for all the music contributors, they're all long since gone.

Can be downloaded here: [https://archive.org/details/SetupGDNClientUpgrade](https://archive.org/details/SetupGDNClientUpgrade)
## Post #2
- Username: Arron17
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 03, 2021 5:30 am
- Post datetime: 2021-10-02T21:38:47+00:00
- Post Title: Extracting .mod music from Global Defense Network

Hi Darkstar,

I've had a look at this, first thing like this I've done, so I thought I'd give a little explanation.

Found 20 Music Files in the pck file located in the SetupGDNClientUpgrade Installer.

You mentioned MOD files, but I wasn't too sure what they were, so had a look in the pck file with a hex editor, found a few headers for LAME MP3 and OGG Vorbis files, some are just sound effects but others were this same odd noise, so thought something else must be going on.

As part of the game files there is a bass.dll, this looked audio related so I looked it up online and it is an audio library, details here -  [https://www.un4seen.com/bass.html](https://www.un4seen.com/bass.html)

I downloaded the library and had a look at the source code for the MOD functions and within the source code was a list of the file formats, so I started looking for the headers of the file formats in the pck file and found 20 MO3 headers, which is an MP3/OGG Compressed MOD.

I still don't fully understand what I'm looking for so the way I extracted them was rather crude, thankfully they are listed one after another in the file, so I manally went from one MO3 header to another and picked them out. I used XMPlay which is a MOD file player made by the same people who made the Bass library to test all the files and they all work.

I've used FFMPEG to convert them to MP3, I'll include a link to a zip with the MP3s and original MO3 files in. It should be valid for 30 days, if it stops working for some reason let me know.

[https://easyupload.io/xtiysl](https://easyupload.io/xtiysl)
## Post #3
- Username: DarkStar18
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 24, 2019 3:58 am
- Post datetime: 2022-03-09T17:59:02+00:00
- Post Title: Extracting .mod music from Global Defense Network

So terribly sorry but i never saw this, had a job change shortly afterwards and in the chaos never saw your replay.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-20T23:42:58+00:00
- Post Title: Extracting .mod music from Global Defense Network

I've also had a look at this PCK file and it seems it is just a blob of data with OGG, MO3, and maybe other audio files written one by another.
File offsets and sizes are calculated at runtime by internal resource manager and it's not possible to create program/script to unpack
this automatically.

So the file format looks probably like this:

```
{
   x bytes - file data
}
```


Data doesn't look compressed, I was able to extract one OGG file manually and play it without issues.
