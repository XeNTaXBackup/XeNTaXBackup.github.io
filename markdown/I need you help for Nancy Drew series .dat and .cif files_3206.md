## Post #1
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2008-11-02T02:31:09+00:00
- Post Title: I need you help for Nancy Drew series .dat and .cif files

I want to find out the subtitles in  Nancy Drew series games.
Can you take a look at the .dat and .cif files?
Thanks.
[dat-cif.rar](https://xentaxbackup.github.io/file/1714_dat-cif.rar)
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2008-12-02T21:35:48+00:00
- Post Title: I need you help for Nancy Drew series .dat and .cif files

It will be very interesting to see this game supported from the gobread! thanks anyway
## Post #3
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2008-12-03T19:31:56+00:00
- Post Title: I need you help for Nancy Drew series .dat and .cif files

> Reply from GOBREAD
>
> Time will tell...
## Post #4
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2008-12-11T17:03:50+00:00
- Post Title: I need you help for Nancy Drew series .dat and .cif files

ok, I did my homeworks. I wrote an extractor for latest Nancy Drew's games (The Haunting Of Castle Malloy and Phantom Of Venice and maybe some earlier), but i have a tiny problem:

in The Haunting Of Castle Malloy  the file with the dialogs is compiled in lua 5.1 but in the inside the format of the text is the SAME of Phantom Of Venice's that's not in LUA so there are two options:

-decompile the lua
-change some instruction in the exe taking those from phantom of venice

but i can't do anyone of that...could some one help out?  

(first 0x30 bytes are just the header of each Nancy Drew's file, nothing to do with lua)
[AUTOTEXT.rar](https://xentaxbackup.github.io/file/1777_AUTOTEXT.rar)
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2008-12-12T21:10:39+00:00
- Post Title: I need you help for Nancy Drew series .dat and .cif files

the compression used in "Legend of the Crystal Skull" and probably other titles is the classical LZSS with the input bytes less a counter:

compression:
- compress with LZSS
- for(i = 0; i < out_size; i++) out += i;

decompression:
- for(i = 0; i < in_size; i++) in -= i;
- decompress with LZSS
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2008-12-14T01:39:49+00:00
- Post Title: I need you help for Nancy Drew series .dat and .cif files

i made the  Translation Tollset for Phantom Of Venice and Castle Malloy, if anyone is interestedin translating it, he could contact me by PM and i'll pass you the text and image files with a little documentation. I won't pass the tools because they're not very user friendly and i'm not interested in doing that
## Post #7
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2008-12-18T03:53:27+00:00
- Post Title: I need you help for Nancy Drew series .dat and .cif files

> Reply from Vash
>
> i made the  Translation Tollset for Phantom Of Venice and Castle Malloy, if anyone is interestedin translating it, he could contact me by PM and i'll pass you the text and image files with a little documentation. I won't pass the tools because they're not very user friendly and i'm not interested in doing that

to Vash:
I want to know some detail about you tools.
Is this tools  a single byte to single byte Translation Tollset ?
I want to Translation from english to chinese. Is it posibble?
It seems save the text in 2 bytes?
And you have cracked the compiled lua files?

to Beutest:
Want to konw more about lzss for this game.
You means :
1-->get the 30bytes file head
2-->use lzss to decompress the rest bytes?
Can you release a tool use this way as extractor for dancy series?
## Post #8
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2008-12-18T12:40:02+00:00
- Post Title: I need you help for Nancy Drew series .dat and .cif files

I think that a chinese translation coul be possible, but you'll need to hack the fonts i guess  i have "cracked" the compiled lua files, yes..somehow  i cracked just the one that contains the text, didn't decompiled it.

i can answer for bugtest too:

the lzss compression is applied to each file in the archive, but the filename table isn't the same of the newest game and the archives also contain a 0x800 byte very strange header (after the 0x30 byte header) that i can't understand, so maybe an extractor could be possible but a reinserter is not for the moment
## Post #9
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-01-21T03:41:14+00:00
- Post Title: I need you help for Nancy Drew series .dat and .cif files

> Reply from Vash
>
> I think that a chinese translation coul be possible, but you'll need to hack the fonts i guess  i have "cracked" the compiled lua files, yes..somehow  i cracked just the one that contains the text, didn't decompiled it.

i can answer for bugtest too:

the lzss compression is applied to each file in the archive, but the filename table isn't the same of the newest game and the archives also contain a 0x800 byte very strange header (after the 0x30 byte header) that i can't understand, so maybe an extractor could be possible but a reinserter is not for the moment

I really need your help. 
can you post a detail Format description?

Head1  Begin
??         0x30Bytes   '' filename table ?
Head1  End

Head2  Begin
??         0x800Bytes   '' filename table ?
Head2  End

For Each File 
??         ??Bytes   ''classical LZSS compressed data 

Can you post or mail your tools and source to me?
I want to continue the research,thanks!

my mail:  [so750515@yahoo.co.jp](mailto:so750515@yahoo.co.jp)
## Post #10
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2009-02-02T21:08:49+00:00
- Post Title: I need you help for Nancy Drew series .dat and .cif files

I have written an unpacker for "Nancy Drews". It is in BETA-Status and extracts "TREE"-files only.
I will release a complete version within the next days. Stay tuned.
[GOBREAD.ZIP](https://xentaxbackup.github.io/file/1852_GOBREAD.ZIP)
## Post #11
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-02-02T23:55:49+00:00
- Post Title: I need you help for Nancy Drew series .dat and .cif files

> Reply from asmxtx
>
> I have written an unpacker for "Nancy Drews". It is in BETA-Status and extracts "TREE"-files only.
I will release a complete version within the next days. Stay tuned.

Wow!Very thanks!
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-02-08T23:59:06+00:00
- Post Title: I need you help for Nancy Drew series .dat and .cif files

> Reply from Vash
>
> the file with the dialogs is compiled in lua 5.1 [...] so there are two options:

-decompile the lua
Well, no decompiler, but at least recently a Lua 5.1 disassembler has come up: [http://luaforge.net/projects/chunkspy/](http://luaforge.net/projects/chunkspy/)

EDIT: It's written in Lua, another disassembler available as an exe is located here: [http://modtools.petrolution.net/tools/Lua](http://modtools.petrolution.net/tools/Lua)

Your Autotext.cif file gives the following results, pretty nicely commented 
[out.rar](https://xentaxbackup.github.io/file/1864_out.rar)
