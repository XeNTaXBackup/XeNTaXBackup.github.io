## Post #1
- Username: sammyrms1
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 06, 2016 9:37 am
- Post datetime: 2016-04-06T01:52:39+00:00
- Post Title: Hyperdimension Neptunia U .wwb sound files (SOLVED)

Around 2 weeks earlier, I downloaded Neptunia U when it was on sale on Steam. I looked through the sound files with a file format that I think is similar to .xwb. Is there a way to extract this type of file?
EDIT: Turns out the .wwb file was the same as an .xwb file, and the .wsb had 16 extra bytes before the header compared to .xsb (Thanks Liandril).
## Post #2
- Username: sammyrms1
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Apr 06, 2016 9:37 am
- Post datetime: 2016-04-22T23:39:03+00:00
- Post Title: Hyperdimension Neptunia U .wwb sound files (SOLVED)

Opened up the .wsb file with HxD, and it looks like the .wwb could work the same way as extracting a .xwb file with the .xsb filenames.
## Post #3
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2016-04-24T12:51:55+00:00
- Post Title: Hyperdimension Neptunia U .wwb sound files (SOLVED)

Hi sammyrms1,

the .wwb looks like a normal .xwb, but for some reason (maybe because it's an unsupported version) [xactxtract](http://forum.xentax.com/viewtopic.php?f=17&t=4391&p=43840&hilit=saint+row#p43840) cannot extract the files. Maybe unxwb can.

The .wsb is a modified .xsb. They put 16 additional bytes before the soundbank header ("SDBK"), so
delete the first 16 Byte of the .wsb with a hex editor
rename it to n00en.xsb
use xactxtract in order to correct the checksum:

```
xactxtract.exe -c n00en.xsb
```

Afterwards, you get the file info using

```

INFO n00en.xsb: Version (46,43), 286 StdCues,0 ExtraCues, 286 Sounds
1 Wavebank(s): n00en
Cue-Name                      |Soundtyp | Wavebankname+Index
------------------------------|---------|-----------------------------
n00act009140                  ->Std->     n00en_279
g00act001010                  ->Std->     n00en_0
g00act001020                  ->Std->     n00en_1
g00act001030                  ->Std->     n00en_2
g00act001040                  ->Std->     n00en_3
g00act001050                  ->Std->     n00en_4
g00act001060                  ->Std->     n00en_5
g00act002010                  ->Std->     n00en_6
g00act002020                  ->Std->     n00en_7
g00act002030                  ->Std->     n00en_8
g00act002040                  ->Std->     n00en_9
g00act002050                  ->Std->     n00en_10
g00act002060                  ->Std->     n00en_11
g00act002070                  ->Std->     n00en_12
g00act002080                  ->Std->     n00en_13
g00act002090                  ->Std->     n00en_14
g00act002100                  ->Std->     n00en_15
g00act003010                  ->Std->     n00en_16
g00act003020                  ->Std->     n00en_17
g00act003030                  ->Std->     n00en_18
g00act003040                  ->Std->     n00en_19
g00act003050                  ->Std->     n00en_20
...

```

Please note that the cue names in the .xsb are not the file names of the .xwb files. But in your case, every cue is assigned to exactly one file, so you can use the list provided by xactxtract together with an appropriate renaming tool in order to name the extracted files according to the cue names.
## Post #4
- Username: whfill
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 23, 2023 7:39 pm
- Post datetime: 2023-05-23T11:48:08+00:00
- Post Title: Hyperdimension Neptunia U .wwb sound files (SOLVED)

> Reply from Liandril ↑Sun Apr 24, 2016 8:51 pm at Sun Apr 24, 2016 8:51 pm
>
> 
Hi sammyrms1,

the .wwb looks like a normal .xwb, but for some reason (maybe because it's an unsupported version) xactxtract cannot extract the files. Maybe unxwb can.

The .wsb is a modified .xsb. They put 16 additional bytes before the soundbank header ("SDBK"), so
delete the first 16 Byte of the .wsb with a hex editor
rename it to n00en.xsb
use xactxtract in order to correct the checksum:
Code: Select allxactxtract.exe -c n00en.xsb
Afterwards, you get the file info using
Code: Select allD:\>xactxtract.exe n00en.xsb

INFO n00en.xsb: Version (46,43), 286 StdCues,0 ExtraCues, 286 Sounds
1 Wavebank(s): n00en
Cue-Name                      |Soundtyp | Wavebankname+Index
------------------------------|---------|-----------------------------
n00act009140                  ->Std->     n00en_279
g00act001010                  ->Std->     n00en_0
g00act001020                  ->Std->     n00en_1
g00act001030                  ->Std->     n00en_2
g00act001040                  ->Std->     n00en_3
g00act001050                  ->Std->     n00en_4
g00act001060                  ->Std->     n00en_5
g00act002010                  ->Std->     n00en_6
g00act002020                  ->Std->     n00en_7
g00act002030                  ->Std->     n00en_8
g00act002040                  ->Std->     n00en_9
g00act002050                  ->Std->     n00en_10
g00act002060                  ->Std->     n00en_11
g00act002070                  ->Std->     n00en_12
g00act002080                  ->Std->     n00en_13
g00act002090                  ->Std->     n00en_14
g00act002100                  ->Std->     n00en_15
g00act003010                  ->Std->     n00en_16
g00act003020                  ->Std->     n00en_17
g00act003030                  ->Std->     n00en_18
g00act003040                  ->Std->     n00en_19
g00act003050                  ->Std->     n00en_20
...

Please note that the cue names in the .xsb are not the file names of the .xwb files. But in your case, every cue is assigned to exactly one file, so you can use the list provided by xactxtract together with an appropriate renaming tool in order to name the extracted files according to the cue names.

Tried this for Diablo 4 wsb files, but not success
