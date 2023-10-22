## Post #1
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-03-11T13:20:50+00:00
- Post Title: Command and Conquer 3 - TGA files

Ok, so I downloaded the C&C3 demo and opened the *.BIG archives as "Lord of the Rings: BFME" BIG files in MultiEx Commander. 

I noticed some TGA files in there, but they don't show in Photoshop and others. 

I've attached two of them, perhaps someone can take a look. 


[terrain.zip](https://xentaxbackup.github.io/file/1087_terrain.zip)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-11T17:12:58+00:00
- Post Title: Command and Conquer 3 - TGA files

Well the two files are identicals, have the same code, and the same of you i can't open the tga files
## Post #3
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-03-11T22:00:00+00:00
- Post Title: Command and Conquer 3 - TGA files

The files are compressed, like almost all files from these BIG files.
I don't know the compression method uses but suspect it could be the "default" Westwood compression (usually called something like codec80).
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-11T23:44:48+00:00
- Post Title: Command and Conquer 3 - TGA files

I read the data are compressed with RefPAck, the unpacker BigEditor Beta 0.5 comes with this unpacker

Why not try to extract the data with this Big file unpacker?

> (...)is credited for his RefPack Decompression code used in the program(...)

Info about it:
[http://www.ppmsite.com/forum/viewtopic.php?t=14272](http://www.ppmsite.com/forum/viewtopic.php?t=14272)

Unpacker:
[http://www.ppmsite.com/downloads/BIGEditorBeta05.zip](http://www.ppmsite.com/downloads/BIGEditorBeta05.zip)
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-03-12T09:07:19+00:00
- Post Title: Command and Conquer 3 - TGA files

Yes, well, of course, in my case, I wish to KNOW what's going on, instead of using someone else's tool. If I ever want to implement new decompression routines in MultiEx Commander, I must know what the compression method is. 

In any event, your tips pointed me in the right direction and I attach a tool by Jonwil, including source code. The tool seems to decompress the TGA files file. 

Note that the code has been adapted by Mad Ivan so it could actually run. See for reference: 
[http://www.derelictstudios.net/forums/i ... 52&t=15016](http://www.derelictstudios.net/forums/index.php?act=ST&f=152&t=15016)

Below the tool with source code to decompress!
[decompress2.zip](https://xentaxbackup.github.io/file/1089_decompress2.zip)
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-12T10:24:02+00:00
- Post Title: Command and Conquer 3 - TGA files

Thanks i found the unpacker too, but the zip whas CRC error, so i posted the big unpacker, with comes with the source

The decompress works great
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-20T16:01:49+00:00
- Post Title: Command and Conquer 3 - TGA files

I wonder if there is any good documentation of this compression. Don't want to go through all that code.
## Post #8
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-03-21T10:48:58+00:00
- Post Title: Command and Conquer 3 - TGA files

> Reply from Rheini
>
> I wonder if there is any good documentation of this compression.
I do not think that thic method can be documented very well (except reducing the give source code to pseudo code) due to the high usage of flag bits. This is most probably a self-constructed scheme, though the main idea is yet again "find references in past data". It is interesting, though, that the designers have combined back references and literal copying in the handling of most opcode sequences. I have not seen that before ...
