## Post #1
- Username: Pinkertonius
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 26, 2010 11:52 am
- Post datetime: 2012-11-12T16:45:14+00:00
- Post Title: Elderscolls 1: Arena - need help with compressed (?) images

Hello,

I have been attempting a texture overhaul for the Elderscrolls 1:Arena. Most image files can be loaded raw with the palette file for editing but a small handful have some compression and won't load (at least correctly) using this method. I gave a go at examing them in a hex editor. All I could make out was that the first 9 bytes were always "00 00 00 00 40 01 CB 00 01". I did some net searching too and couldn't find any hits about it at all (in fairness it's really old now). Any help on figuring this out would be appreciated.

[Here are the files giving me fits](https://www.dropbox.com/s/zya806olqxa7dp2/ARENA%20samples.zip)

EDIT: Realized the 40 01 CB 00 was the file size (320 x 200). I forgot about Little Endian since I don't do much of this stuff. Still don't know the rest though so...help?
