## Post #1
- Username: LinkvsSangoku
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 25, 2013 4:13 pm
- Post datetime: 2015-01-13T21:22:45+00:00
- Post Title: DragonBall Xenoverse .iggytex

Hi guys!
I search a way to extract some iggytex files
I opened it in Hex-editor and it's looks like a container wich one contain DDS file (i'm maybe wrong)

Does anyone of you have any clue / touched that type of file?

Note: I put a file in attachment
[iggy.zip](https://xentaxbackup.github.io/file/8474_iggy.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-15T20:57:33+00:00
- Post Title: DragonBall Xenoverse .iggytex

Giving the smaller sample a DXT3 header makes it loadable with DXTBmp.exe:



BTNGUIDE_DXT3_header.JPG (46.33 KiB) Viewed 117 times


(further adjusting required)

edit: using DXT5 signature  seems to be the better choice since the artifacts vanish
and the alpha channel looks correct then
## Post #3
- Username: LinkvsSangoku
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 25, 2013 4:13 pm
- Post datetime: 2015-01-16T11:28:28+00:00
- Post Title: DragonBall Xenoverse .iggytex

Alright, thanks Shakotay, what is is hex-editor?
It look pretty nice

Is there a way to find out what is the original size instead try every 32x multiple format?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-16T16:02:44+00:00
- Post Title: DragonBall Xenoverse .iggytex

> Reply from LinkvsSangoku
>
> Alright, thanks Shakotay, what is is hex-editor?
It look pretty niceIt's HexEdit from Andrew W. Phillips, nothing special, just free.
(It doesn't allow previewing of dds files, if you think so. The pic is a screenshot from DXTBmp.)

> Is there a way to find out what is the original size instead try every 32x multiple format?
You might search in the iggytex header.
width could be the WORD at address 0x10, for the height there are several possibilities,
maybe at address 0x1B.
