## Post #1
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-04-23T17:23:21+00:00
- Post Title: Understand Metadata from an unknown audio file

I'm trying to understand the audio of a rather mysterious WAV file extracted from AFC archive.

Mediainfo says this

> Format                                   : Wave
>
> File size                                : 288 KiB
>
> Duration                                 : 28s 941ms
>
> Overall bit rate                         : 81.6 Kbps
>
> 
>
> Audio
>
> Format                                   : In Development
>
> Codec ID                                 : FFFF
>
> Duration                                 : 28s 941ms
>
> Bit rate                                 : 81.6 Kbps
>
> Channel(s)                               : 2 channels
>
> Sampling rate                            : 32.0 KHz
>
> Stream size                              : 288 KiB (100%)

while the first lines of Hex editor say this

RIFF (little-endian) data, WAVE audio, stereo 32000 Hz

> 00	01	02	03	04	05	06	07	08	09	0A	0B	0C	0D	0E	0F	0123456789ABCDEF
>
> 000000	52	49	46	46	39	81	04	00	57	41	56	45	66	6D	74	20	RIFF9...WAVEfmt 
>
> 000010	28	00	00	00	FF	FF	02	00	00	7D	00	00	D2	27	00	00	(........}...'..
>
> 000020	00	00	00	00	16	00	18	00	03	00	00	00	01	00	00	00	................
>
> 000030	00	00	10	00	80	00	00	AA	00	38	9B	71	63	75	65	20	.........8.qcue 
>
> 000040	1C	00	00	00	01	00	00	00	01	00	00	00	00	00	00	00	................
>
> 000050	64	61	74	61	00	00	00	00	00	00	00	00	00	00	00	00	data............
>
> 000060	4C	49	53	54	1E	00	00	00	61	64	74	6C	6C	61	62	6C	LIST....adtllabl
>
> 000070	12	00	00	00	01	00	00	00	54	65	6D	70	6F	3A	20	31	........Tempo: 1
>
> 000080	33	37	2E	30	00	00	76	6F	72	62	34	00	00	00	4B	16	37.0..vorb4...K.
>
> 000090	0E	00	CD	03	00	00	00	00	00	00	D0	0E	00	00	0A	01	................
>
> 0000A0	00	00	A4	7C	04	00	88	03	00	00	58	12	00	00	6D	01	...|......X...m.
>
> 0000B0	00	00	EC	37	00	00	AC	39	00	00	42	68	A4	5C	08	0B	...7...9..Bh.\..
>
> 0000C0	00	00	64	61	74	61	77	80	04	00	00	00	00	00	D0	0E	..dataw.........
>
> 0000D0	00	00	C0	22	00	00	EA	1A	00	00	C0	42	00	00	04	25	...".......B...%
>
> 0000E0	00	00	C0	62	00	00	ED	2E	00	00	C0	82	00	00	1F	39	...b...........9
>
> 0000F0	00	00	C0	A2	00	00	2F	43	00	00	C0	C2	00	00	35	4D	....../C......5M
>
> 000100	00	00	C0	E2	00	00	30	57	00	00	C0	02	01	00	19	61	......0W.......a
>
> 0000B0	00	00	EC	37	00	00	AC	39	00	00	42	68	A4	5C	08	0B	...7...9..Bh.\..
>
> 0000C0	00	00	64	61	74	61	77	80	04	00	00	00	00	00	D0	0E	..dataw.........

Do you guys have any idea of 
1-how to play the file
and
2-how to understand metadata in it, specifically loop points

?
## Post #2
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-04-28T10:16:44+00:00
- Post Title: Understand Metadata from an unknown audio file

Anyone? I tried WW2ogg but all data inside the file is lost.
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-04-28T12:43:10+00:00
- Post Title: Understand Metadata from an unknown audio file

Upload a sample
## Post #4
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-04-28T14:48:22+00:00
- Post Title: Understand Metadata from an unknown audio file

Obvious, silly me. if that is permitted, I will do it now.

There it is.
[https://mega.co.nz/#!N5MT2SDB!gkXs5HHfi ... fgxmHwDT1g](https://mega.co.nz/#!N5MT2SDB!gkXs5HHfi7r3dtBHfwCd-cN3O6REsUr_AfgxmHwDT1g)
## Post #5
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-05-01T11:51:54+00:00
- Post Title: Understand Metadata from an unknown audio file

no idea at all?
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-05-01T13:13:02+00:00
- Post Title: Understand Metadata from an unknown audio file

```
pause
```


Save that into a .bat file and it will convert it just fine.

The file needed the "--full-setup" option to be decoded
## Post #7
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-05-01T15:36:53+00:00
- Post Title: Understand Metadata from an unknown audio file

thanks, but why that works? I tried opening the wav in WWise but it wouldn't work (file .wav)

will it also save metadata information such as loop points?
## Post #8
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-05-01T23:19:22+00:00
- Post Title: Understand Metadata from an unknown audio file

nope. no metadata is found. no loop points, nothing. and I know they are there..
## Post #9
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-05-02T09:40:04+00:00
- Post Title: Understand Metadata from an unknown audio file

Update: I have found sample data and label data. using RIFFpad.

the fadeout I hear at the end is identified as "junk at the end of the file" by riffpad, and some files sport the SMPL information the author of  ww2ogg mentioned to hold loop information.

all this is visible only if the file is WAV or RIFF file. it is not possible to see them if it is converted to ogg. Notepad++ can see this information, as can RIFFpad.

now, if there was a way to delete all junk data automatically..
