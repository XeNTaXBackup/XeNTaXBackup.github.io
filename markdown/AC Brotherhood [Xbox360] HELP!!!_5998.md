## Post #1
- Username: LostMC
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 15, 2010 5:17 am
- Post datetime: 2011-02-05T23:31:53+00:00
- Post Title: AC: Brotherhood [Xbox360] HELP!!!

Hi! Can someone help me?   
I'm trying to unpack some models and textures from Xbox 360 .forge files. 
Maki (with Lucy plugin for AC II) opened them, but the files inside (without any extension) don't open. 
But I very need models and textures inside! How to open them?!
Some of those without-any-extension Ezio models:

_Ezio_RaidenSuit_ALL_VR_Missions
[http://www.mediafire.com/?qd7hhap74wsroa4](http://www.mediafire.com/?qd7hhap74wsroa4)

_Ezio_Ultimate_2_HelmschmiedDrachenArmor_EXCpreorder
[http://www.mediafire.com/?o7nsw1ivabqmgoq](http://www.mediafire.com/?o7nsw1ivabqmgoq)

Thanks in advance.
## Post #2
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-02-08T23:22:07+00:00
- Post Title: AC: Brotherhood [Xbox360] HELP!!!

Both files you provided are container files with additional compressed information inside the container.  Is it at all possible you could provide the .forge file these files were obtained from.

I'll attempt to de-compress these files, but the complete .forge file would be a quicker option.
## Post #3
- Username: LostMC
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 15, 2010 5:17 am
- Post datetime: 2011-02-09T18:19:13+00:00
- Post Title: AC: Brotherhood [Xbox360] HELP!!!

OK....
Here it is (all player models from game (Ezio + Desmond)):

[http://www.mediafire.com/?6gcpdp7gtrjko4k](http://www.mediafire.com/?6gcpdp7gtrjko4k)
## Post #4
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-02-10T01:43:59+00:00
- Post Title: AC: Brotherhood [Xbox360] HELP!!!

Got it.  Gonna work on it a little later.
## Post #5
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-02-10T04:08:20+00:00
- Post Title: AC: Brotherhood [Xbox360] HELP!!!

Ok, this is going to take a little longer than I anticipated.  Endianess is the issue.  XBox360 goes one way, PC the other.  Both Maki and my program can read and open the .forge file.  But the files inside are where they are turned around and is probably the reason Maki will not open them.  It may take me a day or two, but I'll find out if the formats have stayed the same by swapping the endianess based on what I know and see if I can pull anything out of it.
## Post #6
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-02-13T00:10:14+00:00
- Post Title: AC: Brotherhood [Xbox360] HELP!!!

Well this is proving more difficult with every step.  They are using a different compression algorithm than they have in the past.  I have attempted every lzo algorithm and so far the only one that gives me anything has been lzo2a.  And it doesn't correctly decompress the file, but it does get me something that I can read.  Now I have to hunt through the container to find file types that I know.  Hopefully soon, I'll be able to post some pics.
## Post #7
- Username: LostMC
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 15, 2010 5:17 am
- Post datetime: 2011-02-13T00:35:57+00:00
- Post Title: AC: Brotherhood [Xbox360] HELP!!!

MichaelDarkAngel, thank you!        I can't wait....
## Post #8
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-02-18T02:14:15+00:00
- Post Title: AC: Brotherhood [Xbox360] HELP!!!

Having issues, that I may not be able to solve until the PC version of the game becomes available.  Some of the issues; CompressionDX10 DDS
On the compression issue, the best I can decompress the files using lzo2a leaves me with large chunks null bytes, which based on previous versions of AC and PoP leads me to believe this is not right.

On the DX10 issue, either I am not writing the header properly (which is most likely the case), or the compression issue is causing other problems.

I have tried making the images DXT5 instead of DX10, but I get garbage.

[](http://www.tbotr.net/images/CU_Ezio_Clothes_NormalMap.png)
Image from the AC:Brotherhood .forge file (click for larger image)

[](http://www.tbotr.net/images/AC2_CU_Ezio_Clothes_NormalMap.png)
Assuming same image from AC2 .forge file (click for larger image)
## Post #9
- Username: LostMC
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 15, 2010 5:17 am
- Post datetime: 2011-02-19T21:18:59+00:00
- Post Title: AC: Brotherhood [Xbox360] HELP!!!

And what with models?
## Post #10
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-02-25T00:21:20+00:00
- Post Title: AC: Brotherhood [Xbox360] HELP!!!

> Reply from LostMC
>
> And what with models?

Unfortunately with this also I've been unable to find a clean model file.  Meaning, a model file that is not borked by my inability to decompress the FILEDATA properly.

Sorry
