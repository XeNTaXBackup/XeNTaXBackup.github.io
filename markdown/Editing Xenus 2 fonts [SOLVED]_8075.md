## Post #1
- Username: myers
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 26, 2010 12:52 am
- Post datetime: 2012-01-17T15:20:47+00:00
- Post Title: Editing Xenus 2 fonts [SOLVED]

Hi!

I have a problem. I would like to edit the fonts in Xenus 2. So the fonts are in .FNT files, what contains DDS file in the file's "end" so if I cut out the other things before the DDS start, and I save it as DDS, I can load it to Photoshop, or other and edit this DDS. Its okay, but I can't find a way to save the exactly same type of DDS, what the original. I took a look to the original DDS with WTV, and I found something, what I don't know how to do. The WTV says for the original file: "Mem:256.0KB/516.2KB"
But if I edit the file and save with Photoshop (as 8.8.8.8 ARGB 32bp | unsigned, like the original format) I get Mem: 256.0KB/256.0KB in WTV and of course half size of file.
If I try to run the game with this "half sized" DDS, I get error (Unable to create impostor texture.). 

I attached the cutted DDS, and the .FNT too.
[Fonts.rar](https://xentaxbackup.github.io/file/5000_Fonts.rar)
## Post #2
- Username: myers
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 26, 2010 12:52 am
- Post datetime: 2012-01-20T08:57:56+00:00
- Post Title: Editing Xenus 2 fonts [SOLVED]

Okay, its solved. I just had to modify the whole files length in the file, at 0x30C and at 0x408 (on 4 bytes).
## Post #3
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2012-08-07T19:16:48+00:00
- Post Title: Editing Xenus 2 fonts [SOLVED]

Could somebody please explain how this is done? Thanks you in advance.
