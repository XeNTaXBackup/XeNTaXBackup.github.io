## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-03-12T21:40:07+00:00
- Post Title: Commandos Strike Force

The data it's compressed i dont' know wich compressor it's used. 
Maybe it's zlib?.

Here it's the sample:
[http://rapidshare.de/files/15353728/Ambush.pak.zip.html](http://rapidshare.de/files/15353728/Ambush.pak.zip.html) (2mb's)
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-03-13T08:04:37+00:00
- Post Title: Commandos Strike Force

Scanned thru the archive and found some 16x16 PNG pictures.
, also found 256x256 and 512x512 PNG images.

however, the images larger than 16x16 is not viewable,
they have a strange header ive never seen before in a PNG image,
but they are for sure PNG images.
those do not look compressed. but there is a possibility that the
rest of the files in the archive is compressed yes =o

an example, on all 16x16 PNGs they have pHYs Header,
on 256x256 and up this header has been replaced with a
ICC Profile header. and the IDAT  (image data) is far away down in the
image file, where on the 16x16 images are located in the beginning of
the file. could be a custom made PNG format.
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-03-13T11:10:24+00:00
- Post Title: Commandos Strike Force

> but there is a possibility that the
>
> rest of the files in the archive is compressed yes

it's compressed, i tried to pack with rar and the file size it's the same.
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-03-13T11:26:56+00:00
- Post Title: Commandos Strike Force

keep in mind that PNG format is automatically compressed in its
whole structure. so compressing an PNG picture with rar or zip
does not make any sense.

i would like to have the full archive so i can check it in whole.
because from what i see now, jaeder naub ripped out exactly 1 MB
of PNGs from this front* archive. (and the cutted files was 1 MB)

BUT.....the back* cut is a little different. there are only 1 PNG file
12kb big and the rest is an unknown file for me.

im still investigating. what confuses me most is this odd PNG header
for some of the files.
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-03-13T13:58:08+00:00
- Post Title: Commandos Strike Force

You need a big/full file? like 40mb's?
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-03-13T14:33:00+00:00
- Post Title: Commandos Strike Force

That would make my day!

so, yes please =))) if you dont mind.
## Post #7
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-03-13T18:06:42+00:00
- Post Title: Commandos Strike Force

Okis here a full file:

[http://rapidshare.de/files/15416648/a_f ... k.pak.html](http://rapidshare.de/files/15416648/a_file_pack.pak.html)

It's 27mb's

Looks like a zip, but it's not a zip, maybe a own packer?
## Post #8
- Username: bouvrie
- Rank: advanced
- Number of posts: 55
- Joined date: Sun Mar 19, 2006 12:29 am
- Post datetime: 2006-03-19T11:55:00+00:00
- Post Title: Commandos Strike Force

Whatever it is, it's no known WinRAR archive format. Usually, opening pak files in WinRAR will open them in case WinRAR recognizes the format. In this case, WinRAR doesn't.
## Post #9
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-03-19T23:24:17+00:00
- Post Title: Commandos Strike Force

Pulposo:
Okay, the whole archive is actually compressed, except for the PNG images =o , but everything else is indeed compressed.
## Post #10
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-03-20T00:49:38+00:00
- Post Title: Commandos Strike Force

Yes i know it's compressed, but somebody knows wich compressor it's used or know how to unpack it?
## Post #11
- Username: ENV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 22, 2006 10:25 pm
- Post datetime: 2006-03-22T14:30:09+00:00
- Post Title: Commandos Strike Force

Managed to get a wav file out of the GlobalEK.pak file seemed to play ok,

I assume the first 4 chars are the identifier (if that is the word)

seems strange thou that all the map .pak files start PAKC and the GlobalEK.pak file starts PAKA.

Could just be me not having a clue what i'm looking at thou
## Post #12
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-03-22T15:02:53+00:00
- Post Title: Commandos Strike Force

> PAKC and the GlobalEK.pak file starts PAKA.
PAKC it's compressed, PAKA not.
## Post #13
- Username: ENV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 22, 2006 10:25 pm
- Post datetime: 2006-03-22T15:21:45+00:00
- Post Title: Commandos Strike Force

ahh, can you give me any tips on understanding the PAKA file better?
I can't seem to work out the addressing system.
## Post #14
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-03-22T15:34:07+00:00
- Post Title: Commandos Strike Force

Sorry, i only tested with the files, if you compress the packa file with rar the compression it's good, the pakc no.

I know it's silly and easy but works.
## Post #15
- Username: ENV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 22, 2006 10:25 pm
- Post datetime: 2006-03-22T16:19:28+00:00
- Post Title: Commandos Strike Force

I cant seem to understand how the file table works in the uncompressed file at the moment, but I am very noob at this
## Post #16
- Username: ENV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 22, 2006 10:25 pm
- Post datetime: 2006-03-22T17:09:29+00:00
- Post Title: 

hmm I think ive got enough to extract the non compressed file now...

Any ideas on the type of compression used on the others?
## Post #17
- Username: ENV
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 22, 2006 10:25 pm
- Post datetime: 2006-03-27T08:38:32+00:00
- Post Title: 


## Post #18
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-08-16T22:55:57+00:00
- Post Title: 

Well GAUP looks can unpack the .PAK, i dont' have a sample or similar to try...so..if somebody have the game to test... 

[http://wincmd.ru/plugring/gaup.html](http://wincmd.ru/plugring/gaup.html)

* "Commandos Strike Force" .PAK files (Not decompress)

mm.. looks unpacker not decompressor
## Post #19
- Username: Anatoly Prokofiev
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 31, 2006 7:42 pm
- Post datetime: 2006-10-31T13:35:16+00:00
- Post Title: 

The type of compression, used in PAK files, is a simple Deflate. ZLibEx library can handle such packed blocks with no problem. Each file in PAK archive is stored like this:

@[Real file offset from the main table]:
long PackedBlockSize
long UnpackedBlockSize

Here's a pseudocode to extract one file from _compressed_ PAK.

Get Real_File_Size from the main table
Seek to Real_File_Offset.

Repeat
 Read PackedBlockSize
 Read UnpackedBlockSize

 Read Block
 DecompressIt (i.e., using ZDecompress from ZLibEx)
 WriteTo_Output

 Real_File_Size = Real_File_Size - UnpackedBlockSize
until Real_File_Size<=0

That's all, I guess. Today I managed to decompile (AND recompile) all PAK files from the game. Remember to change "PAKC" header ID to "PAKA", if you want to produce an uncompressed PAK file.
## Post #20
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-11-04T14:08:17+00:00
- Post Title: 

```
Get V1 Long 0 ;
Get V2 Long 0 ;
Get ResNum Long 0 ;
# First loop needed to just find the offset of the first file
SavePos ST 0 ;
For T = 1 To ResNum ;
Get FN String 0 ;
Get ROff Long 0 ;
Get Size Long 0 ;
Get V1 Long 0 ;
Get V2 Long 0 ;
Next T;
SavePos Offset 0 ;
GoTo ST 0 ;
For T = 1 To ResNum ;
Get FN String 0 ;
Get ROff Long 0 ;
Get Size Long 0 ;
Get V1 Long 0 ;
Get V2 Long 0 ;
Math ROff += Offset ;
Log FN ROff Size 0 0 ;
Next T;
```


This will enable full extraction from the 'A'  type PAK files.
## Post #21
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-02-27T16:43:14+00:00
- Post Title: 

> Reply from Anatoly Prokofiev
>
> The type of compression, used in PAK files, is a simple Deflate.
as always 

> Today I managed to decompile (AND recompile) all PAK files from the game.
So you wrote a tool? Will you release it?
## Post #22
- Username: Anatoly Prokofiev
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 31, 2006 7:42 pm
- Post datetime: 2007-04-06T11:04:22+00:00
- Post Title: 

Wow. I almost forgot about this topic... 

> So you wrote a tool? Will you release it?

No, what's the point? It was a very simple tool - no GUI, no options.
But there is also a good news. I sent a letter to creator of GAUP with a brief description of how to unpack this files. Look at this:

0.4.9.0 PRO (02/11/2006)
Добавлена полная распаковка of Commandos Strike Force .PAK файлов (спасибо Анатолию Прокофьеву).

Added full extraction of Commandos Strike Force .PAK files (thanks to Anatoly Prokofiev).

So, enjoy!
## Post #23
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-04-07T09:41:37+00:00
- Post Title: 

Hmmmm... the big question at this point is if the game recognises the decompressed files or if recompiling the PAK file is relatively simple. Since the compression is simply deflate it seems it would be a simple process to recompress and remake the archive and it would be playable?

I don't own the game myself but it seems that this could be tested perhaps? It is important how easily decompression and recompiling is in relation to if the game would recognise it afterwards... that is, to test that hypothesis for a clear answer if I have to find some way to do so myself.
