## Post #1
- Username: Slappy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jul 17, 2012 5:28 pm
- Post datetime: 2023-01-05T08:23:09+00:00
- Post Title: Star Trek Away Team fonts .seq16 .fmt16

Hi.

Can anyone help me with fonts from Star Trek Away Team game (Commandos style) in .seq16 / .fmt16 format? I need to convert them to some editable bitmap and back.

This is a Reflexive game on the same engine as Lionheart: Legacy of the Crusader game but it looks like the format is slightly modified.

I found some information about the used formats at [http://lionheart.eowyn.cz/doku.php?id=formats:frm16](http://lionheart.eowyn.cz/doku.php?id=formats:frm16) and [http://lionheart.eowyn.cz/doku.php?id=formats:seq16](http://lionheart.eowyn.cz/doku.php?id=formats:seq16)


I have uploaded Fonts from game (.seq16) which I believe is a container for a bitmap (.fmt16) which I also included: [https://ufile.io/kehzf8b4](https://ufile.io/kehzf8b4)

FRM16

*.frm16 files are simple bitmap images, used for many things like UI elements, icons, minimaps, textures, portraits … In Lionheart, even more of them is actually embedded as frames in .SEQ16 and .MDL16 files. They use 16 bits per color and 8 bits for transparency (the older format probably used between 2 and 3 bits for transparency).

 FRM16 file consists of a header and up to five layers. Each layer consists of pixel data followed by a lookup table to first pixels of each image row.

Depending on a file type, pixels are either uncompressed (type 64), or RLE-compressed (file type 68). Only the type 68 allows transparency.
