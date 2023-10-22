## Post #1
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-19T05:37:20+00:00
- Post Title: How to fix dds format?

Hi! All
I have a dds(DXT1 formats) image. 
It was unpacked from a G1T file
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-19T19:04:00+00:00
- Post Title: How to fix dds format?

not sure whats going on exactly, I think that converter you have injects a DDS into an XPR, then runs it through the xbox360 sdk tool, or runs it through the same algo that the sdk tool would.

i tossed the raw (BNS0375) into a huge 1024x1024 DXT1 texture, and saw "unswizzled" textures


donno where you got the files, but that stuff you see on your converted textures are blockshorts caused by improper decompression. so either the wrong decompressor was used or the data was offseted, and the decompressor didnt read/write at the proper location


the format lools a bit annoying inside looks like they're tagging each channel and mip of the texture O_o


I would find the author of the tool and ask him to have another look, maybe theres a bug in the program.
## Post #3
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-20T00:12:12+00:00
- Post Title: How to fix dds format?

> Reply from mariokart64n
>
> not sure whats going on exactly, I think that converter you have injects a DDS into an XPR, then runs it through the xbox360 sdk tool, or runs it through the same algo that the sdk tool would.

i tossed the raw (BNS0375) into a huge 1024x1024 DXT1 texture, and saw "unswizzled" textures


donno where you got the files, but that stuff you see on your converted textures are blockshorts caused by improper decompression. so either the wrong decompressor was used or the data was offseted, and the decompressor didnt read/write at the proper location


the format lools a bit annoying inside looks like they're tagging each channel and mip of the texture O_o


I would find the author of the tool and ask him to have another look, maybe theres a bug in the program.
Just Good, thanks mariokart64n.
I'm very sorry, can you give me more details?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-20T01:00:40+00:00
- Post Title: How to fix dds format?

It looks like a standard koei texture dynasty warriors gundam i guess?
You need to delete 0xC bytes that are right after the standard 0x80 dds header
then you need to perform a byte swap on the rest of the file in the form of unsigned shorts.
This should be the same format as hokuto musou aka fist of the north star did you try Noesis on the original files?
## Post #5
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-20T08:15:15+00:00
- Post Title: How to fix dds format?

> Reply from chrrox
>
> It looks like a standard koei texture dynasty warriors gundam i guess?
You need to delete 0xC bytes that are right after the standard 0x80 dds header
then you need to perform a byte swap on the rest of the file in the form of unsigned shorts.
This should be the same format as hokuto musou aka fist of the north star did you try Noesis on the original files?

I thank you for replying.
You said it! Form  PS3 dynasty warriors gundam 3.
how to swap a byte?
## Post #6
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-20T08:53:29+00:00
- Post Title: How to fix dds format?

I cannot make sense of this "Just do 16bit swap"...
Would you elaborate on it, please?
## Post #7
- Username: dj082502
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-20T11:13:19+00:00
- Post Title: How to fix dds format?

take for example you had the bytes 1 2 3 4
you would need to make them
2 1 4 3
you can do this in the program 010 editor.

click tools > hex operations > swap
then do a unsigned short swap.
## Post #8
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-20T11:32:39+00:00
- Post Title: How to fix dds format?

> Reply from chrrox
>
> take for example you had the bytes 1 2 3 4
you would need to make them
2 1 4 3
you can do this in the program 010 editor.

click tools > hex operations > swap
then do a unsigned short swap.
Thank you for your explanation.

Merry Christmas in advance
## Post #9
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2010-12-21T00:53:55+00:00
- Post Title: How to fix dds format?

Hex Workshop can flip bytes too.
## Post #10
- Username: Murdiaries
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Mar 03, 2011 9:40 pm
- Post datetime: 2011-03-19T23:38:35+00:00
- Post Title: How to fix dds format?

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-03T09:45:39+00:00
- Post Title: How to fix dds format?

> Reply from chrrox
>
> take for example you had the bytes 1 2 3 4
you would need to make them
2 1 4 3
you can do this in the program 010 editor.

click tools > hex operations > swap
then do a unsigned short swap.
Thank you for your a detailed explanation
