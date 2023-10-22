## Post #1
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-05-14T07:46:00+00:00
- Post Title: Help by decrypt strange .tga files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-05-14T09:45:36+00:00
- Post Title: Help by decrypt strange .tga files

oh i forgot...

there are some jpg files in also in the same folder

I have xored them 0xff and that works... 

But when i xor the .tgas i get a file where the signature seems correct and displayd plain TRUEVISION-XFILE in the last 26 bytes, but the filde wont open.  So there must be something i cant figure out with my really little experience on that.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-14T10:22:36+00:00
- Post Title: Help by decrypt strange .tga files

It is just missing the header just grab a tga file about the same size and copy the header from that.
## Post #4
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-05-14T10:55:36+00:00
- Post Title: Help by decrypt strange .tga files

ahhh. thank you, that was not the 100% the right tip but i helped me to work it out 

You just have to xor it and then cut of the first 8 bytes which are garbage 

Thx
