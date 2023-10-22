## Post #1
- Username: Anomy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Sep 04, 2007 3:04 pm
- Post datetime: 2007-09-10T11:03:29+00:00
- Post Title: ROFS Compression\?Encryption? Method

I learned this today while doing some research on the type of compression\encryption method used on the CVM file I was trying to decode.

If you open a CVM file(or possibly any archive file) in a hex program and see something along the lines of

ROFSROFSBLD Ver# Date 

within the header, it was compiled using a tool called CRI ROFS from a japanese company called CRI MIDDLEWARE

[http://www.cri-mw.co.jp/index_e.htm](http://www.cri-mw.co.jp/index_e.htm)

To learn more about the how the format works go here.(Poorly Translated by Google)

[http://translate.google.com/translate?h ... f%26sa%3DG](http://translate.google.com/translate?hl=en&sl=ja&u=http://www.cri-mw.co.jp/insidemw/rofs1/index_j.htm&sa=X&oi=translate&resnum=1&ct=result&prev=/search%3Fq%3DROFSTOKO%26hl%3Den%26safe%3Doff%26sa%3DG)

And finally a list of games that will most likely have had this tool used on them.

[http://www.cri-mw.co.jp/index_e.htm](http://www.cri-mw.co.jp/index_e.htm)

Since as the site states the file system used is the ISO9660, maybe someone will be able to come up with a tool for extracting files 
from these archives files that have used the ROFSBLD TOOL.

I hope this information proves to be useful and someone can put it to good use cause I sure could use tool for this
## Post #2
- Username: Anomy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Sep 04, 2007 3:04 pm
- Post datetime: 2007-09-10T11:40:23+00:00
- Post Title: ROFS Compression\?Encryption? Method

Another bit of information I can only make a little sense out since it is translated from Japanese, and I have had no success using it, but someone else may realize what is being done here better than I.

Original Source
[http://homepage1.nifty.com/~hin/rofs.html](http://homepage1.nifty.com/~hin/rofs.html)

----------------------------------------------------------------------------------
ROFS , By turning off the  0x1800 byte from the forefront of the file (header), and change the extension to .iso, Daemon tools can mount it.

With the header where 0x1800 is gone, then it seems that its retained with the file system ( ISO9660 )

ROFS (CVM) file format memo 

B = byte (8bit) 
W = word (16bit) 
L = long word (32bit) 

-- 
0x0000-0xb7ff 
 - ROFS version 
 - GAME TITLE and PUBLISHER_NAME etc. 

offset 0xb800
1W: first data length = A 
1L: START address START (little endian) 
1L: START address START (big endian) 
1L: FAT SIZE (little endian) 
1L: FAT SIZE (big endian) 
1B: 0x68?? 
1B: data length X 
XB: ?? (date?) 
4B: 01 00 00 01 ?? 
2B: 01 00 or 01 01 
	01 01 as for the FAT SIZE-related data end? 

1W: next data length = B 

here byte become A. Reading B Byte next, it processes. 　

However, because completely it has become the same contents as A in regard to data which is read next, as for meaning in regard to data of B you do not understand well. For verification? 

-- 
offset 0xb800 + A + B 
1W: data length C

:DATA FIRST 

1L: START address START (little endian) 
1L: START address START (big endian) 
	FILE START address = 0x800*START + 0x1800
1L: file size (little endian) 
1L: file size (big endian) 

1B: 0x68 ?? 
1B: data length Y 
YB: ?? (date?) 
4B: 01 00 00 01 ?? 
1B: file name length Z 
ZB: file name 
2B: 3B 31 (flag?) 

0 fill are done

last 1W: In case of data length of following data D 
			0x0000, it adjusts the length of the following data and is packed (?)There is a place where it is done. The data other than 
			0x00 appears to has the necessity to search. 　

The quantities of all to here byte become C. Reading D Byte next, it processes. However, it adjusts and is packed (?)When it was done, data length stops being agreeable. 　

After returning to DATA FIRST, to FAT SIZE + 0x1800 it repeats processing.
-------------------------------------------------------------------------------------

Hope this helps a bit.
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-09-10T12:48:33+00:00
- Post Title: ROFS Compression\?Encryption? Method

ROFS = Read Only Files System
It had been using to creating Disk Image for long time! Is there any new technology came up? And I think there is an extractor for that but not sure if it is universal!?

Do a google search on 'ROFS' may come up for the tool!

If not I can upload it when I found it.
## Post #4
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2008-02-25T22:51:39+00:00
- Post Title: ROFS Compression\?Encryption? Method

long ago I looked into this format and found out that it is actualy a normal iso with a slightly diferent header. I also found one file that had a compressed or encrypted file index. so those are a no go :(

This is what I had(not much)

struct ROFSRootEntry
{
	int Offset;
	short Unknown;
	std::string Name;
};

struct ROFSEntry
{
	unsigned short EntrySize; // Entry Header Size
	unsigned int Address; // File start offset
	unsigned int Size; // File Size
	unsigned char Unk0[10];
	unsigned short Unk;
	std::string Name;
};

if I remember correctly the root entries are a listing of all directories  in the file. from there the rofsentry structure is used to navigate the actual directory and file structure. a flag in the rofsentry structure tells if the entry is a directory(0x02) or a file(0x01) but I don't know where that was ^_^; when the entry is a directory the offset leads to another listing of directories or files. the file is padded to 4096 or 2048 I don't remember. (directories always have "." and ".." entries)

First read the root entries at offset ??? load them into memory and use that to get the entire file list(with rofsentry structure) it is just a bunch of interconnecting nodes.

That japanese document was incomplete when I first saw it... and the auto translation makes it even more dificult to read hehe.

Sorry I don't have a working program :(
## Post #5
- Username: roxfan
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 15, 2008 10:28 am
- Post datetime: 2012-02-19T21:36:48+00:00
- Post Title: ROFS Compression\?Encryption? Method

I had some plans for a long writeup, but I think I'll just attach the sources and everyone can see for themselves.

Briefly, ROFS is a repackaged ISO9660 (CD filesystem) image, with some added headers and optionally encrypted file table. I managed to completely reverse both packing and encryption algos, the only thing you'll need is the password the game uses to open the file (if password is used). The password can usually be found in the binary next to the CVM filename, or strings like "VOL", "ROFS" or "ADXF_AddRofsVol".

It seems CRI is not using this format anymore but maybe this will help people working on some older games.
[cvm_tool_02.zip](https://xentaxbackup.github.io/file/5091_cvm_tool_02.zip)
## Post #6
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2012-02-23T04:26:53+00:00
- Post Title: ROFS Compression\?Encryption? Method

Thanks a lot, and thanks for including the source for decrypting the header.
## Post #7
- Username: Brandondorf9999
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2012 10:08 am
- Post datetime: 2014-08-04T00:19:21+00:00
- Post Title: ROFS Compression\?Encryption? Method

What are the hex values to the header with 0x1800? I can't find that on the ROFS.CVM.
## Post #8
- Username: Pixelise
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 30, 2016 1:35 am
- Post datetime: 2017-07-15T15:40:14+00:00
- Post Title: ROFS Compression\?Encryption? Method

> Reply from roxfan
>
> I had some plans for a long writeup, but I think I'll just attach the sources and everyone can see for themselves.

Briefly, ROFS is a repackaged ISO9660 (CD filesystem) image, with some added headers and optionally encrypted file table. I managed to completely reverse both packing and encryption algos, the only thing you'll need is the password the game uses to open the file (if password is used). The password can usually be found in the binary next to the CVM filename, or strings like "VOL", "ROFS" or "ADXF_AddRofsVol".

It seems CRI is not using this format anymore but maybe this will help people working on some older gamea.
Hi. I have a little problem with your program. Whenever I try to open it (dragging and dropping an .CVM file or not) it starts and as soon as it shows up it closes not doing any conversion. Any help please?
## Post #9
- Username: roxfan
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 15, 2008 10:28 am
- Post datetime: 2017-07-15T16:42:39+00:00
- Post Title: ROFS Compression\?Encryption? Method

> Reply from Pixelise
>
> 
Hi. I have a little problem with your program. Whenever I try to open it (dragging and dropping an .CVM file or not) it starts and as soon as it shows up it closes not doing any conversion. Any help please?

It's a commandline tool, you need to run it from a command prompt.
## Post #10
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2018-08-14T12:42:29+00:00
- Post Title: ROFS Compression\?Encryption? Method

I don't get it... where i find and put the password?
[jakaaka.JPG](https://xentaxbackup.github.io/file/14741_jakaaka.JPG)
## Post #11
- Username: roxfan
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 15, 2008 10:28 am
- Post datetime: 2018-08-15T14:41:14+00:00
- Post Title: ROFS Compression\?Encryption? Method

> Reply from BL4CK0UT
>
> I don't get it... where i find and put the password?
It's explained in my post; you need to reverse the game to extract the password:

> The password can usually be found in the binary next to the CVM filename, or strings like "VOL", "ROFS" or "ADXF_AddRofsVol".
Note: "usually" is not "always"; the password may be obfuscated, encrypted, or otherwise generated at runtime instead of being hardcoded.



If you found a candidate password, pass it with the -p parameter on the commandline. e.g.:

```
>cvm_tool.exe decrypt -p my_password file file.cvm
```
## Post #12
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-08-15T20:46:01+00:00
- Post Title: ROFS Compression\?Encryption? Method

what cvm are you trying to extract? what game?
## Post #13
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2018-08-16T12:33:54+00:00
- Post Title: ROFS Compression\?Encryption? Method

NARUTO ULTIMATE NINJA 3, i would like to do with all Ultimate ninja series as well
## Post #14
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2018-09-20T19:59:19+00:00
- Post Title: ROFS Compression\?Encryption? Method

I finded that the password to  Naruto Ultimate Ninja 3 [same pass on 4 & 5] is cc2fuku.

but i don't understand it , and i don't want to bother anymore .. so i'm givin' up on Ultimate ninja project... good  luck to who want to do it
## Post #15
- Username: blackknight2000
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 22, 2022 9:47 am
- Post datetime: 2022-02-22T02:54:04+00:00
- Post Title: ROFS Compression\?Encryption? Method

Hello Everyone, hoping you guys can help me - I desperately want to patch this game with a translation 



The translation I can do with the help of my wife the part that I have to teach myself is how to reverse engineer this game. I've been at this for three days or so now and I got as far as dumping the ISO, here is the result.



 I am on a few different forums trying to get assistance so now I am giving this one a try. The game I am trying to decompress uses CVM files and it seems like the people here really understood how to decompress them so hoping you guys can help.
## Post #16
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-02-22T11:22:48+00:00
- Post Title: Re: ROFS Compression\?Encryption? Method

already answered you.

[https://zenhax.com/viewtopic.php?f=12&t=16564](https://zenhax.com/viewtopic.php?f=12&t=16564)
