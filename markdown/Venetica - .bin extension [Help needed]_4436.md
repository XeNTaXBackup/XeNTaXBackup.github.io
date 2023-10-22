## Post #1
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2010-05-09T12:17:44+00:00
- Post Title: Venetica - .bin extension [Help needed]

I've read about somebody else trying to extract the contents of a .bin file of Venetica, but he had no luck.

I'm curious about this .bin file, which hopefully contains the game's texts. Is editing/repacking possible?

[http://www.speedyshare.com/files/223451 ... sh_bin.rar](http://www.speedyshare.com/files/22345193/english_bin.rar)
## Post #2
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2010-05-13T12:56:50+00:00
- Post Title: Venetica - .bin extension [Help needed]

Any ideas? Anyone?
## Post #3
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-12T16:33:41+00:00
- Post Title: Venetica - .bin extension [Help needed]

Well, here's a simple .BIN viewer / exporter / importer.

Updated version! v0.999
## Post #4
- Username: Farflame
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Nov 11, 2009 12:11 am
- Post datetime: 2010-06-13T13:22:38+00:00
- Post Title: Venetica - .bin extension [Help needed]

Thank you very much, bacter. It seems you are very experienced in this kind of coding   .

Note - your utility reports 11959 entries in original bin file. But when exporting it reports only 11459 entries exported. What about the others - are there also ingame texts included in between them?
## Post #5
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-06-13T15:20:18+00:00
- Post Title: Venetica - .bin extension [Help needed]

The 11,959 means the total number of entries in the TreeView stucture, and the 11,495 is the number of editable text lines.
(This is the number of the Tree items marked with yellow pencil. Plus one, the very first line, 'LANGUAGE_ID=something')
## Post #6
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2010-09-05T14:00:32+00:00
- Post Title: Venetica - .bin extension [Help needed]

> Reply from bacter
>
> Well, here's a simple .BIN viewer / exporter / importer.

Updated version! v0.999
Well, I open a BIN file (Pina or Venetica), the window jumps left and right a bit and then nothing happens.
Apparently, this tool is defunct. Too bad.
## Post #7
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-09-06T18:50:21+00:00
- Post Title: Venetica - .bin extension [Help needed]

The program's caption says: Venetica language BIN manipulator [v0.999]
Works only with Venetica LANGUAGE BIN files.
I tested with english.bin, german.bin, chinese.bin, and czech.bin files. It works perfectly.
## Post #8
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2010-09-07T00:22:55+00:00
- Post Title: Venetica - .bin extension [Help needed]

> Reply from bacter
>
> Works only with Venetica LANGUAGE BIN files.
Oh, I must have missed that, sorry.
I was hoping for a BIN packer/unpacker for the LUA files.
## Post #9
- Username: LordRius
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 01, 2011 5:48 pm
- Post datetime: 2011-11-23T23:06:29+00:00
- Post Title: Venetica - .bin extension [Help needed]

Please i need the link for the bin tool

Anybody have the tool for manipulate Venetica language bin files??
## Post #10
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-11-29T15:31:20+00:00
- Post Title: Venetica - .bin extension [Help needed]

Important!
This is NOT the earlier published tool! So this can't handle that unpacked text, and vice versa.
To unpack use the bin file, to repack use the txt file, but the original bin always required!

The unpacked txt use UTF8 with BOM.
[VeneticaBIN.zip](https://xentaxbackup.github.io/file/10456_VeneticaBIN.zip)
## Post #11
- Username: LordRius
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 01, 2011 5:48 pm
- Post datetime: 2011-11-29T18:04:39+00:00
- Post Title: Venetica - .bin extension [Help needed]

Many thanks evin!
## Post #12
- Username: LordRius
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 01, 2011 5:48 pm
- Post datetime: 2011-11-30T09:10:07+00:00
- Post Title: Venetica - .bin extension [Help needed]

Hi evin i'm using your Venetica tool and does not work well for me, i unpack, modify and repack successfully, but when start the game, it crashes. I suppose the problem can be due the accentuated words and other non-UTF8 caracters in original spanish texts. It's strange but your DeadIslandBIN.exe works fine with spanish strings. I try to only unpack and repack the Venetica spanish.txt without any modification and the game still crashing. Any idea? Why DeadIslandBIN.exe works fine with spanish texts and VeneticaBIN.exe did not? Can you fix this issue in VeneticaBIN.exe? I'm doing something wrong?

Thanks.
## Post #13
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-11-30T10:26:22+00:00
- Post Title: Venetica - .bin extension [Help needed]

You are talking about 2 different game, 2 different engine, and 2 different text file.
I need those files to figure out what's wrong.
## Post #14
- Username: LordRius
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 01, 2011 5:48 pm
- Post datetime: 2011-11-30T10:46:05+00:00
- Post Title: Venetica - .bin extension [Help needed]

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-11-30T16:43:34+00:00
- Post Title: Venetica - .bin extension [Help needed]

Ok, fixed, previous attachment updated.
## Post #16
- Username: LordRius
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Apr 01, 2011 5:48 pm
- Post datetime: 2011-11-30T17:46:09+00:00
- Post Title: Re: Venetica - .bin extension [Help needed]

> Reply from evin
>
> Ok, fixed, previous attachment updated.
Yeeeaahh!! i tried, works fine, great work evin and many many thanks.
## Post #17
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2016-02-08T04:38:53+00:00
- Post Title: Re: Venetica - .bin extension [Help needed]

> Reply from evin
>
> Important!
This is NOT the earlier published tool! So this can't handle that unpacked text, and vice versa.
To unpack use the bin file, to repack use the txt file, but the original bin always required!

The unpacked txt use UTF8 with BOM.

Can you make a update for Black Sails's bin file? Thanks.
[Black Sails.zip](https://xentaxbackup.github.io/file/10442_Black Sails.zip)
## Post #18
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2016-02-08T06:25:41+00:00
- Post Title: Re: Venetica - .bin extension [Help needed]

> Reply from stevenx
>
> evin wrote:Important!
This is NOT the earlier published tool! So this can't handle that unpacked text, and vice versa.
To unpack use the bin file, to repack use the txt file, but the original bin always required!

The unpacked txt use UTF8 with BOM.

Can you make a update for Black Sails's bin file? Thanks.

Previous post updated with the fixed tool!
## Post #19
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2016-02-12T16:28:48+00:00
- Post Title: Re: Venetica - .bin extension [Help needed]

> Reply from evin
>
> stevenx wrote:evin wrote:Important!
This is NOT the earlier published tool! So this can't handle that unpacked text, and vice versa.
To unpack use the bin file, to repack use the txt file, but the original bin always required!

The unpacked txt use UTF8 with BOM.

Can you make a update for Black Sails's bin file? Thanks.

Previous post updated with the fixed tool!

Thanks! It worked!
