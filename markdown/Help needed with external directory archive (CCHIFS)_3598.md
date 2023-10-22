## Post #1
- Username: Faalagorn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 20, 2009 9:57 pm
- Post datetime: 2009-07-20T15:19:09+00:00
- Post Title: Help needed with external directory archive (CCH/IFS)

Firstly, welcome everyone! It's my first post here, as I finally decided to register after some reading out here.

The reason I registered here is because I need some help with extracting files from a GRAF. I won't name the game yet, because of it's nature it could be a bit problematic speaking directly about it, I will however try to give some detail about the GRAF itself.
Also keep in mind, that I already investigated the format specification, extension etc. and I'm 99% sure it's a 100% custom archive. That's the first game from that studio, so the game engine is custom, and so is the GRAF, therefore there are no working extractors for that files.

I'm after reading both DGTEFF and the [QUICKBMS GUIDE](http://forum.xentax.com/viewtopic.php?f=29&t=3525) from XeNTaX. Both were great and were really helpful, but unfortunately they didn't solved all my problems.

Firstly, I quickly discovered that my GRAF have a structure of external directory archives. There is a directory file (data.ifs.cch, approx. 2MB) and a archive file itself (data.ifs, 3.64GB). Looking at the files in HxD made me sure of this. Next, after looking at the file more deeper, I found that they are probably neither encrypted or compressed, because in CCH file there are visible filename strings and on the IFS file there are uncompressed DDS texture files.

After a bit more reading, I found out that the CCH file (but not the IFS!) have a 4-byte GRAIS string: CCH,00, the following 20 bytes is the directory header and that the filename strings contain full patch (ex. /textures/brick/brickwall008_nm.dds), are always ending with 00h and the 20 bytes prior to filename string are the file header.

I assumed that the 20-bytes headers (especially those related to files) are five 4-byte longs. That led to discovery of the first (and so far the only) field, the 4 bytes prior the string contain the length of the string along with the 00h byte.

Now, the problem is - how to discover the meaning of the other fields? Especially the offset, the filesize and how to verify the results in the IFS file? The examples in both guides mentioned earlier are assuming you are working with a single file, not the one with external directory. Also, there are way less fields in the examples than I have. Any clues and help with exploring that GRAF are welcome, thanks a lot in advance.


I also made a sketch of how the CCH file may looks like, assuming all fields would be a 4-byters. You can take a look:
Also note that there is nothing at the end of file, such as additional metadata. The last bytes of the file are: /actors/hmf/anim/hmf_ud7.v3n. ( . = 00h )

> 4 bytes - GRAIS,00 (43 43 48 00 - CCH,00)
>
> 
>
> 4 bytes - ??? (4A 62 65 9D - 1 247 962 525)
>
> 4 bytes - ??? (00,00,00,00)
>
> 4 bytes - ??? (0800 - 2048)
>
> 4 bytes - ??? (A266 - 41574)
>
> 4 bytes - ??? (0F - 15)
>
> 
>
> ==========================
>
> 
>
> 4 bytes - ??? (03 32 86 30 - 53 642 800)
>
> 4 bytes - ??? (03 32 CB B0 - 53 660 592)
>
> 4 bytes - ??? (00 30 A7 F1 - 239 601)
>
> 4 bytes - ??? (04 - 4)
>
> 4 bytes - N; file path string size,00 (24 - 36)
>
> 
>
> N bytes - /file path,00 (/textures/brick/brickwall008_nm.dds,00)
>
> 
>
> 4 bytes - ??? (03 32 55 98)
>
> 4 bytes - ??? (03 32 86 48)
>
> 4 bytes - ??? (00 30 6D 7E) 
>
> 4 bytes - ??? (00 00 01 5A)
>
> 4 bytes - N; file path string size,00 (1D - 29)
>
> 
>
> N bytes - /file path,00 (/portal/complex_sm/cs110.mat,00)
>
> 
>
> ...
>
> 
>
> 4 bytes - ??? (00 00 00 00)
>
> 4 bytes - ??? (02 86 F2 48)
>
> 4 bytes - ??? (00 09 53 13) 
>
> 4 bytes - ??? (00 00 00 78)
>
> 4 bytes - N; file path string size,00 (1D - 29)
>
> 
>
> N bytes - /file path,00 (/actors/hmf/anim/hmf_ud7.v3n,00)

I added fragments of both files as an attachment.
The IFS file is even more messed up >_<...
(File Cutter didn't worked, so I did it by HxD)

PS. It seems that the IFS won't make any help, it's all messed up, the tail (1MB) of the file consists of only zeroes and 4 FF-s at the end of file... I'll add it for completeness though.

PPS. The file was too big, I uploaded it on savefile.com: [http://www.savefile.com/files/2158745](http://www.savefile.com/files/2158745)
## Post #2
- Username: Faalagorn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 20, 2009 9:57 pm
- Post datetime: 2009-07-26T00:18:37+00:00
- Post Title: Help needed with external directory archive (CCH/IFS)

Bump. Any tips?
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-26T00:26:35+00:00
- Post Title: Help needed with external directory archive (CCH/IFS)

I'll take a look at this. What are you after anyway? What is it that you wish to accomplish with this game?
## Post #4
- Username: Faalagorn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 20, 2009 9:57 pm
- Post datetime: 2009-07-26T12:47:20+00:00
- Post Title: Help needed with external directory archive (CCH/IFS)

> Reply from Mr.Mouse
>
> What are you after anyway? What is it that you wish to accomplish with this game?
Two things actually: firstly, I was always interested in things such as demoscene and romhacking, and natural it came to exploring GRAFs, so it's partially to fill me in.
Secondly, I'm thinking of creating a wiki about the game, and having all the resources extracted without necessarily having to screen every thing in game will come handy.

Thanks for interest though, Mr.Mouse .
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-26T14:10:26+00:00
- Post Title: Help needed with external directory archive (CCH/IFS)

If you want to test your guess on the file format you an simply copy the entire small file in HxD and paste it at the end of the large file.
Just make sure you take note of the offset you went to to paste it in there.
that way just add goto 0x???
at the begging of your script and you can try extracting it like it is just one archive.
## Post #6
- Username: Loculi
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 15, 2009 10:40 pm
- Post datetime: 2009-08-15T14:46:09+00:00
- Post Title: Help needed with external directory archive (CCH/IFS)

Faalagorn,

Just wondering if you've made any progress with this.  I'm also working on tapping into the data for this game (yes I know exactly which one you're working on)   I'm basically in the same situation, there's some very specific data within these files that I would love to be able to tap into to power the back-end of a tool I'm working on for it.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-08-15T14:54:59+00:00
- Post Title: Help needed with external directory archive (CCH/IFS)

I need the name of the game so I can work on this format.
## Post #8
- Username: Loculi
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 15, 2009 10:40 pm
- Post datetime: 2009-08-15T15:11:00+00:00
- Post Title: Help needed with external directory archive (CCH/IFS)

> Reply from chrrox
>
> I need the name of the game so I can work on this format.

It's not released yet (although super close), so I PM'd you more details for now.
## Post #9
- Username: verkho
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 24, 2009 9:40 pm
- Post datetime: 2009-09-24T15:34:16+00:00
- Post Title: Help needed with external directory archive (CCH/IFS)

The game is out 

Any progress on this yet ?

I've found that there are certain reference-headers that have 24 bytes instead of 20 bytes and I've created a small ruby script which extracts all file names with corresponding header info.

- Verkho
