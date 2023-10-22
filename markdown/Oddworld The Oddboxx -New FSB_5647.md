## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-12-28T07:41:07+00:00
- Post Title: Oddworld: The Oddboxx -New FSB?

This game has FSB4 audios, actually i tried a lot of programs (like: towav, fsbext, mpegfsb and to see if it's crypted i used guessfsb) to extract the data, but i can't, only i get a small wav header (44bytes)...any idea?
Well if i use the latest version of fsbext, the program can extract the audios but i can't convert to wav or mp3

> FSB files extractor 0.2.10
>
> by Luigi Auriemma
>
> e-mail: aluigi@autistici.org
>
> web:    aluigi.org
>
> 
>
> - input file:   saveload.fsb
>
> - FSB4 version 4.0 mode 64
>
> 
>
> Filename                         Size       Mode frequency channels bits
>
> ========================================================================
>
> mus_menu_01pt                    79086      00-23 44100 2 16
>
> 
>
> - 1 files processed
Thanks!   
I attach a small sample
[saveload.zip](https://xentaxbackup.github.io/file/3726_saveload.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-12-29T05:20:30+00:00
- Post Title: Oddworld: The Oddboxx -New FSB?

note that you are using an old version of fsbext and the 0.2.11 one added support for the aligned files.

anyway in the sample you attached I don't see problems, it's one file and the size is correct.
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-12-29T15:28:57+00:00
- Post Title: Oddworld: The Oddboxx -New FSB?

You right about the version now i tried with 0.2.11, can extract the audios but i can't play (i used mplayer, winamp, ffmpeg..)
I used:

> fsbext.exe -R -a saveload.fsb
>
> FSB files extractor 0.2.11
>
> by Luigi Auriemma
>
> e-mail: aluigi@autistici.org
>
> web:    aluigi.org
>
> 
>
> - input file:   saveload.fsb
>
> - FSB4 version 4.0 mode 64
>
> - aligned files
>
> 
>
> Filename                         Size       Mode frequency channels bits
>
> ========================================================================
>
> mus_menu_01pt                    79086      00-23 44100 2 16
>
> 
>
> - 1 files processed
And i get this wav..what im doing wrong?  
[mus_menu_01pt.zip](https://xentaxbackup.github.io/file/3736_mus_menu_01pt.zip)
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-12-30T13:13:45+00:00
- Post Title: Oddworld: The Oddboxx -New FSB?

So far: There are frames with an 8 byte header, all seem to be 0x8B long. First 4 bytes are all 17 C3 0D F3, which may be a stream ID, next 4 are little endian 8B, which is the size of the payload. Payload has some interesting patterns but I haven't identified it yet. Looks possibly encrypted, maybe just compressed.
[edit] Almost certainly compressed, the only bits in the whole frame which are unevenly distributed are the first ten and the last two. This does lead to the weird question of why compressed yet fixed frame sizes... if you could put up some more files I'd be happy to take a look.
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-12-30T19:32:37+00:00
- Post Title: Oddworld: The Oddboxx -New FSB?

Sure no problem, uploaded 6 new files:
[http://www.mirrorcreator.com/files/MGUV ... .rar_links](http://www.mirrorcreator.com/files/MGUV6ICQ/oddworld.fsbs.rar_links)
If you need more files just ask.
## Post #6
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-08T11:22:03+00:00
- Post Title: Oddworld: The Oddboxx -New FSB?

i keep blocking for extract fsb
