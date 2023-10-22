## Post #1
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-06-13T09:35:29+00:00
- Post Title: [PS2] KOF maximum impact 2

ok here are some files extracted from the ps2 game king of fighter maximum impact 2, those files seems to use some LZs compression 
magic = PK
version = 2
filesize decompressed : integer
then 2 integer padding (for ps2 16 byte alignement)
then the compressed data

aluigi, could you have a look at it ?

pak sample files :
[http://www.mediafire.com/?34zzzztez3q](http://www.mediafire.com/?34zzzztez3q)

extracted compressed pk file :
[http://www.mediafire.com/?n5mnqm1wyng](http://www.mediafire.com/?n5mnqm1wyng)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-13T10:44:56+00:00
- Post Title: [PS2] KOF maximum impact 2

I noticed the start header goes 
magic long
unk 8 bytes
filecount long
then the start offset of the pk headers as a long value x the number of files.
