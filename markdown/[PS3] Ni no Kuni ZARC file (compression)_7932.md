## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-26T11:16:38+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

anyone know what compression this game is using? these aren't the zarc files that noesis opens.
thanks!

sample:
[http://www.mediafire.com/?vr0p2gakbvx5tl6](http://www.mediafire.com/?vr0p2gakbvx5tl6)

EDIT: oops, posted in wrong forum
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-26T14:16:48+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

Just use this command on the file.
offzip.exe -1 -a -z -15 c:\file.zarc c:\output
model format looks pretty easy.
This file actually contains 2 zarc files. also it looks to be just a slightly modified psarc file.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-26T19:53:24+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

Really? Now that's what I like to hear . I didn't see the 0x79 zlib signature used with the file list table so that confused me. I used 
my own zlib code since offzip puts the file table in different files. 

I'll check it out in a few days. Thanks!
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-29T08:03:58+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

Awesome.... figured it out thanks.
## Post #5
- Username: zanearn
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-30T21:59:44+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

if someone needs to extract the big file you can use this.

```
endian big
idstring "PSAR"
get VER short
get MVER short
getdstring COMP 0x4
get START long
get ENTRYSIZE long
get FILES long
get CHKSIZE long
get TWO long
set BASEOFF files
math BASEOFF * ENTRYSIZE
math BASEOFF + 0x20
math files - 1
getdstring null 0x15
get TSIZE long
get NULL byte
get OFFSET long
savepos TBL
set COUNT TSIZE
math COUNT / 0x10000
math COUNT + 1
goto BASEOFF
for i = 0 < COUNT
get TMP short
putarray 0 i TMP
next i
comtype unzip_dynamic
for i = 0 < COUNT
getarray ZSIZE 0 i
append
clog MEMORY_FILE OFFSET ZSIZE ZSIZE
append
math OFFSET + ZSIZE
next i
goto 0 MEMORY_FILE
goto TBL
for i = 1 to FILES
if i == FILES
savepos tmp MEMORY_FILE
get NSIZE asize MEMORY_FILE
math NSIZE - tmp
getdstring NAME NSIZE MEMORY_FILE
else
GetCT NAME string 0x0a MEMORY_FILE
endif
getdstring null 0x15
get SIZE long
get NULL byte
get OFFSET long
log NAME OFFSET SIZE
next i

```
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-31T02:15:37+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

and then, after you're run that script, put the following exe and zlib dll in the data directory and run the exe. it will extract all 20,000+ JPEG files in the data/book directory and convert all zarc files to their uncompressed forms (it will delete zarc files when done so back them up if you still want them). now somebody needs to write a model extractor. the character models aren't so great in this game but the environments are really nice...

[http://www.mediafire.com/?2wx1rw8ikncnbea](http://www.mediafire.com/?2wx1rw8ikncnbea)
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-31T02:24:39+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

> it will delete zarc files

No option to not delete them?
Unfriendly program
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-31T02:32:10+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

ha ha ha well the problem is this:

the zarc files are named f_c01_i01.hpk.zarc
and the saved names are f_c01_i01.hpk

if i get to doing the models, leaving both files in the directory, when i do a batch search for *.hpk it will also try processing the .hpk.zarc files as well. WIN32_FIND_FILE sucks. i did it to make my life a little simpler. it's just 4 lines of code to leave them back in, but i would have to include a string check to not process any file ending in .zarc.
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-12-31T02:41:48+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

ok, this one won't delete the zarc files or the dat file that contains the jazillion jpegs.

EDIT: See next post.
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-01T17:52:14+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

Continuing on, this version of the data extractor operates in 6 phases and fixes a bug in the zlib code that made some of the hpk archives a little too big. Process takes 10 minutes or so.

phase #1: finds gvd.dat and extracts JPEG files.
phase #2: finds all zarc files and decompresses them.
phase #3: finds all hpk files, which are non-compressed archives, and extracts all files from them.
phase #4: finds all pkchr files, which have same format as hpk and are also archives, and extracts all files from them.
phase #5: finds all imgpak files, which are also archives (that typically only contain two files), and extracts all files from them.
phase #6: finds all img files, which contain DDS images, and extracts all DDS images within them.

[http://www.sticklove.com/content/semory/ni_no_kuni.7z](http://www.sticklove.com/content/semory/ni_no_kuni.7z)

notes:
 character model data appears to be stored in the p3mmg files?
 p3mmg has a funky vertex format, what I got out of it looked like a uv map more than a model.
 bones data appears to be stored int the p3msk files?
 animations appear to be stored in the ask files?
 map model data is stored in mpk files. i got some geometry out of these.
 do imgpak files contain images?
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-01-06T08:26:51+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

lol this is the same f-ed up format as white knight chronicles isn't it?
## Post #12
- Username: jasin
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Aug 07, 2012 5:12 pm
- Post datetime: 2012-08-07T09:43:40+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

howfie Please update your links
## Post #13
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-01-14T15:07:39+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

.zarc use deflate compression.
data split on blocks.1 block after unpacking must have size no more 65536byte.

first row 16byte
offset 0-5  unchangeable head.
offset 6-7 quantity  of block with data
offset 8-9 quantity  of block with data that have size 65536bits after unpacking.
offset A-B unpacking size last block with data. if last block after unpacking have size 65536byte, this write null.
offset C-F size  zarc file with head.

second row and etc description of the data blocks.
description of one block is 8byte.
first 2 byte -> size block
2byte size unpacked block, if block after unpacking have size 65536byte, this write null.
4byte start offset block + 1
if one row have descriptoin only one block, then following 8 byte  write null.

start data block always start with new row.

if after end data block,  row not full,  it write null


sorry for my english
## Post #14
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-01-15T02:32:29+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

the zarc format is the easy part... [the code is here](http://code.google.com/p/sticklove/source/browse/trunk/source/xentax/ripper/ps3_ni_no_kuni.cpp). problem is the model format is time consuming.

also updated link above to the exe. maybe... maybe... one day in the future i'll come back and look at this lol.
## Post #15
- Username: dodther
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jan 07, 2013 11:14 am
- Post datetime: 2013-01-15T03:51:27+00:00
- Post Title: [PS3] Ni no Kuni ZARC file (compression?)

I have very little experience and independent analysis of the file, even such a easy, a big achievement.
Thanks for your program.
## Post #16
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-16T23:22:37+00:00
- Post Title: Re: [PS3] Ni no Kuni ZARC file (compression?)

it's possible to extract sound from this game
## Post #17
- Username: zanearn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 03, 2012 9:02 am
- Post datetime: 2013-08-01T06:31:26+00:00
- Post Title: Re: [PS3] Ni no Kuni ZARC file (compression?)

> Reply from kilik
>
> it's possible to extract sound from this game
Bar from ffshrine edited the tracks and shared them in [this post](http://forums.ffshrine.org/f72/%5Bflac%7Cmp3%5D-ni-no-kuni-ps3-complete-gamerip-110559/)

Also [a post](http://forum.xentax.com/viewtopic.php?f=17&t=7799) here discussing this matter.
## Post #18
- Username: zanearn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 03, 2012 9:02 am
- Post datetime: 2013-08-02T07:33:49+00:00
- Post Title: Re: [PS3] Ni no Kuni ZARC file (compression?)

Compiled howfie's ripper, anyone needs it please find it here:

[howfie's ni no kuni ripper](http://pan.baidu.com/share/link?shareid=757683885&uk=2066843061).

Also seems someone stitched the tiles with a function from imageMagic: [link](http://www.gamefaqs.com/boards/998014-ni-no-kuni-wrath-of-the-white-witch/65249845)
## Post #19
- Username: costelabr
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 18, 2019 10:30 pm
- Post datetime: 2019-11-18T23:08:32+00:00
- Post Title: Re: [PS3] Ni no Kuni ZARC file (compression?)

please someone have this tools to upload it again?
## Post #20
- Username: Dema
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 22, 2020 7:05 am
- Post datetime: 2020-05-21T23:16:09+00:00
- Post Title: Re: [PS3] Ni no Kuni ZARC file (compression?)

Please, somebody help me. I extracted the gvd.dat from hd05_it.adat, but i can't find the howfie's ni no kuni ripper anymore. Is there anyone who can upload it again?   
Sorry for my English
