## Post #1
- Username: SonofKalas
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Aug 27, 2015 5:42 am
- Post datetime: 2015-11-23T03:15:34+00:00
- Post Title: Skulls of the Shogun - XSB XWB Audio looping

Hi, I've Extracted audio from an XWB file and Isolated the ones I want. but the files are unlooped. I'm certain that the BGM files rather then being split into segments to loop them , loop internally, by which i mean that the game plays the audio file and then when it hits the end of the file it starts the same file Again from a specific time stamp somewhere within the same file. The problem is I don't know where that info is stored. Included are both XWB and corresponding XSB as well as the tool i extracted them with. I was hoping someone could help me find the time stamps that the files loop to, which i believe are in the xsb (which i don't know how to open in a human readable way). any help would be appreciated

[https://mega.nz/#!aNQnTTDY!yXGbwO-BKEji ... xqxUzOOrjI](https://mega.nz/#!aNQnTTDY!yXGbwO-BKEjiK8c-vBBUD1AtJBG4x7A3xxqxUzOOrjI)

the info might also be in this xgs, but i can't find anything to open it
[https://mega.nz/#!iJgAkKaD!8HPrUvhDOrWt ... tBORCOxvlk](https://mega.nz/#!iJgAkKaD!8HPrUvhDOrWtkST4Ov_07melgkoiKn6wltBORCOxvlk)

It's only the following files i need the loop time for

MusicStreamingWaveBank_00000.xwma
MusicStreamingWaveBank_00002.xwma
MusicStreamingWaveBank_00004.xwma
MusicStreamingWaveBank_00010.xwma
MusicStreamingWaveBank_00011.xwma
MusicStreamingWaveBank_00013.xwma
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-11-23T16:39:56+00:00
- Post Title: Skulls of the Shogun - XSB XWB Audio looping

Might need to actually post a link there first
## Post #3
- Username: SonofKalas
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Aug 27, 2015 5:42 am
- Post datetime: 2015-11-23T17:12:23+00:00
- Post Title: Skulls of the Shogun - XSB XWB Audio looping

oops my bad I thought i had
## Post #4
- Username: SonofKalas
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Aug 27, 2015 5:42 am
- Post datetime: 2015-11-23T17:35:12+00:00
- Post Title: Skulls of the Shogun - XSB XWB Audio looping

Link is up now
## Post #5
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2015-11-24T18:57:00+00:00
- Post Title: Skulls of the Shogun - XSB XWB Audio looping

Hi SonofKalas,

I'm the author of xactxtract - nice to see that my old perl script is still in use. Unfortunately, XACT (the tool .xwb (Wavebanks) and .xsb (Soundbank) files are created with and part of Microsofts DirectX SDK) is AFAIK not able to load existing .xwb and .xsb files. So you can't get the looping information by just using Microsofts XACT, but you're right: the looping information is in the .xsb.

.xsb files consist of cues (the 'interface' to the game, sort of a playlist), which contain sounds. Each sound may have one or more tracks. Tracks again point to the files in the wavebank. Unfortunately I don't even know if sound properties or track properties contain the looping information you're looking for. 

xactxtract gives you at least some information:

```
xactxtract.exe MusicBank.xsb
```

will give you information about how cues, sounds, tracks and wavebank files are related.
The wavebank files that you listed are not shown in this information which means they have to be in the cues 
TitleMusic, BeachMusic, CutScene1Mix, SpringMusic, SummerMusic, FallMusic, WinterMusic and/or Outro.

I hope this helps as a start. Sorry that I don't have more information.
## Post #6
- Username: SonofKalas
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Aug 27, 2015 5:42 am
- Post datetime: 2015-11-25T00:37:12+00:00
- Post Title: Skulls of the Shogun - XSB XWB Audio looping

Thank you for taking notice and responding
The command you mentioned is one i tried. I came here because it didn't provide the info i was looking for. 
The game in question is skulls of the shogun. If anyone has any info on how to access the looping info or where it is stored please let me know.
