## Post #1
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2012-03-19T19:48:48+00:00
- Post Title: PTMD format

Got some PTMD files from the black rock shooter model files, wondering if someone could have a quick look.
Ideally could do with getting them into 8 bit bitmap.

I've had a good look at them, seem to have a 16 byte header, followed by 128 byte blocks, followed by a palette (3 bytes color + 1 byte alpha) 
Don't know what the format is, looks like just an indexed palette with the data stored funny.
ptmd2 only has 16 colors in the palette but has more that 16 colors in the data.... 

Examples: [http://uppit.com/2w2g66o8jq08/ptmd.zip](http://uppit.com/2w2g66o8jq08/ptmd.zip)
(ptmd1.ptmd has extra data at the end, probably part of something else)

Anyone know the format or can help convert?
