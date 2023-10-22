## Post #1
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2006-04-22T12:58:52+00:00
- Post Title: True Crime: New York City language and (possibly) textures

Hello there, I would like to ask you guys if you could help me in two things:

The first one is that if you can make some sort of text converter for the files shown at the ENG folder of the zip file, and the second one would be to ask you if in the .tag files are any textures that can be edited.
## Post #2
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2006-04-22T12:59:50+00:00
- Post Title: True Crime: New York City language and (possibly) textures

The file with the textures...
## Post #3
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2006-04-22T16:52:21+00:00
- Post Title: True Crime: New York City language and (possibly) textures

For The Text Files:

[4] Bytes - Table Size  / 8 = Number of Files

Table
[4] Bytes - Hash/ID?
[4] Bytes - Offset to text after Table ends. (Offset + TableSize)

Text are Null Terminated.

For Textures (only looked briefly)
[4] Bytes - Number of Files * 16 = Table Size

Table 
[8] Bytes Unknown
[2] Bytes - Maybe Type?
[2] Bytes - Unknown
[4] Bytes - Offset (Current location + offset)


Images are DXTn
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-04-22T17:32:14+00:00
- Post Title: True Crime: New York City language and (possibly) textures

textures definitely DXT. without a header as usual. only me whos starting to see a trend among the new games here? =/
## Post #5
- Username: PierreDeVega
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 14, 2006 11:32 pm
- Post datetime: 2006-06-06T10:15:29+00:00
- Post Title: True Crime: New York City language and (possibly) textures

Someone could be explain me, where from it is known that textures are DXT?
