## Post #1
- Username: DrSid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 10, 2011 8:13 am
- Post datetime: 2011-04-10T22:29:34+00:00
- Post Title: Lost Planet 2 Tex file

Hello there, my first post. Hope it won't be a bother for you.

So .. Lost Planet 2. Capcom game. Not much people play it (which I totally don't get), and there is no modding scene for it at all. I kinda like challenge, so I took a look.
Step one, using old tools, did not really work. The primary compression seems to be fine (ARC, simple structure with zip). I made my own anyway, because I thought the older tools do not work correctly, but in the end they actually seem to work. But the texture files are not converted correctly by any tool I tried (old LP, RE5, and some mystical DMC4 which just renamed the files). They generate DDS textures, which are invalid.
By looking into the files (samples included), I guess they indeed are DDS textures. But the header is just 16 bytes. There also is array of pointers for individual mipmap levels.
I exported large number of those headers into excel, to see some relation between mipmap size and the header .. but there is none I can see. 4 bits do represent number of mipmaps, and that's it.

I attached two files. These are typical files. Some of the files are little more obscure, like being very small, or not having correct (in my understanding) number of mipmaps set.

Here are the headers, together with mipmap sizes (by 16bit words, all in hexa). Those simple zeros are zeros in all files I looked so far (hundreds). The mipmap number is the 4 in 242 and 5 in 252. After this there is the offset array, and then the data itself.

a412_text1_BM.tex   100 242 200 2100 0 17 0: 10000,4000,1000,400
lg2602_BM-00_A.tex 100 252 400 2200 0 13 0: 20000,8000,2000,800,200

I never worked with DDS before. But the data 'look like' DDS I saved from XnView. It seems to use 4 bits per pixel.
So the questions are:

- Does the header ring any bells for you ? 
- I can read mipmap sizes. Can I guess compression type and dimensions from it to create my own header ?
- What about number of components ? Can it be guessed from the mipmap size ? Any idea what kind of normal maps Capcom uses ? I can tell normal maps from filenames. Well .. there is just a few options, so I will eventually simply try.

It would be best to provide more files, like 10 .. but I can only upload 256kB. Will host some bigger batch somewhere later.

Thanks for your time ! Btw. cool site, didn't know something like this even exist until yesterday. There's no better game then hacking the codes !
[tex.zip](https://xentaxbackup.github.io/file/4203_tex.zip)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-10T22:47:23+00:00
- Post Title: Lost Planet 2 Tex file

this is the same as resident evil 5 use a texture converter from that game.
## Post #3
- Username: DrSid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 10, 2011 8:13 am
- Post datetime: 2011-04-11T10:01:56+00:00
- Post Title: Lost Planet 2 Tex file

I've already tried this converter from RE5:

[http://z6.invisionfree.com/Resident_Evi ... opic=10046](http://z6.invisionfree.com/Resident_Evil_4_PC/index.php?s=5da0bc8121fed1b3779885214cd9b368&showtopic=10046)

It does not work on LP2 files. It produces DDS texture, but it is not valid, it can't be displayed in nVidia's dds viewer, nor in XnView. Both say 'Invalid texture format'.
