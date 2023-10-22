## Post #1
- Username: BagelsYeah
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 06, 2016 6:57 am
- Post datetime: 2016-04-08T02:35:53+00:00
- Post Title: XBlaze: Code Embryo xactxtract Help .XWB

Hi I was wondering if there was a way to extract a XWB along with the cue names with a toolversion number of 46 and a format version of 43 with xactxtract ( or some other way)
## Post #2
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2016-04-09T01:35:42+00:00
- Post Title: XBlaze: Code Embryo xactxtract Help .XWB

The problem is that the cue names in the .xsb cannot be assigned uniquely to the (wav) files in the .xwb. A cue may contain several sounds and each sound may contain several tracks. The (unnamed) track entries in the .xsb point to the files in the .xwb.
## Post #3
- Username: BagelsYeah
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 06, 2016 6:57 am
- Post datetime: 2016-04-09T16:36:15+00:00
- Post Title: XBlaze: Code Embryo xactxtract Help .XWB

> Reply from Liandril
>
> The problem is that the cue names in the .xsb cannot be assigned uniquely to the (wav) files in the .xwb. A cue may contain several sounds and each sound may contain several tracks. The (unnamed) track entries in the .xsb point to the files in the .xwb.
The Thing is, the xwb in question has 645 files (.wav) and the correspoding xsb also has 645 cues

From your tool:

> INFO xbz_ep01.xsb: Version (46,43), 645 StdCues,0 ExtraCues, 645 Sounds
>
> 1 Wavebank(s): xbz_ep01
>
> 
>
> WARNUNG: xbz_ep01.xwb hat Toolversion 46 und Formatversion 44.
>
> xaXwb.pm unterstuetzt nur die Versionen 45 und 43
>
> ---WAVEBANK xbz_ep01.xwb: Version (46,44), Typ: Streaming, 645 Waves
## Post #4
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2016-04-10T13:50:30+00:00
- Post Title: XBlaze: Code Embryo xactxtract Help .XWB

You're right - in this case (where you have only 'standard cues', i.e. the same amount of cues and wave files) it would be possible to name the waves exactly like the cue names. Unfortunately, xactxtract is an old Perl script I wrote 7 years ago and the source code is somewhere on an old hard disk, so I can't release a new version right now.

If you use xactxtract without parameter, i.e.

```
xactxtract.exe xbz_ep01.xsb
```

you'll get a list of the cue names and the corresponding waves. Maybe you can use this list together with a good renaming tool in order to rename the extracted .wav files. I'm sorry that I can't offer you a better solution.
## Post #5
- Username: BagelsYeah
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 06, 2016 6:57 am
- Post datetime: 2016-04-10T14:28:34+00:00
- Post Title: XBlaze: Code Embryo xactxtract Help .XWB

> Reply from Liandril
>
> You're right - in this case (where you have only 'standard cues', i.e. the same amount of cues and wave files) it would be possible to name the waves exactly like the cue names. Unfortunately, xactxtract is an old Perl script I wrote 7 years ago and the source code is somewhere on an old hard disk, so I can't release a new version right now.

If you use xactxtract without parameter, i.e.
Code: Select allxactxtract.exe xbz_ep01.xsb
you'll get a list of the cue names and the corresponding waves. Maybe you can use this list together with a good renaming tool in order to rename the extracted .wav files. I'm sorry that I can't offer you a better solution.
The problem is it doesn't give me the corresponding waves it gives me

```
1 Wavebank(s): xbz_ep01
Cue-Name                      |Soundtyp | Wavebankname+Index
------------------------------|---------|----------------------------------
XB01_01_0009                   NonStd,19B
XB01_01_0011                   NonStd,19B
XB01_01_0013                   NonStd,19B
XB01_01_0015                   NonStd,19B
XB01_01_0017                   NonStd,19B
XB01_01_0018                   NonStd,19B
```


No corresponding waves, unless I'm missing something...
The .xwb is in the same location.
## Post #6
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2016-04-10T15:50:12+00:00
- Post Title: XBlaze: Code Embryo xactxtract Help .XWB

Hi,
if each cue was related to exactly one sound and each sound was related to exactly one track (pointing to a file in the .xwb), then the output would look like this:

```
------------------------------|---------|----------------------------------
EndScene5_title_stinger       ->Std->     MusicStreamingWaveBank_18     
EndScene1_head_rise           ->Std->     MusicStreamingWaveBank_19     
EndScene2_trigger_swirly_sound->Std->     MusicStreamingWaveBank_20 
```


In your case, you have 645 'standard' cues, but the sounds are non-standard (meaning they use more than one track/wave). On the other hand you have 645 wave files, which means that wave files are being used in more than one sound. So it's not possible to assign the cue names to the wave files (at least not with xactxtract), I'm afraid. These 'non-standard' cues and sound entries are really weird - they were the reason why I gave up further decoding of the xsb file format back then.
## Post #7
- Username: BagelsYeah
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 06, 2016 6:57 am
- Post datetime: 2016-04-10T18:04:45+00:00
- Post Title: XBlaze: Code Embryo xactxtract Help .XWB

> Reply from Liandril
>
> Hi,
if each cue was related to exactly one sound and each sound was related to exactly one track (pointing to a file in the .xwb), then the output would look like this:
Code: Select allCue-Name                      |Soundtyp | Wavebankname+Index
------------------------------|---------|----------------------------------
EndScene5_title_stinger       ->Std->     MusicStreamingWaveBank_18     
EndScene1_head_rise           ->Std->     MusicStreamingWaveBank_19     
EndScene2_trigger_swirly_sound->Std->     MusicStreamingWaveBank_20 

In your case, you have 645 'standard' cues, but the sounds are non-standard (meaning they use more than one track/wave). On the other hand you have 645 wave files, which means that wave files are being used in more than one sound. So it's not possible to assign the cue names to the wave files (at least not with xactxtract), I'm afraid. These 'non-standard' cues and sound entries are really weird - they were the reason why I gave up further decoding of the xsb file format back then.
That might make things really difficult, but okay. My next question, is there a way to find what cues go to the waves? However, I think I know the answer to that question.
## Post #8
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2016-04-10T20:38:49+00:00
- Post Title: XBlaze: Code Embryo xactxtract Help .XWB

> Reply from BagelsYeah
>
> That might make things really difficult, but okay. My next question, is there a way to find what cues go to the waves? However, I think answer to that question.
I only know how to read the standard entries (1 cue -> 1 sound and 1 sound -> 1 wave). The non-standard cue and sound entries are (as mentioned above) the 'weird ones' where I gave up   

In your .xsb the non-standard sound entries are the problem, so in case you want to try by yourself:
At offset 0x46 you'll find the 4B-Pointer to the sound section. A standard sound entry has 12B:

```
2B(?) category
1B(?) volume
3B    unknown
2B    length of the sound entry (for standard sounds: 0x0C = 12B)
2B    track index
1B    number of wavebank
```


All I know about non-standard sound is that the values for volume and length are at the same position as in standard sound entries.
## Post #9
- Username: BagelsYeah
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 06, 2016 6:57 am
- Post datetime: 2016-04-11T05:01:20+00:00
- Post Title: XBlaze: Code Embryo xactxtract Help .XWB

> Reply from Liandril
>
> BagelsYeah wrote:That might make things really difficult, but okay. My next question, is there a way to find what cues go to the waves? However, I think answer to that question.
I only know how to read the standard entries (1 cue -> 1 sound and 1 sound -> 1 wave). The non-standard cue and sound entries are (as mentioned above) the 'weird ones' where I gave up   

In your .xsb the non-standard sound entries are the problem, so in case you want to try by yourself:
At offset 0x46 you'll find the 4B-Pointer to the sound section. A standard sound entry has 12B:
Code: Select all2B(?) category
2B    volume
2B    unknown
2B    length of the sound entry (for standard sounds: 0x0C = 12B)
1B    unknown
2B    track index
1B    number of wavebank

All I know about non-standard sound is that the values for volume and length are at the same position as in standard sound entries.

Could you possibly upload an example of a .xsb with standard sound entries, Im gonna try my best to understand since these parts are kinda new to me.
## Post #10
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2016-04-11T20:20:29+00:00
- Post Title: XBlaze: Code Embryo xactxtract Help .XWB

Here's a very small .xsb containing 3 standard sound entries:

```
------------------------------|---------|----------------------------------
SHOT                          ->Std->     Wave Bank_0                   
BREAK1                        ->Std->     Wave Bank_1                   
BREAK2                        ->Std->     Wave Bank_2  
```

As described above, you can find the offset to the sound section at position 0x46: 0x00CA. Each standard sound entry is 12B long, so the data (hexadecimal) for the 3 entries are:

```
00 01 00 5a 00 00 00 0c 00 01 00 00     
00 01 00 5a 00 00 00 0c 00 02 00 00
```

This means (see the above description of standard sound entries) that all sound entries are standard  (value 0), category 2, volume 0x5a and length 0x0C (12B). The last 3B of each entry contain track index (00,01,02) and wavebank (00).

Please note that I changed the description of the sound entry after having a look at the small sample .xsb. Originally, I wrote down what I remembered about my research on sound entries, but that was 7 years ago
