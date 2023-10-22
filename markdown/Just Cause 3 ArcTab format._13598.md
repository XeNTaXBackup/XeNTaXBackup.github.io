## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2015-12-01T17:03:49+00:00
- Post Title: Just Cause 3 Arc/Tab format.

If anyone can take a look thanks.

[https://www.sendspace.com/file/w516pe](https://www.sendspace.com/file/w516pe)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-12-01T23:40:53+00:00
- Post Title: Just Cause 3 Arc/Tab format.

You provided invalid TAB file (game33.tab) for ARC (game34.arc). Anyway try this [http://aluigi.altervista.org/bms/justcause2.bms](http://aluigi.altervista.org/bms/justcause2.bms)
## Post #3
- Username: shakotay2
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-12-02T20:31:44+00:00
- Post Title: Just Cause 3 Arc/Tab format.

Very simple format. Looked at this yesterday.

1. .tab files contain the filetable, offsets to files and their hashes.
2. .arc contains the actual filedata.
3. Each tab is paired with an .arc file. It also has a .txt file paired containing all the filenames including their hashes (looks like devs accidentally left them over).
4. Don't ask me about compression, some files might be compressed and there's probably a flag somewhere. It should be zlib.

```
{
	unsigned int m_hashedName;
	unsigned int m_fileOffset;
	unsigned int m_fileSize;
};

struct tab
{
	unsigned int m_magic;//"TAB "
	unsigned short m_unk00;//Probably version always 2
	unsigned short m_unk01;//Always 1?
	unsigned long  m_unk02;//Alignment?
	tabFileEntry[numFiles];
};

numFiles = (tabfileSize-0xC)/0xC;

```
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-02T23:58:18+00:00
- Post Title: Just Cause 3 Arc/Tab format.

yeah, totally easy. You can even cut an uncompressed file from the .arc using a hexeditor and create a wav from it using daemon1's fmod_extr:


 2107115430.zip
(241.57 KiB) Downloaded 70 times



```
========== ========== ========== ==========  ==========
0x9437BC85 0x00000000 0x0000DD10 0x0000DD10  sound/dialogue/bra/mission_mm220_dial_gameplay_shieldup_010.wavc
```


btw: it's not from the .arc in the opening post - it's from game55.arc in another parallel thread that obviously has been deleted to not confuse people.
## Post #5
- Username: iUltimateLP
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 11, 2014 12:24 am
- Post datetime: 2015-12-03T09:23:59+00:00
- Post Title: Just Cause 3 Arc/Tab format.

Yep, that was my post.. No matter, is there any easier way than cutting this with a hex editor? I mean, the files are 800MB big
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-03T12:18:40+00:00
- Post Title: Just Cause 3 Arc/Tab format.

easy ways are boring, aren't they?

here you go (tested with Sound Archive game55.arc only!):

```
# script for QuickBMS http://quickbms.aluigi.org

open FDDE "tab" 0
open FDDE "arc" 1

set EXT string "fsb"

get ARC_SIZE asize 1
get TAB_SIZE asize
goto 12

for i = 0
    savepos CURR_OFF
    if CURR_OFF >= TAB_SIZE
        cleanexit
    endif
    get NAME_CRC long
    get OFFSET long
    get FSIZE long

    math OFFSET += 16
    math FSIZE -= 16
    
    string NAME p= "%08x.%s" NAME_CRC EXT
    log NAME OFFSET FSIZE 1
next i
```

Will extract 1365 fsb files from game55.arc.
Filenames are not "un-hashed", sry.
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-12-03T12:25:46+00:00
- Post Title: Just Cause 3 Arc/Tab format.

Almost finish.

See below.
## Post #8
- Username: CzlowiekDrzewo
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 17, 2014 5:46 pm
- Post datetime: 2015-12-03T13:45:58+00:00
- Post Title: Just Cause 3 Arc/Tab format.

How can I find a particular file in an .arc archive using hash names in Hex Editor?
## Post #9
- Username: iUltimateLP
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 11, 2014 12:24 am
- Post datetime: 2015-12-03T14:04:22+00:00
- Post Title: Just Cause 3 Arc/Tab format.

> Reply from CzlowiekDrzewo
>
> How can I find a particular file in an .arc archive using hash names in Hex Editor?
Get the Byte offset and the length, then a great hex editor like HxD, open the arc file where its inside, calculate the end adress with a hex calculator (byte offset + length), and mark all bytes between the start and end adress. Copy that in a new file and save it as the extension you need, and your done. In HxD you can use Ctrl+E for easier selecting of a range of bytes
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-12-03T14:56:24+00:00
- Post Title: Just Cause 3 Arc/Tab format.

Ok, unpacker is out. I will share packer later.

[https://www.sendspace.com/file/nel9xi](https://www.sendspace.com/file/nel9xi)
## Post #11
- Username: iUltimateLP
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 11, 2014 12:24 am
- Post datetime: 2015-12-03T17:50:57+00:00
- Post Title: Just Cause 3 Arc/Tab format.

> Reply from Ekey
>
> Ok, unpacker is out. I will share packer later.

https://www.sendspace.com/file/nel9xi
Nice, but how to actually extract a file? This looks more like a viewer to me..
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-12-03T18:23:57+00:00
- Post Title: Just Cause 3 Arc/Tab format.

> Reply from iUltimateLP
>
> Ekey wrote:Ok, unpacker is out. I will share packer later.

https://www.sendspace.com/file/nel9xi
Nice, but how to actually extract a file? This looks more like a viewer to me..
Just open tab index file. Extracting files will be automaticly! You must see output directory with extracted files in same tab folder > Unpacked. Examples:

```
Output directory will be here: e:\Games\Just Cause 3\archives_win64\Unpacked
```

Packer for test only
[https://www.sendspace.com/file/hmugmy](https://www.sendspace.com/file/hmugmy)

Make backup files!
## Post #13
- Username: iUltimateLP
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Dec 11, 2014 12:24 am
- Post datetime: 2015-12-03T18:35:35+00:00
- Post Title: Just Cause 3 Arc/Tab format.

Ah lol didn't know that, thanks for your work!!
## Post #14
- Username: MightWeasel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 02, 2015 11:50 pm
- Post datetime: 2015-12-03T18:58:07+00:00
- Post Title: Just Cause 3 Arc/Tab format.

Can anyone help me getting a high rez image file of the map pls? Would be very appreciated.
## Post #15
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-12-04T12:21:18+00:00
- Post Title: Just Cause 3 Arc/Tab format.

I don't have the game, is anyone able to share a model file?
## Post #16
- Username: CzlowiekDrzewo
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Aug 17, 2014 5:46 pm
- Post datetime: 2015-12-04T12:57:35+00:00
- Post Title: Re: Just Cause 3 Arc/Tab format.

Is there any way to extract .bank files? I tried fsb extractor but all I get is error message: 'Not a valid FSB file format (file id 046464952)'.
## Post #17
- Username: TheAmazingX
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 12, 2015 5:18 pm
- Post datetime: 2015-12-12T09:20:25+00:00
- Post Title: Re: Just Cause 3 Arc/Tab format.

Hi...To the person who made the ARC Unpacker/Packer...

Do you know how to add more DLC to the name.txt files under the Just Cause 3 DLC directory please? I combined a few DLC's into one .arc and .tab for neatness but then I cannot make a call to it from "name.txt"

It seems to only take 1 dlc name....help?
## Post #18
- Username: yoyodaman234
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 21, 2012 3:10 pm
- Post datetime: 2016-01-26T05:37:17+00:00
- Post Title: Re: Just Cause 3 Arc/Tab format.

> Reply from shakotay2
>
> yeah, totally easy. You can even cut an uncompressed file from the .arc using a hexeditor and create a wav from it using daemon1's fmod_extr:
2107115430.zip
Code: Select allHASH       BYTEOFFSET SIZE       DCOMP SIZE  NAME      
========== ========== ========== ==========  ==========
0x9437BC85 0x00000000 0x0000DD10 0x0000DD10  sound/dialogue/bra/mission_mm220_dial_gameplay_shieldup_010.wavc

btw: it's not from the .arc in the opening post - it's from game55.arc in another parallel thread that obviously has been deleted to not confuse people.

How did you use fmod_extr get a wav from the wavc dialogue files? I could only get an error message:

> Unsupported file or audio format.
And could someone look into the weird ogg format the music is in, nothing I've used is able to recognise them.
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-26T21:30:07+00:00
- Post Title: Re: Just Cause 3 Arc/Tab format.

> Reply from yoyodaman234
>
> How did you use fmod_extr get a wav from the wavc dialogue files? I could only get an error message:
Unsupported file or audio format.I passed the filename as a parameter to the exe iirc.

Did you check your FSB file to start with 46 53 42 35 01 (FSB5)?
## Post #20
- Username: yoyodaman234
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 21, 2012 3:10 pm
- Post datetime: 2016-01-26T22:41:34+00:00
- Post Title: Re: Just Cause 3 Arc/Tab format.

I figured out what the problem was. The file does contain the FSB5 header, but there was an extra line above it. Removed this and it worked perfectly. It's going to be annoying to do this to every dialogue file though.
[jc3vox_hexproblem.jpg](https://xentaxbackup.github.io/file/10368_jc3vox_hexproblem.jpg)
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-01-27T22:33:04+00:00
- Post Title: Re: Just Cause 3 Arc/Tab format.

> Reply from yoyodaman234
>
> Removed this and it worked perfectly. It's going to be annoying to do this to every dialogue file though. 
You've to search for "FSB5" in the archives and use the finds as starting addresses for fsb file extraction.

If you can't code search for a suiting bms script (quickbms) and try to modify it.
(I remember quickbms script having a feature to search for bytes: FindLoc)
## Post #22
- Username: desperado
- Rank: beginner
- Number of posts: 25
- Joined date: Thu Aug 21, 2014 2:54 am
- Post datetime: 2016-07-24T15:11:35+00:00
- Post Title: Re: Just Cause 3 Arc/Tab format.

> Reply from Ekey
>
> iUltimateLP wrote:Ekey wrote:Ok, unpacker is out. I will share packer later.

https://www.sendspace.com/file/nel9xi
Nice, but how to actually extract a file? This looks more like a viewer to me..
Just open tab index file. Extracting files will be automaticly! You must see output directory with extracted files in same tab folder > Unpacked. Examples:
Code: Select allTab Location: e:\Games\Just Cause 3\archives_win64\game2.tab
Output directory will be here: e:\Games\Just Cause 3\archives_win64\Unpacked
Packer for test only
https://www.sendspace.com/file/hmugmy

Make backup files!

Hello, packer is dead. Can you reupload it?
## Post #23
- Username: AnushkaChakrabart
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 05, 2016 2:56 pm
- Post datetime: 2016-08-08T07:08:47+00:00
- Post Title: Re: Just Cause 3 Arc/Tab format.

Will anybody help me getting a high rez picture document of the guide pls?
## Post #24
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-03-04T13:29:22+00:00
- Post Title: Re: Just Cause 3 Arc/Tab format.

Does anybody know how enable file name logging?
I tried to use Procmon to collect file names, but it works only on Mad Max. JC3 doesn't log them at all, even when I'll create dropzone folder.
So if anyone know, please how did you get hashed filenames?
