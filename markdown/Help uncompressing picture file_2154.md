## Post #1
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-15T06:39:51+00:00
- Post Title: Help uncompressing picture file

Hello :) I was hoping someone could help me out and tell me what type of compression does this picture uses

the uncompressed tim2 is not the same file as the compressed one but it has the same proportions so the output should only difere in picture data

the  uncompressed size is 256*256(pixels)+1024(pallet)+256(header) 66816 bytes

both headers have the exact same data
[files.rar](https://xentaxbackup.github.io/file/920_files.rar)
## Post #2
- Username: szevvy
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Sep 21, 2006 2:20 pm
- Post datetime: 2006-10-15T14:41:24+00:00
- Post Title: Help uncompressing picture file

Can you put up a compressed and uncompressed version of the same file?  "Differing in picture data" means that the vast majority of data is useless as we can't compare the two.

edit: although, if you're sure the two headers are the same that gives 256 bytes to work with, I guess.
## Post #3
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-15T18:10:02+00:00
- Post Title: Help uncompressing picture file

yes :( sadly only the header is the same

I did not find any 100% equal file but from the header alone I can see it
uses some sort of RLE that compressed repeated data
I didn't find the literal character so I guess it might use come sliding window but compression is not my strong point :(

also I opened the compressed picture to "visualize it"  and the  compression add 0000 every 32 bytes or more resulting in vertical scan lines in the picture hehe

I hope someone can get at least a clue as to what compression it uses

thank you for your help :)

Thisgs I know:
Headers have same data- first 256 bytes
the pallet is always at the end 1024 bytes
the pallet consists of 4 bytes with the last value always being FF
The uncompressed file size is the same as the uncompresed tim
the compression adds 0000 flollowed by some number( eg E2CD)
every 32 bytes or so...
[compressed picture.gif](https://xentaxbackup.github.io/file/922_compressed picture.gif)
## Post #4
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-10-19T04:57:32+00:00
- Post Title: Help uncompressing picture file

How's that?


4 bottom rows is palette in this order :
R (red value) B (blue value) G (green value) FF and so on 256 x
To titred to extract now but maybe tomorow to give this pic nice colors.
## Post #5
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-19T06:33:57+00:00
- Post Title: Help uncompressing picture file

Yes the uncomrpessed tims are pretty straight forth :)

but I'm interested in the compressed ones, I want to uncompress them or to atleast have a clue as to what compression they use

the compressed tims(picture I posted) are the ones that have the texture data
## Post #6
- Username: john_doe
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2006-10-19T07:53:37+00:00
- Post Title: Help uncompressing picture file

Which game uses these files?
Can you upload the game's exe somewhere?
## Post #7
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-19T08:45:11+00:00
- Post Title: Help uncompressing picture file

The game is biohazard outbreak for ps2

the executable is an elf - executable and linkable format
[http://rapidshare.de/files/37307206/elf.RAR.html](http://rapidshare.de/files/37307206/elf.RAR.html)

I'm really tired ZZzz =_= good night
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-21T22:21:32+00:00
- Post Title: Help uncompressing picture file

This is what xnView gave me for the uncompressed one. 
It supports TIM to view and convert to other formats but is not officially supported, I guess that's the reason why I can't convert back to it. If anyone has a program that can, then please help out DRAVEN in the Graphics Files thread.
[UncompressedTim2.jpg](https://xentaxbackup.github.io/file/942_UncompressedTim2.jpg)
## Post #9
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2006-10-21T23:16:25+00:00
- Post Title: Help uncompressing picture file

I see that program has the right palette...

I could code something that will write back to(some) tim2s but I'm too busy right now :(
