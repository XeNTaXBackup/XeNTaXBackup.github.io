## Post #1
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-03-14T09:14:35+00:00
- Post Title: Obscure 2 - HVP files

I unpacked the HVP file, but contain only DAT files. That's no problem. But, all DAT are compressed with some kind of LZO or LZ77, I don't really know.

Knows somebody what compression use the file?

[http://evin.uw.hu/obscure2_compr_dat.7z](http://evin.uw.hu/obscure2_compr_dat.7z)

Thx
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-14T11:47:08+00:00
- Post Title: Obscure 2 - HVP files

it's the classical lzo1x
## Post #3
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-03-14T13:13:22+00:00
- Post Title: Obscure 2 - HVP files

I tried to unpack with minilzo, but it's didn't workt.
But now, I made some modification.
Thanks.
## Post #4
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2010-03-17T02:51:23+00:00
- Post Title: Obscure 2 - HVP files

Any chance you can share your method or tools to unpack the .hvp and uncompress the .dat files.

Thanks
## Post #5
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-03-17T09:13:01+00:00
- Post Title: Obscure 2 - HVP files

Dat files:
Maybe, but I can't repack. I mean I can, but the repacked file is not equal with the original file, just the size, so it's doesn't work. So it's useless now.
I downloaded the official Russian version, and if I replace an eng file to rus, the game also doesn't work. I think the game contain somewhere filesize data or something. I'll compare the 2 language game version to see what changed, I hope this will the key.

To hvp: Xpert2
alucard.cc (free reg, recommend), or Google
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-03-21T14:30:36+00:00
- Post Title: Obscure 2 - HVP files

I remember this trying to hack and i got the same problkem than you, if you unpack the data the game crashes..what i did it's:
-Unpack (decompress) the data (i found a russian tool)
-Then pack the uncompressed data in compression 0
Game still crashing

-I split the first 30mb's of the header and attached to the packed data with compression 0 with the silly command 
```
copy /b header + compression0 datafinal
```


Maybe i'm wrong it was time ago..but i remember this, decompress, pack with compression 0 and attach a big header (compressed) from the original.

I know sounds strange..but it worked
## Post #7
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-03-22T07:45:32+00:00
- Post Title: Obscure 2 - HVP files

I'll give a try. But if I recompress the data with compression 0, the size of the files will changes, and than the header contain the wrong offset/size values. Or am I wrong?!

Do you remember who made this russian tool? CHEATER maybe?
Or do you have a link or something to this tool?
Because as I saw, the Xpert2 tool can unpack (not decompress) the data, but if I repack the hvp, this mess up the header.
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-05-05T13:09:43+00:00
- Post Title: Obscure 2 - HVP files

Finally i found in a really old hard disk with a lot of dust the tools to work with Obscure 2:
[http://www.multi-load.com/files/1HATF1C ... yIghor.rar](http://www.multi-load.com/files/1HATF1CG/Obscure2RUSbyIghor.rar)
Unrar the .rar, and unrar the .exe (it's a rar sfx) have a look to the bat's and the programs.
## Post #9
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-05-05T15:53:24+00:00
- Post Title: Obscure 2 - HVP files

Does anyone know how to decompress the text files???
## Post #10
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-05-06T09:15:51+00:00
- Post Title: Obscure 2 - HVP files

You want to translate the game?
## Post #11
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-05-06T13:49:32+00:00
- Post Title: Obscure 2 - HVP files

> Reply from evin
>
> You want to translate the game?

Well, yeah... i have a dump of the psp ram while running this game... the texts are decompressed but i still need a decompressor to see the original text file...
## Post #12
- Username: srcs34k
- Rank: n00b
- Number of posts: 14
- Joined date: Wed May 23, 2012 11:45 pm
- Post datetime: 2013-01-30T08:43:48+00:00
- Post Title: Obscure 2 - HVP files

> Reply from Savage
>
> Finally i found in a really old hard disk with a lot of dust the tools to work with Obscure 2:
http://www.multi-load.com/files/1HATF1C ... yIghor.rar
Unrar the .rar, and unrar the .exe (it's a rar sfx) have a look to the bat's and the programs.

please reupload if you still have.
## Post #13
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2013-02-07T09:43:03+00:00
- Post Title: Obscure 2 - HVP files

Here is:
[http://www.mirrorupload.net/file/0XKDIB ... yIghor.rar](http://www.mirrorupload.net/file/0XKDIBT2/Obscure2RUSbyIghor.rar)
## Post #14
- Username: TerrorMask
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 04, 2021 5:52 pm
- Post datetime: 2021-08-29T00:30:18+00:00
- Post Title: Obscure 2 - HVP files

> Reply from Savage ↑Thu Feb 07, 2013 5:43 pm at Thu Feb 07, 2013 5:43 pm
>
> 
Here is:
http://www.mirrorupload.net/file/0XKDIB ... yIghor.rar
By any chance do you still have this ? the link keeps giving error of no response from server
## Post #15
- Username: EcosEstudio
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Aug 31, 2022 1:32 pm
- Post datetime: 2022-09-30T05:29:34+00:00
- Post Title: Obscure 2 - HVP files

Hello,
How can I extract the Obscure II .hvp file?
I tried using the tools "obscure.hvptool" and "unhvp" but it didn't work.
I'm dubbing the game to my language and I want to extract the video and audio files.
Thanks.
## Post #16
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-19T15:00:01+00:00
- Post Title: Re: Obscure 2 - HVP files

I have some good news for Obscure 2 fans. 

I've spent some time researching HVP archives and now it's clear to me what type of hash function was used to store filenames.
It turns out it was just regular CRC32.

File format is available on the wiki here [http://wiki.xentax.com/index.php/Obscure_2_HVP](http://wiki.xentax.com/index.php/Obscure_2_HVP)
with all the notes/comments that should be useful for further research.
My focus was mainly on PC version of the game, but afaik PSP/PS2/WII versions uses the same file format.

I was able to correctly guess 80-90% of all hashes for PC release.
Here are the current results:

```
kinepack.hvp --> 89.29%
loadpack.hvp --> 84.32%
datapack.hvp --> 91.37%

```


Some of the hashes are identical or similar in PS2/PSP release, so you can use it as a starting point in further research.

To make a good use of filenames, I've created a HVP extractor (and some other tools as well)
All of them are available here: 
[https://github.com/bartlomiejduda/Tools ... bsCure%202](https://github.com/bartlomiejduda/Tools/tree/master/NEW%20Tools/ObsCure%202)

Usage is explained in the readme file.

It is possible to get 100% of the correct hashes, but it requires a lot of time.
If you want to help, you can send me a PM with correct filenames and I will add them to the tool.

Here is a tutorial with explanation how to do it:
[https://ikskoks.pl/tutorial-how-to-rest ... -archives/](https://ikskoks.pl/tutorial-how-to-restore-hashed-filenames-from-archives/)

Also, game is able to read files outside of the archives, but I didn't figure out how to do it yet. 
(even with the files unpacked in the correct directory, game preferred to load files from HVP archives)

If you know how to help with that, please let me know.


By the way, if you are interested in my "Obscure 1" research as well, here are the links:
[http://wiki.xentax.com/index.php/Obscure_HVP](http://wiki.xentax.com/index.php/Obscure_HVP)
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/ObsCure/Obscure_HVP_script.bms)
## Post #17
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2022-12-21T17:19:41+00:00
- Post Title: Re: Obscure 2 - HVP files

Just found my old research stuff, might be useful 
[hvp_stuff.zip](https://xentaxbackup.github.io/file/23171_hvp_stuff.zip)
## Post #18
- Username: Ekey
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-21T22:01:39+00:00
- Post Title: Re: Obscure 2 - HVP files

> Just found my old research stuff, might be useful

Thank you, I have compared your logs with my filenames list and there is some progress:

```
loadpack  --> from  84.32% to 85.97%
datapack --> from 91.37% to 94.2%
```

Here is a commit with new filenames [https://github.com/bartlomiejduda/Tools ... 9934073e86](https://github.com/bartlomiejduda/Tools/commit/3c89e49c695e4eef9d7ecba851df3f9934073e86)

as for PACK_EN.hvp and STRMPACK.hvp, in my version of the game (PC version) those files comes already unpacked, 
so I should have 100% of names for both of them, but to be sure I need to do some testing.
If someone could upload those archives, I would be able to test it.
## Post #19
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2022-12-22T00:11:00+00:00
- Post Title: Re: Obscure 2 - HVP files

STRMPACK is missing 3 files and these filenames are in french encoding. You can check soundfx.xmc or streams.xmc files to get them, I don't remember which one 

PS: PACK_EN.hvp and STRMPACK.hvp present in Russian version from 1C Company. You can download torrent here <link deleted by moderator> if you need it
## Post #20
- Username: hgdagon
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-22T17:36:16+00:00
- Post Title: Re: Obscure 2 - HVP files

Ok, thanks, in the newest commit I was able to get those missing french names
[https://github.com/bartlomiejduda/Tools ... 40da9c5900](https://github.com/bartlomiejduda/Tools/commit/bc411cd78e0c62c40e748972c483fd40da9c5900)
(I had encoding issue in my tool... but now it's fixed)

So I can confirm that we have 100% names for STRMPACK.hvp (for PC release)
and 22.22% for PACK_EN.hvp (for PC release)
