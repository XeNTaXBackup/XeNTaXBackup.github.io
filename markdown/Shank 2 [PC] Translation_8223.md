## Post #1
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2012-02-08T13:12:38+00:00
- Post Title: Shank 2 [PC] Translation

Hi, folks. 

Since Shank 2 came out I'm thinking to buy the game but first decided to try the pirate version and test it out and try if the game can be translated, but i can't find where are the text files (maybe the text is encoded into the .exe) but i don't have the skills to research where are they and that's why i have created this thread. I think that there are many fans of the game and if the other members here can help with the translation.

This is the original (non-cracked) .exe - [http://uploading.com/files/4cdme4d2/Sha ... 2BExe.rar/](http://uploading.com/files/4cdme4d2/Shank2%2BOriginal%2BExe.rar/)

Is there a way to find the text and fully translate the game or there is no chance for translation?

I haven't tried with Shank 1 but i think that the files and the engine are the same.
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-02-08T17:49:01+00:00
- Post Title: Shank 2 [PC] Translation

Engine in Shank 2 is new and it differs from Shank 1. Unfortunately (for translators).
Some texts are in .lua files, but I don't know (yet) if game reads them.

And also textures are in new format (Shank 1 used .dds, and menus are made in Scaleform GFx).

EDIT: Texts are in .chui files.

Now textures have KTEX header. 

Some examples in attachment.
[shank2_textures.7z](https://xentaxbackup.github.io/file/5045_shank2_textures.7z)
## Post #3
- Username: afsoongar
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 04, 2012 4:53 pm
- Post datetime: 2012-02-11T07:18:34+00:00
- Post Title: Shank 2 [PC] Translation

We help you to decode files KTEX header
## Post #4
- Username: pitbon1986
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 05, 2012 5:55 pm
- Post datetime: 2012-02-11T12:52:46+00:00
- Post Title: Shank 2 [PC] Translation

I need a tool to unpack / repack. tex files of shank 2 because I want to make the Italian translation. THx very much for help
## Post #5
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-02-12T16:32:35+00:00
- Post Title: Shank 2 [PC] Translation

Guys,
Does anybody knows what means these values?
## Post #6
- Username: lily4761
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Feb 14, 2012 6:40 am
- Post datetime: 2012-02-14T03:55:16+00:00
- Post Title: Shank 2 [PC] Translation

I can not find any information
hope the tools
## Post #7
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-02-14T07:43:35+00:00
- Post Title: Shank 2 [PC] Translation

I'm not good at QuickBMS scripting, but I have made this and it works.
TEX2DDS script will convert .tex texture to .dds (DXT5) and also extract that unknown values to separate .ktex file

```
# TEX to DDS converter
# by MerlinSVK    Feb 2012
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
get NAME basename
string DNAME = NAME
string DNAME += ".dds"
string KNAME = NAME
string KNAME += ".ktex"

get ASIZE asize
getdstring KTEX 0x8
get WIDTH short
get HEIGHT short
getDString UNK 0x6        # get that 6 unknown values
log KNAME 0xC 0x6         # save them to .ktex file

math DATASIZE = ASIZE 
math DATASIZE -= 0x12     # 0x12 = size of KTEX header
savepos START

putVarChr MEMORY_FILE 0XC HEIGHT short
putVarChr MEMORY_FILE 0x10 WIDTH short

append
log MEMORY_FILE START DATASIZE
append

get DDSSIZE asize MEMORY_FILE
log DNAME 0 DDSSIZE MEMORY_FILE

```

If you will try to convert .tex files with only numbers in base name such as, 1.tex, 2.tex, ... QuickBMS will ask you for new name for .ktex file. I don't know if it's because my bad coding, or it is a bug in QuickBMS. But, simply add any letter to that file (a1.tex, abcd2.tex, ...) and you will be fine. 

DDS2TEX. Doesn't need an explanation   

```
# DDS to TEX converter
# by MerlinSVK    Feb 2012
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

set MEMORY_FILE binary "\x4B\x54\x45\x58\x00\x00\x01\x02\xAA\xAA\xBB\xBB\xCC\xCC\xDD\xDD\xEE\xEE"

open FDDE DDS 0
open FDDE KTEX 1

get NAME basename
string NAME = NAME
string NAME += ".tex_NEW"  # change extension, as you wish

get ASIZE asize 0
goto 0xC 0
get HEIGHT short 0
get DUMMY short 0
get WIDTH short 0
goto 0x80 0

savepos START 0
math DATASIZE = ASIZE
math DATASIZE -= 0x80     # 0x80 = size of DDS header

putVarChr MEMORY_FILE 0x8 WIDTH short
putVarChr MEMORY_FILE 0xA HEIGHT short
# correction of KTEX header in final .tex file
set CORRECTION short 0x0201
putVarChr MEMORY_FILE 0x6 CORRECTION short
# correction

get UNK1 short 1
get UNK2 short 1
get UNK3 short 1

putVarChr MEMORY_FILE 0xC UNK1 short
putVarChr MEMORY_FILE 0xE UNK2 short
putVarChr MEMORY_FILE 0x10 UNK3 short

append
log MEMORY_FILE START DATASIZE
append

get TEXSIZE asize MEMORY_FILE
log NAME 0 TEXSIZE MEMORY_FILE

```


And if you can make that scripts harder, better, faster, stronger, do it.
## Post #8
- Username: lily4761
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Feb 14, 2012 6:40 am
- Post datetime: 2012-02-14T10:12:23+00:00
- Post Title: Shank 2 [PC] Translation

> Reply from merlinsvk
>
> I'm not good at QuickBMS scripting, but I have made this and it works.
TEX2DDS script will convert .tex texture to .dds (DXT5) and also extract that unknown values to separate .ktex file
Code: Select all# Game: Shank 2 (PC)
# TEX to DDS converter
# by MerlinSVK    Feb 2012
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
get NAME basename
string DNAME = NAME
string DNAME += ".dds"
string KNAME = NAME
string KNAME += ".ktex"

get ASIZE asize
getdstring KTEX 0x8
get WIDTH short
get HEIGHT short
getDString UNK 0x6        # get that 6 unknown values
log KNAME 0xC 0x6         # save them to .ktex file

math DATASIZE = ASIZE 
math DATASIZE -= 0x12     # 0x12 = size of KTEX header
savepos START

putVarChr MEMORY_FILE 0XC HEIGHT short
putVarChr MEMORY_FILE 0x10 WIDTH short

append
log MEMORY_FILE START DATASIZE
append

get DDSSIZE asize MEMORY_FILE
log DNAME 0 DDSSIZE MEMORY_FILE

If you will try to convert .tex files with only numbers in base name such as, 1.tex, 2.tex, ... QuickBMS will ask you for new name for .ktex file. I don't know if it's because my bad coding, or it is a bug in QuickBMS. But, simply add any letter to that file (a1.tex, abcd2.tex, ...) and you will be fine. 

DDS2TEX. Doesn't need an explanation   
Code: Select all# Game: Shank 2 (PC)
# DDS to TEX converter
# by MerlinSVK    Feb 2012
# script for QuickBMS    http://aluigi.org/papers.htm#quickbms

set MEMORY_FILE binary "\x4B\x54\x45\x58\x00\x00\x01\x02\xAA\xAA\xBB\xBB\xCC\xCC\xDD\xDD\xEE\xEE"

open FDDE DDS 0
open FDDE KTEX 1

get NAME basename
string NAME = NAME
string NAME += ".tex_NEW"  # change extension, as you wish

get ASIZE asize 0
goto 0xC 0
get HEIGHT short 0
get DUMMY short 0
get WIDTH short 0
goto 0x80 0

savepos START 0
math DATASIZE = ASIZE
math DATASIZE -= 0x80     # 0x80 = size of DDS header

putVarChr MEMORY_FILE 0x8 WIDTH short
putVarChr MEMORY_FILE 0xA HEIGHT short
# correction of KTEX header in final .tex file
set CORRECTION short 0x0201
putVarChr MEMORY_FILE 0x6 CORRECTION short
# correction

get UNK1 short 1
get UNK2 short 1
get UNK3 short 1

putVarChr MEMORY_FILE 0xC UNK1 short
putVarChr MEMORY_FILE 0xE UNK2 short
putVarChr MEMORY_FILE 0x10 UNK3 short

append
log MEMORY_FILE START DATASIZE
append

get TEXSIZE asize MEMORY_FILE
log NAME 0 TEXSIZE MEMORY_FILE


And if you can make that scripts harder, better, faster, stronger, do it.

you are awesome
## Post #9
- Username: pitbon1986
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 05, 2012 5:55 pm
- Post datetime: 2012-02-14T15:39:31+00:00
- Post Title: Shank 2 [PC] Translation

thx sooooo much man
## Post #10
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-02-16T15:15:02+00:00
- Post Title: Shank 2 [PC] Translation

Are they working correctly?

And guys, what about fonts? I tried to add chars from slovak alphabet, but game totally ignores them. It looks like game has defined range of chars, something like 32 - 128, and everything above 128 (which actually is that big red exclamation mark) is ignored. I hope, I'm wrong.
## Post #11
- Username: pitbon1986
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 05, 2012 5:55 pm
- Post datetime: 2012-02-16T17:51:58+00:00
- Post Title: Shank 2 [PC] Translation

I extracted a lot of .tex file and everything worked perfectly, creating (for each .tex file): a .dds file and a .tex file of small size.
In these days, I'll modify some .dds files, I'll recreate the .tex file and then test it in-game (I'll let you know if everything works).

As for the fonts: you must only use the English vocabulary, avoiding the use of accents and using apostrophes in their place. To change the text you have to edit .chui files respecting the number of hexadecimal characters.

Example: when you find a written, check the previous character to the first letter, that character index the number of characters used for the word. You must edit the text and change the index character in the match those characters used in the written. (So is probabily that you insert or delete some characters in the file).
## Post #12
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-02-16T18:05:34+00:00
- Post Title: Shank 2 [PC] Translation

Yeah, I saw that "string length" byte there, but I'm litle bit angry because of that character problem   
It would be cool to have full alphabet in game.
## Post #13
- Username: afsoongar
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 04, 2012 4:53 pm
- Post datetime: 2012-02-17T07:00:06+00:00
- Post Title: Shank 2 [PC] Translation

Hello

Please see guide for making Alphabetical

fonts Fnt file

Programs do

With respect
## Post #14
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-02-17T08:32:06+00:00
- Post Title: Shank 2 [PC] Translation

afsoongar, what guide you mean?
## Post #15
- Username: afsoongar
- Rank: n00b
- Number of posts: 17
- Joined date: Wed Jan 04, 2012 4:53 pm
- Post datetime: 2012-02-17T15:49:12+00:00
- Post Title: Shank 2 [PC] Translation

i wonder how can i create arabic font in the format of Fnt file with low size so i can import it to my translated game?

thanks in advanced
## Post #16
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-02-17T16:11:55+00:00
- Post Title: Re: Shank 2 [PC] Translation

Try this [http://www.angelcode.com/products/bmfont/](http://www.angelcode.com/products/bmfont/)
I made all fonts there.

For example:
## Post #17
- Username: pitbon1986
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 05, 2012 5:55 pm
- Post datetime: 2012-02-20T13:53:15+00:00
- Post Title: Re: Shank 2 [PC] Translation

I modified dds, reimported and all ok. Good work merlinsvk.

For the font: i don't know
## Post #18
- Username: XpucmoBG
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Apr 30, 2011 3:27 am
- Post datetime: 2012-02-22T13:50:51+00:00
- Post Title: Re: Shank 2 [PC] Translation

How to edit the text files? I live in a country where the alphabet is cyrillic and I don't know how to create the font. I would appreciate any help.
