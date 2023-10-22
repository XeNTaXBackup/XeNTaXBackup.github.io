## Post #1
- Username: ofthriceandmen
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Dec 01, 2018 1:08 am
- Post datetime: 2021-10-26T18:02:30+00:00
- Post Title: Unknown CSB files from X-Men Legends prototype

Hello,
I am here because an Xbox prototype of X-Men Legends 1 came out recently and inside are some .csb files that have audio files stored in them.

The final version of X-Men Legends 1, X-Men Legends 2, and Marvel Ultimate Alliance 1 all use .zsm and .zss to store their audio files. These can be gotten into quite easily with a program called ZSM Sound Editor.

However, neither of the 2 quickbms scripts for .csb files worked. Neither has anything else anyone has tried.

The prototype ones have unused audio that isn't in the game. We can tell this because of the names of some of these .csb files. I am a member of Marvel Mods and no one can get into these files, so I thought I go here for help.

Here is what another community member said of his efforts to get into these files:

"I’ve tried about every tool under the sun; those CSB files refuse to open lol. Only luck I had was dragon unpacker’s Hyper Ripper which only got 8 files and not in a playable state.

If anyone else wants to take a shot feel free; I think whatever codec it’s in is not Criwave but rather some early version of ZSS or ZSM. Idk what that codec is but it refused to open in any criwave tools.

At best, we’ll only be able to open this thing if we can find some other way of ripping sound files (Vgmstream and foobar both didn’t work mind you) or if we could crack the codec but even then we have zero documentation on these files. Best case scenario is if we could test these in the demo somehow." (By demo he means the prototype).

I couldn't get the attachment to work, so I put the whole sound folder from the prototype on drive.

[https://drive.google.com/file/d/1YTVedV ... sp=sharing](https://drive.google.com/file/d/1YTVedVm3j64IsMDbGiKbtS3xKolp7B0E/view?usp=sharing)

Does anyone have any ideas on what to do?
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-10-26T20:51:54+00:00
- Post Title: Unknown CSB files from X-Men Legends prototype

Some extra info which might help ...

After the "CSX1" header, you've got what seems like a file type.  Some observations: If it's type 6, then it seems to be a single multi-channel stream (music/cutscene) - the value at offset 0x8 seems to be the number of channels (2 or 4).  If it's not type 6, then it's a bunch of mono audio files (count at offset 0x8, table at 0x18 with 0x20 bytes per entry).  The table contains sample rate, start offset, size and some other unknowns.

I've done some manual tests and a lot of them are standard XBOX ADPCM, particularly the mono files.  However, some of the multi-channels ones seem to be different - some are XBOX ADPCM and some look like another codec.

For multi-channel files the audio data seems to start at 0x11b8.  For mono files, they start at the next 0x200-byte block after the file table.
## Post #3
- Username: ofthriceandmen
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Dec 01, 2018 1:08 am
- Post datetime: 2021-10-26T21:32:34+00:00
- Post Title: Unknown CSB files from X-Men Legends prototype

So I've got some more info.

Here is some info about the final retail build's sound files for each console version from another Marvel Mods member when I asked about what you said:

"The sounds are all console-specific within the zsm file. Xbox uses XBADPCM, PS2 uses .vag I think, and the GameCube uses .dsp files. 
There isn't a PC version of X-Men Legends 1, but the PC version of X-Men Legends 2  uses .wav files
So it does make sense for them to conclude about XBADPCM"

Here are the sounds from the retail Xbox version for comparison:
[https://drive.google.com/file/d/11iq0Et ... sp=sharing](https://drive.google.com/file/d/11iq0EtAcSS3nJGbTVm6ZVI1Go-rFf_hN/view?usp=sharing)

And here's the zsm sound editor we use for the retail sounds:
[https://www.mediafire.com/file/tbqzfjob ... r.zip/file](https://www.mediafire.com/file/tbqzfjob972cfz4/Uploaded_2013-09-10_ZSMsoundeditor.zip/file)
## Post #4
- Username: ofthriceandmen
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Dec 01, 2018 1:08 am
- Post datetime: 2021-10-27T19:30:14+00:00
- Post Title: Unknown CSB files from X-Men Legends prototype

Also, the xmen_1.ctf file in the prototype sounds folder appears to be a list of all the files that are in x_common and all the files that are in that are in x_voice in the prototype.
## Post #5
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-10-28T19:13:34+00:00
- Post Title: Unknown CSB files from X-Men Legends prototype

The prototype audio is definitely all XBox ADPCM.  The attached QuickBMS script will extract the majority of the audio that can be played in Foobar with the vgmstream plugin.

The ones that don't extract perfectly, such as a_int_a are also XBox ADPCM but there's some weird interleave that I can't determine yet.


 xmen.zip
(892 Bytes) Downloaded 32 times
## Post #6
- Username: ofthriceandmen
- Rank: n00b
- Number of posts: 18
- Joined date: Sat Dec 01, 2018 1:08 am
- Post datetime: 2021-10-28T19:58:58+00:00
- Post Title: Unknown CSB files from X-Men Legends prototype

Thanks so much! We all really appreciate it! You're the greatest!
