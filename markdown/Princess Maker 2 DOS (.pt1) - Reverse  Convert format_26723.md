## Post #1
- Username: Perception
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 02, 2023 9:04 pm
- Post datetime: 2023-05-02T13:33:24+00:00
- Post Title: Princess Maker 2 DOS (.pt1) - Reverse / Convert format

Hello!

I'm trying for fun (and learn) to reverse engineer the old DOS file format .PT1 from the game Princess Maker 2, but I'm too noob in the reverse stuff to get to a decent state. I'm wondering if anyone here is able to help me.

I was able to extract the files from the .lbx containers, and I have what they look like in the .bmp format from the Princess Maker 2 Windows 3.1 version.

I would assume the .pt1 file format is something of a 4-bit (RLE or not, compressed?) palettized DOS format. I was able to figure out (the easy part I guess) that the height of the file might be at byte 08-09 from the start of the file, but for the life of me I can't even find the width!

CIPBSN.PT1 (48x64) -0x 40 00 -> 64

```

```


CIPBSN.PT1 (64x64) -0x 40 00 -> 64

```

```


FXNUM.PT1 (80x16) -0x 10 00 -> 16

```

```


I know supposedly arc_conv can convert them to TGA, (pt1>TGA) but I can't understand if the program even does anything, and I can't seem to figure out the .asm (maybe only is able to handle the .lbx containers?):
[https://github.com/amayra/arc_conv/blob ... pm2lbx.asm](https://github.com/amayra/arc_conv/blob/master/arc_conv/arc_pm2lbx.asm)

Anyone with more experience can give me some clues/ideas what to do next?
[testfiles.7z](https://xentaxbackup.github.io/file/23759_testfiles.7z)
