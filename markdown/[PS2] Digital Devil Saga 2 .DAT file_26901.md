## Post #1
- Username: A Friendly Irin
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 25, 2023 11:23 pm
- Post datetime: 2023-06-25T15:29:45+00:00
- Post Title: [PS2] Digital Devil Saga 2 .DAT file

I was able to extract some files from a Digital Devil Saga 2 ISO using the BMS script for SMT with QuickBMS (DDS2 uses the same engine as Shin Megami Tensei: Nocturne). However, even after extraction, there is a file called "ZZZ.DAT" I can't seem to decompress. Does anyone know what to do with this?

Here is a MegaUpload link to the file: [https://mega.nz/file/sLsWGYgA#C61ovr_B1 ... spI3JnO-uM](https://mega.nz/file/sLsWGYgA#C61ovr_B1nLSZ60AbeQl-H1UcJ_9KRzSfspI3JnO-uM)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-25T17:05:06+00:00
- Post Title: [PS2] Digital Devil Saga 2 .DAT file

> Reply from A Friendly Irin ↑Sun Jun 25, 2023 11:29 pm at Sun Jun 25, 2023 11:29 pm
>
> 
The .DAT file is unfortunately too large to attach here. Is there a way to split it up so I can share it?

Please upload whole file to some hosting site like mega.nz or google drive and then share a public link here.
## Post #3
- Username: A Friendly Irin
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 25, 2023 11:23 pm
- Post datetime: 2023-06-25T19:37:38+00:00
- Post Title: [PS2] Digital Devil Saga 2 .DAT file

Ah, I see. I've added a link to the OP.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-06-25T21:36:46+00:00
- Post Title: [PS2] Digital Devil Saga 2 .DAT file

Turns out your "ZZZ.DAT" sample is not an archive file, but it is an audio file. 
It has APCM signature which lead me to that post explaining the audio format in details [viewtopic.php?p=28087#p28087](https://forum.xentax.com/viewtopic.php?p=28087#p28087)

Then I've created this script:

```

codec = PSX
interleave = 256
sample_rate = 44100
channels = 2
start_offset = 0x00
num_samples = data_size
```


If you'll save the script as ".dat.txth" and put the script in the same directory as  "ZZZ.DAT" file, you will be able to play your DAT file in foobar2000 with vgmstream plugin.

I'm moving this topic to audio section on this forum.
