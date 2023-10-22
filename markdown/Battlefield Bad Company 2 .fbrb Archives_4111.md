## Post #1
- Username: zeroy
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Feb 03, 2010 6:08 pm
- Post datetime: 2010-02-03T15:16:32+00:00
- Post Title: Battlefield Bad Company 2 .fbrb Archives

Just a quick note to thank Aluigi for QuickBMS and the fbrb.bms script, it works fine to unpack most of the .fbrb archive in the BFBC2 Beta!
 

I attached the QuickBMS scripts Aluigi posted in another thread,
[quickbms_bfbc2.zip](https://xentaxbackup.github.io/file/2765_quickbms_bfbc2.zip)
## Post #2
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-02-05T15:39:36+00:00
- Post Title: Battlefield Bad Company 2 .fbrb Archives

Sounds really nice trying to unpack that now
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-05T16:01:56+00:00
- Post Title: Battlefield Bad Company 2 .fbrb Archives

oh I forgot that yesterday I updated the main script because an user reported an error with the file "ondemand_awards-00.fbrb".

the link to the updated script is ever the same: [http://aluigi.org/papers/bms/fbrb.bms](http://aluigi.org/papers/bms/fbrb.bms)

while the following is the technical explanation of the problem (that was not caused by the script, it was an error in the format that specified a gzip file bigger than its real size):

> practically each gzip file has a 32bit value at its end specifying the
>
> size of the uncompressed data and so, logically, the script readed it
>
> for calculating how much is the uncompressed size but in the case of the
>
> file you uploaded the size of the archived gzip file was bigger than its
>
> real one and so the latest 32bit value was zero because various bytes
>
> after the location of the correct 32bit field.
## Post #4
- Username: nightvison
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 20, 2009 2:35 pm
- Post datetime: 2010-02-28T08:39:31+00:00
- Post Title: Battlefield Bad Company 2 .fbrb Archives

How can I repack the unpacked files?
## Post #5
- Username: pirateplunder
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 01, 2010 8:42 pm
- Post datetime: 2010-03-01T15:10:10+00:00
- Post Title: Battlefield Bad Company 2 .fbrb Archives

aluigi

Can you tell me how you got around the problem of the ondemand_awards-00.fbrb - the one (and theres another one) where the given size of the first compressed block is wrong, and then the uncompressed size of the block is of course not returned properly.

I've been developing an unpacker/packer in C# but am completely stuck getting this fbrb to decompress.
## Post #6
- Username: nightvison
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 20, 2009 2:35 pm
- Post datetime: 2010-03-05T05:45:21+00:00
- Post Title: Battlefield Bad Company 2 .fbrb Archives

I use your script, but only on the overlay-00.fbrb file.
The unpacked dirs and files i copy the Output\win32  and i rename the original overlay-00.fbrb to overlay-00.fbrb.bak
and works!
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-07T22:48:42+00:00
- Post Title: Battlefield Bad Company 2 .fbrb Archives

@pirateplunder
I used a simple and basic work-around, because the good way would be the incremental decompression of the data ignoring the size field at the end of the gzip file.

practically I get all the 32 bit fields from the end of the file one by one (so for example first the 32bit field at offset 0x1234, then 0x1233, 0x1232 and so on) and if this value is major than zero and not negative then I use it.
## Post #8
- Username: LukLuk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 13, 2010 3:37 am
- Post datetime: 2010-04-14T19:18:29+00:00
- Post Title: Battlefield Bad Company 2 .fbrb Archives

Hey guys!

I've just found this forum through google and i've successfully unpacked the .fbrb files, thanks man!

I've got one question: I have extracted many soundfiles from the game and wanted to play them, but they are compiled into .res. Does anybody know how to play them, so i can listen or record them?
## Post #9
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-04-14T20:12:35+00:00
- Post Title: Battlefield Bad Company 2 .fbrb Archives

hcs was trying to figure it out for the pc version, supposedly xbox can already be played with a whole load of steps.
## Post #10
- Username: LukLuk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 13, 2010 3:37 am
- Post datetime: 2010-04-16T16:45:58+00:00
- Post Title: Battlefield Bad Company 2 .fbrb Archives

So there is no way to play them at the moment? =(
## Post #11
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2010-08-02T09:43:53+00:00
- Post Title: Battlefield Bad Company 2 .fbrb Archives

Pls help me create or repack .fbrb archive.
Please
