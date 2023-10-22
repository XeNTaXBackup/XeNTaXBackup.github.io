## Post #1
- Username: dedumpf
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 11, 2016 2:06 am
- Post datetime: 2016-08-10T18:53:20+00:00
- Post Title: Bayonetta 2 Extracting stream files from DAT files

Hello. I've been trying to extract some sfx files from bayonetta 2 files I have. I've been following this thread for the most part [viewtopic.php?f=17&t=14141&hilit=bayonetta](http://forum.xentax.com/viewtopic.php?f=17&t=14141&hilit=bayonetta), but I'm using a different quickBMS script for extracting wavs from the bnk files. 

```
Get SECTION_SIZE long
If SECTION_SIZE > 0xFFFF
ReverseLong SECTION_SIZE
Endian BIG
EndIf
GoTo SECTION_SIZE 0 SEEK_CUR
Get BNK_SIZE asize

Do
GetDString SECTION_NAME 4
Get SECTION_SIZE long
If SECTION_NAME == "DIDX"
  SavePos DIDX_OFFSET
  Math FILES = SECTION_SIZE
  Math FILES /= 12
ElseIf SECTION_NAME == "DATA"
  SavePos DATA_OFFSET
EndIf
GoTo SECTION_SIZE 0 SEEK_CUR
SavePos POS
While POS < BNK_SIZE

GoTo DIDX_OFFSET
For I = 0 < FILES
Get FID long
Get FOFFSET long
Get FSIZE long
String FNAME p= "%08X.wav" FID
Math FOFFSET += DATA_OFFSET
Log FNAME FOFFSET FSIZE
Next I
```


After extracting with the wav, I decode with the Imajigger5 but I don't have the stream files (and I'm dont know where to get them) so the wav only plays a second or so before EOF.


Any help would be much appreciated. Thank you.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-10T20:00:00+00:00
- Post Title: Bayonetta 2 Extracting stream files from DAT files

I'm not really following you... if you extract the RIFX at 0x100 in voe027_us.dat, you can decode that with ima_rejigger5 for a noisy but seemingly complete voice sample. Actually there are a few in there, also at 0x4300 and 0x5580. Attached is the decoded wavs.
[voe027_us wavs.zip](https://xentaxbackup.github.io/file/11538_voe027_us wavs.zip)
## Post #3
- Username: dedumpf
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 11, 2016 2:06 am
- Post datetime: 2016-08-10T20:08:23+00:00
- Post Title: Bayonetta 2 Extracting stream files from DAT files

I'm completely new to modifying sound files and quickbms and the sort so I am just following this thread [viewtopic.php?f=17&t=14141&hilit=bayonetta](http://forum.xentax.com/viewtopic.php?f=17&t=14141&hilit=bayonetta). Did you break up the files by looking at the dat file with hex editor? 

What I did was use quickbms to extract wav files from a sound bnk file I have. Then I need to decode the wav/wem file with imjigger5 to be able to play it. Bayonetta 2 uses the ipa_adpec wwise codec so I'm not sure if that means bnk files only contain a small portion of the audio file and the rest of the file is streamed through another file. 

The files I extract from the bnk file go to an unexpected EOF but I can see the length of the file is much longer (44s for this file but only plays for a second). 


Could you tell me how to extract the wav files from the dat? I see the offset RIFX ids at the offsets you told me but I dont know how to do that.
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-10T20:16:53+00:00
- Post Title: Bayonetta 2 Extracting stream files from DAT files

I think you should just need to run the RIFF/RIFX scanner BMS on the .dat, or just directly on the .cpk.
## Post #5
- Username: dedumpf
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 11, 2016 2:06 am
- Post datetime: 2016-08-10T20:33:56+00:00
- Post Title: Bayonetta 2 Extracting stream files from DAT files

Thanks for all your help with the DAT files. Got the wavs from the DAT using Ravioli Scanner and Renaming to .wem and using the wems on imajigger5. You're Awesome.



I still need help with the other problem where my extracted wem from the sound bnk file does not play fully because I don't have the stream files(and I don't know what stream files are).

I think I need to do something like this: [viewtopic.php?f=17&t=13762&hilit=wwise+wwise+ima+adpcm](http://forum.xentax.com/viewtopic.php?f=17&t=13762&hilit=wwise+wwise+ima+adpcm)

The bit squid program daemon1 has requires a stream file to extract fully.

> Reply from daemon1
>
> 
bitsquid_timpani [bank file name] [stream file name]

Audio bank unpacker for other games. It requires stream name too. If there's no stream for some particular bank, just type anything you want for second parameter. If you run it with 1 parameter, the result is unpredictable. If the stream will not be present, it will work, but files may be cut, having only some first seconds of sound.

About the .stream files

Streams are just an "addition" to the bank, you can't extract it without the bank. Bank files have extension "timpani_bank" and they are extracted from the packages with all the other files. During this process, the main stream file is also been cut into parts (small stream files) that are corresponding to each bank contained within a package.

I need some help with exactly how to extract/decode wems so that they play more than the first couple of seconds.
