## Post #1
- Username: Quingo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 25, 2010 7:45 pm
- Post datetime: 2010-02-25T12:22:15+00:00
- Post Title: NHL 10 texture files (Xbox 360)

Hello everybody!

I have been trying to "crack" the texture file format for EA Sports' NHL 10 game on the Xbox 360 for quite some time now, but I don't get anything done. I'm not exactly a programmer/coder and I rarely have had to work with HEX-Editors etc. before. So this is the status quo:

- the files on the DVD can easily be extracted onto a PC's HDD (surprise, surprise...)
- most files are stored in big archives, and by saying big I also mean that they're stored in *.big file-type archives.
- these archives can be opened using BIGEditor and files can also be extracted from these archives.
- these newer files also consist of *.big archives, in which there seem to be four files without a file header

Among these files usually are one texture file, whose header according to HEX-Editors is "RW4xb2" (might be a hint at the file being some sort of compressed RAW-file, like "Raw for Xbox 2" [=360]), a file that weighs in at 1,0 to 1,5 kbytes and two more files at 32 bytes and 288 bytes. I tried changing the texture file (always around 120-150 kbytes big) to some file headers and when changing it to RAW, IrfanView is even able to open it - but it only looks pretty weird.

Here's some screenshots of what the structure etc. looks like:




This is what IrfanView shows, if you rename the files to RAW:


I uploaded one of the big-archives within the big-archives here: [http://www.sendspace.com/file/j4jj4p](http://www.sendspace.com/file/j4jj4p)
It should, if the numbers stayed the same they were back in PC days, be the cyberface texture of player Teemu Selänne.

In case you don't want to download BIGEditor for this, here's the files included in the archive: [http://www.sendspace.com/file/g2549s](http://www.sendspace.com/file/g2549s)
"268" seems to be the texture file. All I can say is, that EA used to use *.fsh-graphics back on their PC version and later on switched to some kind of *.dds files.

Any help would be greatly appreciated!

Thanks for your help,

- Ben
## Post #2
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-02-25T14:28:46+00:00
- Post Title: NHL 10 texture files (Xbox 360)

I cant shed any light on the texture files but looking at the files numbered 0 and 1, what I see are references to APT.

APT is a format that is used for the user interface of a number of EA RTS games (such as C&C3 and RA3) and (at least in the form used in those RTS games) is loosely based on Macromedia Flash.

The files I see there (0 and 1) are a different format APT file to the ones I have seen though.
## Post #3
- Username: Quingo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 25, 2010 7:45 pm
- Post datetime: 2010-02-25T15:41:53+00:00
- Post Title: NHL 10 texture files (Xbox 360)

> Reply from jfwfreo
>
> I cant shed any light on the texture files but looking at the files numbered 0 and 1, what I see are references to APT.

APT is a format that is used for the user interface of a number of EA RTS games (such as C&C3 and RA3) and (at least in the form used in those RTS games) is loosely based on Macromedia Flash.

The files I see there (0 and 1) are a different format APT file to the ones I have seen though.

Thanks for this reply already, I could see these files being there for facial animation purposes maybe? The players mimic and gesture a lot on the ice, so maybe this could be some kind of "key" to the X/Y/Z positions, where the face's model needs to be moving. Everything we know is valuable, so thanks for already finding that out
## Post #4
- Username: Quingo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 25, 2010 7:45 pm
- Post datetime: 2010-02-26T19:03:16+00:00
- Post Title: NHL 10 texture files (Xbox 360)

Sorry for the double post, but I wanted to provide another texture file so one could probably start to see the schematic with which these textures are created. By looking at a hex-editor, it seems every of these files has "454.000" written at offset 00000010.

Here's the second texture, should be 512*512 and containing a jersey if opened correctly: (texture within the archive)
[Anaheim_home.rar](https://xentaxbackup.github.io/file/2813_Anaheim_home.rar)
## Post #5
- Username: Quingo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 25, 2010 7:45 pm
- Post datetime: 2010-04-04T11:30:23+00:00
- Post Title: NHL 10 texture files (Xbox 360)

Bumping the thread a bit. Anybody got any idea on how to handle these texture files? By now we can pretty much only say, that the file seems to be tiled, swizzled and uses a format that seems to be based on DirectDraw-Surface.
## Post #6
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-04-30T16:04:32+00:00
- Post Title: NHL 10 texture files (Xbox 360)

the 358 file seems to be a texture package but i am not really interested ...
## Post #7
- Username: Quingo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Feb 25, 2010 7:45 pm
- Post datetime: 2010-06-29T08:50:01+00:00
- Post Title: NHL 10 texture files (Xbox 360)

Thanks anyways to everyone, who tried to help me out.

I found out one thing a few days ago (haven't been able to do much thanks to University):

- according to an internal text-file within the game archives, the format seems to be somewhat related to .swf flash formats, as they're named like that within some kind of a file list

If anyone could probably help me out somehow, I'd be glad.
[Mentioned_files.rar](https://xentaxbackup.github.io/file/3180_Mentioned_files.rar)
