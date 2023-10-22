## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-26T22:06:45+00:00
- Post Title: Tom Clancy's Ghost Recon: Advanced Warfighter *.SS1/*.SS2

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2010-02-03T13:12:46+00:00
- Post Title: Tom Clancy's Ghost Recon: Advanced Warfighter *.SS1/*.SS2

Xbox version= xbadpcm 
You can use Luigis Xbox ADPCM decoder
[http://aluigi.org/papers.htm#xbox](http://aluigi.org/papers.htm#xbox)

Dont forget to look for the correct stream beginning. The container has a few tracks separated by by zero blocks.
First file Offset 0, second offset 4B800 - there are no header inside this container 


Ps2 version: Where are the vox files? - Have found only ps2 adpcm. Offset?
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-02-03T15:31:07+00:00
- Post Title: Tom Clancy's Ghost Recon: Advanced Warfighter *.SS1/*.SS2

> Reply from Kataah
>
> Xbox version= xbadpcm 
You can use Luigis Xbox ADPCM decoder
http://aluigi.org/papers.htm#xbox

Dont forget to look for the correct stream beginning. The container has a few tracks separated by by zero blocks.
First file Offset 0, second offset 4B800 - there are no header inside this container
When I try to play the file with ADPCMdecoder (which should work), I only get gibberish. That's why I asked here. 
Could you tell me the exact command line ou used to correctly extract and convert the file I uploaded?

> Reply from Kataah
>
> Ps2 version: Where are the vox files? - Have found only ps2 adpcm. Offset?
Well I just thought they were vox files... Ok, PS2 ADPCM then.  Could you tell me how to convert the different formats inside the SS1? Thanks!
## Post #4
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2010-02-03T16:06:06+00:00
- Post Title: Tom Clancy's Ghost Recon: Advanced Warfighter *.SS1/*.SS2

Dont try to play such files.
xbadpdec.exe mp_01_nl.SS2 stream.wav thats all but like i said you need for all tracks the correct stream beginning.

Same with the ps2 version - go to offset 227810 to convert the next track
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-02-06T23:24:50+00:00
- Post Title: Tom Clancy's Ghost Recon: Advanced Warfighter *.SS1/*.SS2

I can decode the XBox files with the offset after the zero block - but the stream is scratched! What can I do?

About the PS2 version: after decoding you'll notice some kind of interleave change about 3.5 seconds before the end of every decoded stream. How can I cope with this? Best example is the third stream in the uploaded ps2 file. Sounds just awful...
