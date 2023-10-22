## Post #1
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-10-26T12:19:04+00:00
- Post Title: farming simulator 2013

Could some one have a look at these files for me? From their previous games they could be compressed and/or encrypted. I found a couple of references to lzx but that's all.

Thanks.

Head and tail: [http://www.mediafire.com/?8525tbswpl79vyc](http://www.mediafire.com/?8525tbswpl79vyc)

pm me if the whole file is needed (only 4mb) or exe.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-10-31T21:14:35+00:00
- Post Title: farming simulator 2013

[http://aluigi.org/papers/bms/giants_software.bms](http://aluigi.org/papers/bms/giants_software.bms)
## Post #3
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2012-11-01T10:22:30+00:00
- Post Title: farming simulator 2013

Thanks! works great.
## Post #4
- Username: Kxu1d
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 25, 2012 5:30 am
- Post datetime: 2012-11-27T18:32:25+00:00
- Post Title: farming simulator 2013

I'm in the process of trying to open a .DLC file (Which is actually just a renamed .gar file) I renamed it to .gar and used quickbms.exe and giants_software.bms to try and unpack the file. The message I got was "Error: unknown key, contact me". I where wondering how i could get the key for this archieve? I split the file to head/tail as the full size is 311mb.

The Head and Tail are here: [http://db.tt/rC1kySU5](http://db.tt/rC1kySU5) , if anything else is needed tell me  oh and this file where installed at the same time so I where curious if this could contain the key but im unable to read it: AHC_31148.dat its in the archive with the head/tail.

Oh and the DLC is for 2011 but i figured since the BMS for all versions where here I could post this here as well.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-02-01T14:51:31+00:00
- Post Title: farming simulator 2013

I have updated the script to support also the 1.4 beta version of this game
## Post #6
- Username: desperados
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 22, 2009 10:33 pm
- Post datetime: 2013-09-08T20:00:20+00:00
- Post Title: farming simulator 2013

Hello, can someone please edit the BMS version of the xbox360?
[http://www.gamefront.com/files/23681208 ... Memory.rar](http://www.gamefront.com/files/23681208/preloadMemory.rar)

Archive is different than the PC version.
Thank you very much in advance
Sorry for bad English
## Post #7
- Username: XBLToothPik
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 23, 2013 1:44 am
- Post datetime: 2013-09-09T05:54:29+00:00
- Post Title: farming simulator 2013

> Reply from desperados
>
> Hello, can someone please edit the BMS version of the xbox360?
http://www.gamefront.com/files/23681208 ... Memory.rar

Archive is different than the PC version.
Thank you very much in advance
Sorry for bad English

It's a pretty simple format.  Done in C# b/c I've never used QuickBMS

Each TOC entry is 512 bytes long, although not all of those 512 may be used up.  Not sure as to what compression it uses.

```
int hUnk = StreamUtils.ReadInt32(xIn, false);
int fileCount = StreamUtils.ReadInt32(xIn, false);
for (int i = 0; i < fileCount; i++)
{
     int toOffset = (i * 512) + 12;
     xIn.Position = toOffset;

     int Offset = StreamUtils.ReadInt32(xIn, false);
     int Unk1 = StreamUtils.ReadInt32(xIn, false);
     int Unk2 = StreamUtils.ReadInt32(xIn, false);
     int decompSize = StreamUtils.ReadInt32(xIn, false);
     int compSize = StreamUtils.ReadInt32(xIn, false);
     string Name = StreamUtils.ReadNullString(xIn);

     Console.WriteLine(Name, Offset, compSize);
}

```


Header: (12 bytes)
MAGIC/IDENT "PACK" - 0x0
Unknown - 0x4
Entry Count - 0x8

Entry: (512 bytes)
int32 - data offset
int32 - unk
int32 - unk
int32 - decompresed size
int32 - compressedS size
string - name (null terminated)
## Post #8
- Username: desperados
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 22, 2009 10:33 pm
- Post datetime: 2013-09-11T14:46:24+00:00
- Post Title: farming simulator 2013

Thanks XBLToothPik for the advice, program C # is quite difficult for me. So nothing for me - thanks
## Post #9
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-11T19:41:26+00:00
- Post Title: farming simulator 2013

i have unpaker for this, but dont know what is compression used
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-11T22:17:31+00:00
- Post Title: farming simulator 2013

> Reply from michalss
>
> i have unpaker for this, but dont know what is compression used
Use comptype_scanner
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-09-12T06:22:49+00:00
- Post Title: farming simulator 2013

> Reply from Ekey
>
> michalss wrote:i have unpaker for this, but dont know what is compression used 
Use comptype_scanner

Always doing it but not luck with this one
