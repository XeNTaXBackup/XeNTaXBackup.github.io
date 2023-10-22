## Post #1
- Username: curlyfriesonionrings
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 05, 2012 9:51 pm
- Post datetime: 2012-09-22T18:48:19+00:00
- Post Title: [PS2] Odin Sphere .ftp files

Hello,

I need some help extracting images from .ftp files from the PS2 Vanillaware game Odin Sphere. The files came from a DISC.CVM file from the CD that is either encrypted or compressed (I can't tell). I pulled the files from the CVM by looking at the TOC in an eeMemory.bin file. Here are some pictures of the headers of some .ftp files.





I can deal with the main header that starts with "FTEX", but I'm not sure where to go from there. It looks like the file contains .TM2 images, but having come from an encrypted/compressed file, I can't turn them into .png files. I have full file samples too if anyone wants a look, but I'm not sure how to put them up.

Any help would be appreciated. Thanks.
## Post #2
- Username: curlyfriesonionrings
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 05, 2012 9:51 pm
- Post datetime: 2012-10-29T01:11:01+00:00
- Post Title: [PS2] Odin Sphere .ftp files

I've found some extracts that someone was able to pull from the Japanese version of the game. The extracts from this person aren't named the same as the files from the disc, so it's a bit difficult trying to match the image with the .ftp file. I do think I found the .tm2 file that is contained in the "axeknight_npc.ftp" file in my previous post.



So a new question I have is: given the decompressed/decrypted result, is it possible to figure out the encryption method used?

I'm thinking if this algorithm can be figured out this way, then I can decrypt all the .ftp files I have.

Many thanks to those interested.
## Post #3
- Username: RangerRus
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Apr 19, 2011 1:17 am
- Post datetime: 2013-04-27T19:37:12+00:00
- Post Title: [PS2] Odin Sphere .ftp files

This files are not crypted/compressed.
