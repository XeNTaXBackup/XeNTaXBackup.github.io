## Post #1
- Username: Troglodit
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 11, 2009 8:37 am
- Post datetime: 2009-03-11T13:02:11+00:00
- Post Title: Xenon 2 megablast need help

Hello all! 
I want to remake retro game "Xenon 2 megablast" on Flash platform (you can get it here: [http://www.abandonia.com/en/games/42/Xe ... blast.html](http://www.abandonia.com/en/games/42/Xenon+2+Megablast.html))
Some progress Is done alredy but it is too slow to copy sprites from screenshoots.
Can you halp me please to extract the *.vga graphic files or to understand it structure.

Thank you
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-03-11T19:53:15+00:00
- Post Title: Xenon 2 megablast need help

Here is a scan of the file.


  offset   num  description [bits.endian.size]
  --------------------------------------------
  000181c2 370  LZ Huffman decoding table [..256]
  000182c2 1663 Huffman LZH d_len [..256]

- 2 signatures found in the file

seems like a compressed archive that contains the gfx data.
