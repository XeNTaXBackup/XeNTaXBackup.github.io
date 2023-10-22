## Post #1
- Username: Malachi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 12, 2004 9:53 am
- Post datetime: 2009-07-21T19:03:00+00:00
- Post Title: Death Rally .bpk images

Can someone help me figure out Death Rally .bpk graphic file format?
My research hasn't revealed anything except it's some sort of 8-bit compressed format with outside palette file. I couldn't even figure out header structure (height, width, etc.). While testing it by changing values in images and having the game load changed images, compression seemed like some sort of rle with sliding window or dictionary. If some wants to test it I recommend starting with archive menu.bpa (it's uncompressed) and looking/changing bytes of apogee.bpk image  (which is stored in it) as it is the first image game displays when starting.

I attached two images with they captures from game. Others can be extracted from Death Rally .bpa files.
While the Death Rally .bpa game archive format is unknown to me, it can be extracted with [Game Archive UnPacker 0.6.0.2 PRO](http://forrox.narod.ru/gaup_en.htm).
[drbpk.zip](https://xentaxbackup.github.io/file/2219_drbpk.zip)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-28T21:35:09+00:00
- Post Title: Death Rally .bpk images

Now this is interesting, I hope someone can find the answer here. If I have time I may take a look myself.
## Post #3
- Username: Malachi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 12, 2004 9:53 am
- Post datetime: 2009-07-29T16:48:52+00:00
- Post Title: Death Rally .bpk images

After checking further I have no idea what kind of compression it is. Changing random bytes in image and having it loaded by the game most of the time shows only local distortions and rest of the image is decoded properly (offset left or right). Also changing the bytes to see if they correspond to palette index proved useless as apparently they don't so maybe even huffman coding is involved?

Edit:
I made some progress. After saving captured APOGEE.PNG as GIF and opening it in hex editor, I noticed similarities between BPK and GIF files when watched in 18 bytes column widths (filesizes are also comparable). I will continue attacking it from that angle.
## Post #4
- Username: Malachi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 12, 2004 9:53 am
- Post datetime: 2009-07-31T23:37:51+00:00
- Post Title: Death Rally .bpk images

Looks like compression is definitely LZW similar to one found in GIF. Also there appears to be no header information, could be that game has it hardcoded. I managed to decode images partially with modified GIF decoder but the color indexes are wrong and decoding stops after first image block.
I'll continue attacking it.  

Edit:
Compressed files have no header, but some decompressed files have header.

Edit2:
Maybe Compressed files and methods subforum would be more suitable now that it appears .bpk files are compressed files with different contents.
## Post #5
- Username: Malachi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 12, 2004 9:53 am
- Post datetime: 2009-08-02T19:21:23+00:00
- Post Title: Death Rally .bpk images

After struggling to get LZW decoder working in a moment of inspiration I swapped codes for clear code and ending code (opposite from GIF codes and with no block code) and it worked!   
Almost whole files decompress now, color indexes are still bad, need to figure out why. Work continues.
[outfile.png](https://xentaxbackup.github.io/file/2250_outfile.png)
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-08-02T20:22:12+00:00
- Post Title: Death Rally .bpk images

Nice work man! Keep it up!
## Post #7
- Username: Malachi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 12, 2004 9:53 am
- Post datetime: 2009-08-02T20:48:08+00:00
- Post Title: Death Rally .bpk images

Thanks!   

I've figured out why indexes are wrong. Need to do bitwise rotation of 5 to right (or 3 to left) on output bytes.
