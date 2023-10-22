## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2006-11-17T13:07:06+00:00
- Post Title: XBOX360 -> DOA4 & DOAX2 TPR Format (Texture Extractio

Anybody wants to code an extraction tool for these games. The format is "*.TPR" Holds model and texture data.

I had 1 coder to make a quick DDS image extractor for the TPR's for DOA4 (Dead or Alive 4), but the DSS images are swizzled and have to be 16byte swapped first, to view them. Here is the DOA4 DDS extractor for doa4 by akakios: Download: [TPR.rar](http://www.ihud.com/file.php?file=files/171106/1163765917/TPR.rar) (for some reason this app only extracts to the root of D:\) Also though the headers between DOAX2's and DOA4's Tpr files look the same to me, the TPR dds extractor isn't compatible with DOAX2


Here's an example after a 16byte swap, the DDS is swizzled and hard to explain how to, unswizzle. but another coder did figure it out, but has since disappear along with his Texture unswizzler and model extractor 
 

the swizzle method is like every group of 4 pixels is exchanged
>example each box is a pixel

[1][2]
[3][4]

to unswizzle you cross swap

[1][3]
[2][4]

now consider these 4 pixels now a group, you do this for all groups of four. then start swapping the groups as you did the 4 pixels

yah i know its confusing >_< i had to unswizzle some by hand  i can't code

Anyway please, if your interested I'm looking for a program to unswizzle and extract. the swizzle method is the same for both doa4 and doax2. i've included samples from both DOA4, and DOAX2: (ignor the cat file, its no longer believed to hold any importance)
[DOA4_kasumiC1.rar](http://www.badongo.net/file/240994)
[doax2_samps.rar](http://www.ihud.com/file.php?file=files/171106/1163766838/doax2_samps.rar)
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2006-12-10T01:33:26+00:00
- Post Title: XBOX360 -> DOA4 & DOAX2 TPR Format (Texture Extractio

sorry to bump this

has anyone taken a look into this,  haven't had any luck with conventional unswizzle methods, i'm wondering if this is partially due to maybe compression or some other form of encryption, thats sorta scrambling the file.

not that i havent already unswizzled a few, like i said i was able to unswizzle a few, but the way its done is very unconventional, wondering if anyone has an idea on another take on this.
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-04-17T01:33:16+00:00
- Post Title: XBOX360 -> DOA4 & DOAX2 TPR Format (Texture Extractio

haha sorry BUMP'd again

aww, ??someone

i know how to unswizzle these i just need someone smart to code a easy texture extract/injection tool for the TPR files which swizzles/unswizzles on the fly.

if your interested plz let me, know 
also to sweeted the pot, i've successful made a patch, which another person has placed on there modded xbox, and it has proven to work with injected textures. so codding such an app would not go to waste.
## Post #4
- Username: redman
- Rank: advanced
- Number of posts: 71
- Joined date: Tue Jan 12, 2010 9:06 pm
- Post datetime: 2010-04-15T18:52:21+00:00
- Post Title: XBOX360 -> DOA4 & DOAX2 TPR Format (Texture Extractio

any progress in editing doa textures?? i saw a nude hack for doax2 and christie has a tattoo on her back.

can someone tell me which programm i need.
## Post #5
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-10T19:15:04+00:00
- Post Title: XBOX360 -> DOA4 & DOAX2 TPR Format (Texture Extractio

I coded a tool for doa4 texture unswizzling and reswizzling and injection a while back, still have the source if you want it.  Its vb6 though!  Still haven't gotten vb6 apps to work on my new windows7 machine.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-10T19:29:43+00:00
- Post Title: XBOX360 -> DOA4 & DOAX2 TPR Format (Texture Extractio

yes please post it it will be good to learn from.
## Post #7
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-11T06:57:46+00:00
- Post Title: XBOX360 -> DOA4 & DOAX2 TPR Format (Texture Extractio

attached rar with source
[tpr extract src.rar](https://xentaxbackup.github.io/file/3133_tpr extract src.rar)
