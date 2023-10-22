## Post #1
- Username: [C]oopeZz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 25, 2018 3:12 am
- Post datetime: 2018-04-25T21:01:41+00:00
- Post Title: Wwise (IMA) ADPCM .wem format

Hello everyone,

Metal Gear Solid V using this format for most sounds for .bnk audio. Its .wem and its not the classic MS-ADPCM (microsoft's). It contains "JUNK" string, which make thinks harder and I still can't find correct RIFF header for this. To replace sound in this game, you must take the data from your .wem file and replace original data with it. Sadly, without correct RIFF header we are unable to edit things like "sample rate", "channels" and other important things. Do someone understand this format?
[File0717.rar](https://xentaxbackup.github.io/file/14278_File0717.rar)
## Post #2
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2018-04-29T06:38:59+00:00
- Post Title: Wwise (IMA) ADPCM .wem format

[https://github.com/MRWITEK/wwise-adpcm- ... reformat.c](https://github.com/MRWITEK/wwise-adpcm-to-wave-adpcm/blob/master/reformat.c) should help.
