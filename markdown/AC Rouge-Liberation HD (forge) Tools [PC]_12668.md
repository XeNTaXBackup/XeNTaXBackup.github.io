## Post #1
- Username: StrunPS
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-09T07:44:15+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

Here is ARC and ACLHD repacker for all, sharing my tools, just a few things berfore you gonna use it. Repacker works only for non extended files and PC files!!! It is very complicated format and this will take time, so please be patients. Repack can be done only without the compression because i did not finish the crc adler check yet.

I have test repacker on all forge files and they are all working ok but with this ext files exception... If you like it please hit thanx button on the bottom.. 




Download Michalss AC Repacker

```
https://own.cloudproject.cz/cloudproject/index.php/s/NoKtvUoc95VivRG
```
## Post #2
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-03-10T00:59:03+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

Aside from the endianess, I can't see why this would be much different from AC:Unity or possibly even AC:4.  As I haven't written any of the structures out since AC:1 this will take me as little longer than one sitting.  So here's the start, and I'll keep filling it in.

```
       0    Byte[8]     "scimitar" null-terminated string (The same in every AC/POP game, so far)
      13    Int64e      Index Table Pointer (absolute)

...Skip to Index Table Pointer (this file 1050)

    1050    Int32e      File Count (files contained in this forge file)
    1078    Int32e      Index File Count (files contained in this index)
    1102    Int64e      Index Start Pointer (absolute)
    1110    Int64e      Next Index Table Pointer (absolute, -1 if no other indexes are present)
    1118    Int32e      Start Index
    1122    Int32e      End Index
    1126    Int64e      Filename Table Pointer (absolute)
    1134    Int64e      End of Filename Table (absolute, possible pointer for something else unknown)

[IF multiple Index Tables are present] (repeat until no other indexes are present)

...Skip to Next Index Table Pointer (not present in this file, information based on ACIV:Black Flag forge file)

       0    Int32e      Index File Count (files contained in this index)
       8    Int64e      Index Start Pointer (absolute)
      16    Int64e      Next Index Table Pointer (absolute, -1 if no other indexes are present)
      24    Int32e      Start Index
      28    Int32e      End Index
      32    Int64e      Filename Table Pointer (absolute)
      40    Int64e      End of Filename Table (absolute, possible pointer for something unknown)

[ENDIF]

...Skip to Index Start Pointer (this file 1142)

Index block (repeat equal to File Count)

       0    Int64e      File Data Pointer (absolute)
       8    Int64e      File Data ID
      16    Int32e      File Data Size

...Skip to Filename Table Pointer (this file 1242)

Filename block (repeat equal to File Count)

       0    Int32e      File Data Size (should match file data size from index block respectively)
       4    Int64e      File ID
      40    Int32e      Timestamp
      44    Byte[128]   Filename null-terminated string (some filenames are empty strings)
     172    Byte[20]    Unknown

...Skip to first File Data Pointer

```


A couple edits to the above for clarification.

I haven't gotten much farther than this yet, and will continue tomorrow.  So far, everything I have outlined has been little-endian.  I have seen this with other xBox AC offerings so it comes as no surprise to me.  That's why I have tagged the types above with a little "e", because that's how they should be read.

--MDA
## Post #3
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-10T10:04:40+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

man that is perfect... please continue with this and keep us posted... 

thx
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-11T12:58:26+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

ok made a binary template for this and made some modigications also you have a small mistake in struct :

In line with   8   Int32e     File Data ID is wrong need to be  Int64e 

also there is some kind of crc, do you anything about it pls ?



But i have to say your struct template made my day  please if you can continue with this coz this are very rare informations
## Post #5
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-03-12T03:42:33+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

> Reply from michalss
>
> ok made a binary template for this and made some modigications also you have a small mistake in struct :

In line with   8   Int32e     File Data ID is wrong need to be  Int64e

I see that now and fixed the post above, also had another error with a skip to.  I wonder if this may have changed with Rogue and is the reason why my Unity routines won't open the files.  Just to clarify, for anyone not following, I am referring to an [issue](http://forum.xentax.com/viewtopic.php?p=104166#p104166) loriscangini is having with the PC version of Rogue.

Actually, just checked a Unity forge file again and it looks like that should be 64-bit also.  I'll have to see if that changes anything.  Good eye michalss 

> Reply from michalss
>
> also there is some kind of crc, do you anything about it pls ?

Not sure what you are referring to.  Where at in the file?

Continuing on...

Next we tackle the individual "datafiles".  Some of these will be compressed, some will not.  This is also where things switch to big-endian.

We'll start with the compressed datafiles (3 out of the 4 datafiles in this forge file are compressed):

```
       0    Int64E      17,179,869,184 - Not sure what this, not always present in the PC version
       8    Int64E      1,154,322,941,026,740,787 - This signifies a compressed chunk, may be more than one per datafile
      16    Int16E      Compression Type    1 = lzo1x
                                            2 = lzo2a
                                            5 = lzo1c
      18    Byte        Unknown
      19    UInt16E     Min Size (appears to always be 32,768)
      21    UInt16E     Max Size (appears to always be 32,768)
      23    UInt16E     LZO Block Count

LZO Blocks (repeat equal to LZO Block Count)

       0    UInt16E     Uncompressed block size
       2    UInt16E     Compressed block size

Compressed data (repeat equal to LZO Block Count)

       0    Int32E     Possible checksum
       4    Byte[xx]    Compressed data xx = Compressed block size for each respective LZO Block
```


At this point, if you are not beyond the file data size I would read another UInt64E.  If it matches the compressed chunk signature, repeat the decompression routine.  ARchive_neXt decompresses all chunks to a single file (original AC:1 information stated that wasn't necessary, but I find it easier to read if it's a single uncompressed file).  If uncompressed size equals compressed size, there is no need to decompress that data.  Also not positive all three of those compression types are valid for forge files, but they are the ones that I use in my dll.  However, I believe you will only find that one type of compression is used throughout the game (in this case it should be lzo1x).

Uncompressed "datafiles":

Without looking at more all I can tell you is if the first UInt64E does not equal 17,179,869,184 or 1,154,322,941,026,740,787 back up 8 bytes and read it as uncompressed data equal to the file data size for the respective datafile.

For this forge file, the first datafile located at 3083 is not compressed, so starting at 3083 read 280 bytes and that would be the contents of "GlobalMetaFile".  I have never figured out what these files are, every forge file has one.

Hope this helps somewhat.  Next up I'll tackle reading the expanded datafiles.

--MDA
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-12T20:14:54+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

Hi,

I did another a few test to verify your finding and i have a few questions

Whole this part i guess is not right  

```

       0    UInt16E     Uncompressed block size
       2    UInt16E     Compressed block size

Compressed data (repeat equal to LZO Block Count)

       0    Int32E     Possible checksum
       4    Byte[xx]    Compressed data xx = Compressed block size for each respective LZO Block
```


because it seems that LZO Block Count is always 1, and if maximum chunk is 32768 it means it must be more then only 1 Block Count   Also it looks like kind of double header, strange there need to be some kind of how many chunks that file contains right ?
 Can you please double check this ? Also  this :

   0    Int32E     Possible checksum is actually 2 crc checks seems splitted in to int16 crc1 and int16 crc2 adler32 checksum... (infromation from other Ac games, not sure if true  )


also uploaded bigger file:

```
https://dl.dropboxusercontent.com/u/38234344/Data360.forge
```
## Post #7
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-03-12T21:02:20+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

Anyone managed to extract the audio in this game? If so, what's the process of it?

Thanks.
## Post #8
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-13T20:11:30+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

Ok every byte from dat files is know now, thanks to my old templates and my one good friend( with crc part crap  ) That crc part is most likely not really crc, but current position checksum calculation

Template is still a bit mess but it is very usable .... Thx MDA for help, now im able to write repacker for X360,PC version.... 

```
//--- 010 Editor v6.0.1 Binary Template
//
// File: ACr. DAT
// Author: michalss
// Revision: V2.0
// Purpose: X360 version of Game
//--------------------------------------

BigEndian();

local uint x,y,chunk_count,gamma,i,crckonew,crckoorig;

uint64 notsure;

struct HEAD_one {
uint64 sign;
ushort com_type;
byte lzo_block_ver;
ushort compress_size_block_max;
ushort uncompress_size_block_max;
ushort lzo_block_count;

local uint chunks_compress[lzo_block_count];
local uint chunks_deccompress[lzo_block_count];

for (x=0;x<lzo_block_count;x++) 
{
    struct COMP {
         ushort decompresschunksize;
         ushort compresschunksize;
         chunks_compress[y]=compresschunksize;
         chunks_deccompress[y]=decompresschunksize;
    } block;  
}

struct CRC_HedaerdataBlock {
for(i=0;i<lzo_block_count;i++) {
    struct blokdata_header {
        ushort crc1; // velikost+short, ze zabaleneho
        ushort crc2; // ADLER32+1
        gamma=(uint)((int)(crc1+chunks_compress[i]));
        do {
            if(gamma>65521) gamma=gamma-65521;
        } while(gamma>65521);
        crckonew=gamma*65536+crc2+1;
        crckoorig=Checksum(CHECKSUM_ADLER32,FTell(),chunks_compress[i]);
        if(crckoorig!=crckonew) {
            Printf("Problem CRC - Data %i: ",i);
            Printf("Counted: %X, ",crckonew);
            Printf("Original: %X \n",crckoorig);
        }
        ubyte data_chunk[chunks_compress[i]];
    } record;
}
} record;

} DATA;


struct HEAD_Chunks {

uint64 sign2;
ushort com_type2;
byte lzo_block_ver2;

ushort compress_size_block_max2;
ushort uncompress_size_block_max2;
ushort lzo_block_count2;
chunk_count=lzo_block_count2;

local uint chunks_compress[lzo_block_count2];
local uint chunks_deccompress[lzo_block_count2];

for (y=0;y<lzo_block_count2;y++) 
{
   struct UNKcomp { 

    ushort decompresschunksize;
    ushort compresschunksize;
    chunks_compress[y]=compresschunksize;
    chunks_deccompress[y]=decompresschunksize;

  } data;  
}

struct CRCdataBlock {
for(i=0;i<chunk_count;i++) {
    struct blokdata {
        ushort crc1; // velikost+short, ze zabaleneho
        ushort crc2; // ADLER32+1
        gamma=(uint)((int)(crc1+chunks_compress[i]));
        do {
            if(gamma>65521) gamma=gamma-65521;
        } while(gamma>65521);
        crckonew=gamma*65536+crc2+1;
        crckoorig=Checksum(CHECKSUM_ADLER32,FTell(),chunks_compress[i]);
        if(crckoorig!=crckonew) {
            Printf("Problem CRC - Data %i: ",i);
            Printf("Counted: %X, ",crckonew);
            Printf("Original: %X \n",crckoorig);
        }
        ubyte data_chunk[chunks_compress[i]];
    } record;
}
} record;

} DATA;


```
## Post #9
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-13T20:16:38+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

also 1 more think about compression: Im not 100% sure coz i dont have PC version yet but it looks like this is coorect...

```
2 = lzo2a
5 = lzo1c
```
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-03-13T20:19:15+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

Great work there!
## Post #11
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-13T20:20:35+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

> Reply from Mr.Mouse
>
> Great work there!

Thx this is very complicated format for me  but it gave me a lot of new ideas
## Post #12
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-03-14T18:00:25+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

Sorry for the delay.  I guess I didn't explain the multi-chunk format well enough, but it looks like you figured it out on your own.  Should I continue?

Have you attempted any re-packing yet?  Would be interested in reading how it goes.

--MDA
## Post #13
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-14T21:02:39+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

Please continue with it.. I'll gonna work on repacker tommorow... I'll share my work once it is completed  if you want you can use my template as reference  it is completed include the Adler calculations...
## Post #14
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-15T14:40:42+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

I just wrote unpacker for scimitar files, however for repack purposes i need more information about this format, things like Lost and found and etc....
## Post #15
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-15T16:35:00+00:00
- Post Title: AC Rouge-Liberation HD (forge) Tools [PC]

OK i finnish the repacker for scimitar files, not handling compressed chunks yet... My next work would be to make decompressor for compressed files and the repacker for them, this will take some time since they are chunked...
## Post #16
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-15T19:39:37+00:00
- Post Title: Re: AC Rouge (forge)

I have extracted the texts container from forge files and this files are encoded somehow  Ill work on this files once i have a working chunk repacker...
## Post #17
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-20T08:45:18+00:00
- Post Title: Re: AC Rouge (forge)

MDA can you please help with extended Forge Files ? For example DataPC_extra.forge ?

BTW today i will realease a tool for non extended files, it can do repack also without the compression 

Thx
## Post #18
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-20T14:32:46+00:00
- Post Title: Re: AC Rouge (forge)

I just released my repacker on the first post :)Enjoy
## Post #19
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-03-20T15:28:34+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from michalss
>
> I just released my repacker on the first post :)Enjoy

awesome man, this is a big achievement, your tool seems to extract the files correctly, but there is only one problem, when I extract all files with "Decompress Files" selected, it gives an error and stops, please fix this    This is the error :-



Though it does extracts some 1-7 of the files with "Decompress" option selected but both cSize and uSize are the same, Please fix it.
## Post #20
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-20T15:41:12+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from ShivShubh
>
> michalss wrote:I just released my repacker on the first post :)Enjoy

awesome man, this is a big achievement, your tool seems to extract the files correctly, but there is only one problem, when I extract all files with "Decompress Files" selected, it gives an error and stops, please fix this    This is the error :-



Though it does extracts some 1-7 of the files with "Decompress" option selected but both cSize and uSize are the same, Please fix it.

What forge file does it ?? how much memory do you have on that PC? This is not error from application it self, it went out of memory for some reason. I cannot test this on machine under 8GB of ram.. I have try biggest files in game and it was ok also repack OK...
## Post #21
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-03-20T16:15:18+00:00
- Post Title: Re: AC Rouge (forge)

Hmmm strange cause I have tried it on 16 GB RAM and I have tried on 4 forge files, do you get a bigger uSize compared to cSize ? Cause both are shown same in the unpacker. This is another error shown :-



Extraction works good but it doesn't works with decompression option.
## Post #22
- Username: shadowlonely1989
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-20T16:51:55+00:00
- Post Title: Re: AC Rouge (forge)

again what forge files? Also it is only for files from PC. Decompression works only on PC files yet. X360 is not implemented, coz it uses different compression methods!! uSize and cSize will be always the same coz all files alwasys compressed exacept really small once..
## Post #23
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-03-20T17:08:46+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from michalss
>
> again what forge files? Also it is only for files from PC. Decompression works only on PC files yet. X360 is not implemented, coz it uses different compression methods!! uSize and cSize will be always the same coz all files alwasys compressed exacept really small once..

OK, I am sorry, I was trying on AC Unity PC Files, decompression works perfectly on Rogue, and your tool is able to extract files from AC Unity, just the decompression isn't working, can you please fix it because I think it will be easy for you to do, I  really need it, I can give you a file sample if you want.
## Post #24
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-20T17:45:04+00:00
- Post Title: Re: AC Rouge (forge)

Im sorry im working only on Rouge files, after i finnish it i might have a look on Unity files, but not just yet
## Post #25
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-03-21T04:02:00+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from michalss
>
> Im sorry im working only on Rouge files, after i finnish it i might have a look on Unity files, but not just yet

Hmmm, really appreciate the work bro, hope you add just the files decompression support for AC Unity.
## Post #26
- Username: shadowlonely1989
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-21T07:21:29+00:00
- Post Title: Re: AC Rouge (forge)

text repacker is completed but not ready for public yet!! Thx to my friend Kramla
## Post #27
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-03-21T08:52:38+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from michalss
>
> text repacker is completed but not ready for public yet!! Thx to my friend Kramla

That's even better, hope you fix the problem with the extended files and add support for decompression with Unity files very soon.
## Post #28
- Username: StrunPS
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 20, 2014 7:54 pm
- Post datetime: 2015-03-21T14:41:46+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from michalss
>
> text repacker is completed but not ready for public yet!! Thx to my friend Kramla
WOW!!!you could throw the decrypted text files Russian version of the game?
## Post #29
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-03-21T14:44:22+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from michalss
>
> MDA can you please help with extended Forge Files ? For example DataPC_extra.forge ?

BTW today i will realease a tool for non extended files, it can do repack also without the compression 

Thx

Unsure of what you are asking for.  That forge file should be no different from any of the other forge files.

--MDA
## Post #30
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-21T14:52:12+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from MichaelDarkAngel
>
> michalss wrote:MDA can you please help with extended Forge Files ? For example DataPC_extra.forge ?

BTW today i will realease a tool for non extended files, it can do repack also without the compression 

Thx

Unsure of what you are asking for.  That forge file should be no different from any of the other forge files.

--MDA

There is 2 types of scimitar archives, 1 normal forge which included <5000 files and extended files where u can get ever more the 10K files inside the forge. So im asking for help with this extended files withn more then 10k files... For example file call DataPC_extra.forge
## Post #31
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-03-21T16:31:24+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from michalss
>
> There is 2 types of scimitar archives, 1 normal forge which included <5000 files and extended files where u can get ever more the 10K files inside the forge. So im asking for help with this extended files withn more then 10k files... For example file call DataPC_extra.forge

I don't have AC:Rogue yet, so I can only go on past history.  If file count is greater than max file count, use max file count.  If you check the index table, you will not find any more entries than max file count.

For reference:

ACIV: Black Flag - DataPC_extra.forge -- file count is 7205, there are only 5000 file entries in the index table
AC: Revelations - DataPC_ACFE_Constantinople.forge -- file count is 5599, there are only 5000 file entries in the index table

For both of those forge files, the max file count is 5000.

--MDA
## Post #32
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-21T17:24:11+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from MichaelDarkAngel
>
> michalss wrote:There is 2 types of scimitar archives, 1 normal forge which included <5000 files and extended files where u can get ever more the 10K files inside the forge. So im asking for help with this extended files withn more then 10k files... For example file call DataPC_extra.forge

I don't have AC:Rogue yet, so I can only go on past history.  If file count is greater than max file count, use max file count.  If you check the index table, you will not find any more entries than max file count.

For reference:

ACIV: Black Flag - DataPC_extra.forge -- file count is 7205, there are only 5000 file entries in the index table
AC: Revelations - DataPC_ACFE_Constantinople.forge -- file count is 5599, there are only 5000 file entries in the index table

For both of those forge files, the max file count is 5000.

--MDA

Im afraid you wrong here mate. There is another table offset i have done a small research and i think i know how to but it is very tricky
## Post #33
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-03-21T19:36:49+00:00
- Post Title: Re: AC Rouge (forge)

Would love to be able to read the rest of them.  I'll start digging through it again.  Based on the index table and filename table I always just assumed the file count was misleading.  If you have theories on how to get to the other files, I would certainly like to hear them.

--MDA
## Post #34
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-23T06:44:30+00:00
- Post Title: Re: AC Rouge (forge)

ill share info once i know more mate  There is certain pattern for the files just need to figure it out, how exactly this index offsets work.
## Post #35
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-03-23T15:01:16+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from michalss
>
> ill share info once i know more mate  There is certain pattern for the files just need to figure it out, how exactly this index offsets work.

Turfster's Assassin's Creed tool is able to extract more than 5000 files from any forge files until AC Revelations only, so keeping that in mind, I think it will be possible for you to add support for extended forge files.
## Post #36
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-03-25T22:14:34+00:00
- Post Title: Re: AC Rouge (forge)

I just found something interesting, DataPC_ACU_Versailles_assets.forge file of AC Unity has 17,522 files inside and your tool is perfectly able to extract all of them, here no error of extended forge file comes up. Everything seems to be working fine. So it seems to be the case with AC III, IV & Rogue, in those 3 games, the tool can't extract forge files with over 5000 files. So maybe you can check what's up with AC Unity.
## Post #37
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-03-26T04:12:56+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from ShivShubh
>
> I just found something interesting, DataPC_ACU_Versailles_assets.forge file of AC Unity has 17,522 files inside and your tool is perfectly able to extract all of them, here no error of extended forge file comes up. Everything seems to be working fine. So it seems to be the case with AC III, IV & Rogue, in those 3 games, the tool can't extract forge files with over 5000 files. So maybe you can check what's up with AC Unity.

The issue stems from file count being greater than max file count.  As an example the one file I mentioned earlier, AC:Revelations DataPC_ACFE_Constantinople.forge, has a file count of 5599, but max file count is only 5000.  In the index table, there are only 5000 entries.  In games prior to AC3, the files were prefaced with a "FILEDATA" string, which means in theory you could pick out the files without the index table.  Since then it has been more reliable to use the index table.

Of course, you also run into situations like the following, still referencing the AC:Revelations file, the file count is 5599, however if you count the "FILEDATA" tags, there are 5792.  Another situation you'll run into, the multi-player forge files don't always use the same format as the game, AC3's multi-player forge files use a format similar to AC2.

This format is not easy.

--MDA
## Post #38
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-03-26T15:35:58+00:00
- Post Title: Re: AC Rouge (forge)

I edited my [first post](http://forum.xentax.com/viewtopic.php?p=104187#p104187) regarding the index tables.  It now includes how to get to the next index table when multiple tables are present.  I hope it makes sense.  Even though I don't have an AC:Rogue file to verify this against, what I posted should work.  AC:Rogue appears to use the same forge file format as ACIV:Black Flag.

Thanks michalss for making take a second look at this.  Once I do get AC:Rogue and get support for it built into ARchive_neXt I'll fix this issue as well.  If you are going to support earlier games with your tool, here's a list of the games that have split index tables:
AC: Brotherhood
AC: Revelations
Assassin's Creed III (multi-player only, which uses a different format from the single-player forge files)
ACIV: Black Flag (single-player and multi-player forge files, which also use different formats)
Prince of Persia 2008

And apparently AC:Rogue

--MDA
## Post #39
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-03-26T19:02:44+00:00
- Post Title: Re: AC Rouge (forge)

Many thanks for your work over this one mate, really appreciate it, expecting michaelss to fix this one ASAP. And I really hope that he do add decompression support for AC Unity files, this game has no such "extended" forge files problem.
## Post #40
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-03-26T19:43:43+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from MichaelDarkAngel
>
> I edited my first post regarding the index tables.  It now includes how to get to the next index table when multiple tables are present.  I hope it makes sense.  Even though I don't have an AC:Rogue file to verify this against, what I posted should work.  AC:Rogue appears to use the same forge file format as ACIV:Black Flag.

Thanks michalss for making take a second look at this.  Once I do get AC:Rogue and get support for it built into ARchive_neXt I'll fix this issue as well.  If you are going to support earlier games with your tool, here's a list of the games that have split index tables:
AC: Brotherhood
AC: Revelations
Assassin's Creed III (multi-player only, which uses a different format from the single-player forge files)
ACIV: Black Flag (single-player and multi-player forge files, which also use different formats)
Prince of Persia 2008

And apparently AC:Rogue

--MDA

thx a lot mate ill verify this once i have some time and make repacker for this as well or at least ill try, unpack is 1 thing, but repack is very complicated.. I was very busy last week...
## Post #41
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-04-05T17:48:16+00:00
- Post Title: Re: AC Rouge (forge)

Not sure where you're at with this project, or if this is going to help at all.  But, I've started detailing the formats of the AC games on my [Wiki page](http://wiki.tbotr.net).  Currently I have the forge and "DATAFILE" formats for all the AC games.  I've started on the formats for a few of the files inside the "DATAFILEs", but I'm not finished with those yet.

--MDA
## Post #42
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-04-05T22:53:31+00:00
- Post Title: Re: AC Rouge (forge)

> Reply from MichaelDarkAngel
>
> Not sure where you're at with this project, or if this is going to help at all.  But, I've started detailing the formats of the AC games on my Wiki page.  Currently I have the forge and "DATAFILE" formats for all the AC games.  I've started on the formats for a few of the files inside the "DATAFILEs", but I'm not finished with those yet.

--MDA

Hi mate,

I did not move anywhere yet, i have been very busy last weeks  but wiki pages its a great idea
## Post #43
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2015-04-06T14:06:13+00:00
- Post Title: Re: AC Rouge (forge)

And you have thrown this topic? Text retrieval Auger?  [http://zenhax.com/viewtopic.php?f=9&t=699](http://zenhax.com/viewtopic.php?f=9&t=699)
## Post #44
- Username: vladik4kides
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 18, 2015 12:36 am
- Post datetime: 2015-06-21T11:25:36+00:00
- Post Title: Re: AC Rouge (forge)

Can you make unpacker for DataX360.forge files? Pleease.
## Post #45
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-06-21T11:37:23+00:00
- Post Title: Re: AC Rouge (forge)

im still planning to support all ac games, not time yet, once i finnish mine last project ill get back to it.. + MDA is great person and help me to understand the structure
## Post #46
- Username: vladik4kides
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 18, 2015 12:36 am
- Post datetime: 2015-06-21T12:35:28+00:00
- Post Title: Re: AC Rouge (forge) Tools

> Reply from michalss
>
> im still planning to support all ac games, not time yet, once im finnish mine last project ill get back to it.. + MDA is great person and help me to understand the structure

OK,Thanks.
## Post #47
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-07-23T17:37:24+00:00
- Post Title: Re: AC Rouge (forge) Tools

Repacker can also handle Liberation on PC.. proof ...
## Post #48
- Username: TheRanger
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-09-07T15:38:23+00:00
- Post Title: Re: AC Rouge (forge) Tools

updatete to version 1.5..

* added more compression methods
* should work for ACU as well (never tested!!)
## Post #49
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-09-07T21:35:52+00:00
- Post Title: Re: AC Rouge (forge) Tools

> Reply from michalss
>
> updatete to version 1.5..

* added more compression methods
* should work for ACU as well (never tested!!)

Thanks sir for your time but its still not working with AC U, here's a sample forge file from AC Unity :-

```
http://www.solidfiles.com/d/95f1820ce0/
```
## Post #50
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-09-08T11:25:25+00:00
- Post Title: Re: AC Rouge (forge) Tools

> Reply from TheRanger
>
> michalss wrote:updatete to version 1.5..

* added more compression methods
* should work for ACU as well (never tested!!)

Thanks sir for your time but its still not working with AC U, here's a sample forge file from AC Unity :-
Code: Select allhttp://www.solidfiles.com/d/95f1820ce0/

Just check that, sorry mate it is completele different format, My tool never gonna work with it!
## Post #51
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-09-08T15:00:14+00:00
- Post Title: Re: AC Rouge (forge) Tools

> Reply from michalss
>
> Just check that, sorry mate it is completele different format, My tool never gonna work with it!

OK, still thank you sir for giving your valuable time on this.
## Post #52
- Username: StrunPS
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Nov 20, 2014 7:54 pm
- Post datetime: 2015-10-04T11:03:30+00:00
- Post Title: Re: AC Rouge (forge) Tools

> Reply from michalss
>
> Repacker can also handle Liberation on PC.. proof ...
cool, but how to open a text file after repacking , I have not read the characters .
## Post #53
- Username: muserigtc
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Jul 16, 2016 9:44 pm
- Post datetime: 2016-07-31T11:22:41+00:00
- Post Title: Re: AC Rouge (forge) Tools

Can you Reuploade file ACR Tools again... Please... Dropbox and Solidfile link is Dead... Dropbox : Error 429 and Solidfiles : 404 Not Found...
## Post #54
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-10-26T08:23:12+00:00
- Post Title: Re: AC Rouge (forge) Tools

edited download link...
## Post #55
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-11-14T12:36:24+00:00
- Post Title: Re: AC Rouge (forge) Tools

Did the Repack function stop working as of the last update? I opened up all the DataPC files from Rogue, but not matter what I do the Reimport option is disabled for every file.
## Post #56
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-11-16T17:02:38+00:00
- Post Title: Re: AC Rouge (forge) Tools

Alright, I figured it out. You need uncheck Decompress Files, do Unpack All, then do Repack All, and finally replace the original .forge with the .forge.new that is created.

Using this method you can now edit forge files! Unfortunately the only way to do so right now is through hex editing. [Here's an example of a model replacement I made by swapping two model files and editing the headers.](http://steamcommunity.com/sharedfiles/filedetails/?id=800819531)
## Post #57
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-11-16T17:42:04+00:00
- Post Title: Re: AC Rouge (forge) Tools

> Reply from SergeantJoe
>
> Alright, I figured it out. You need uncheck Decompress Files, do Unpack All, then do Repack All, and finally replace the original .forge with the .forge.new that is created.

Using this method you can now edit forge files! Unfortunately the only way to do so right now is through hex editing. Here's an example of a model replacement I made by swapping two model files and editing the headers.

purpose of the repacker is to repack original archive, it has nothing to do with models or antyhing else that is totally different story.
## Post #58
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-11-16T18:00:48+00:00
- Post Title: Re: AC Rouge (forge) Tools

I know! And I have to say thank you, the repacker works excellently. 

To be able to correctly edit models and textures we'll have to find someone who can make proper tools for it. That's why I'm hoping if I make a mod with just really simple replacements it'll inspire the knowledgeable people to make more advanced tools.
## Post #59
- Username: SergeantJoe
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-11-16T18:23:37+00:00
- Post Title: Re: AC Rouge (forge) Tools

> Reply from SergeantJoe
>
> I know! And I have to say thank you, the repacker works excellently. 

To be able to correctly edit models and textures we'll have to find someone who can make proper tools for it. That's why I'm hoping if I make a mod with just really simple replacements it'll inspire the knowledgeable people to make more advanced tools.

Format is very complicated, to reimport files into archive with correct compression and crc adler check is very hard job. Calculation of adler is also very hard, it took months to figure it out how it works and how it is calculated, means reimport it is not working for exact that reason.
## Post #60
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-11-16T19:07:15+00:00
- Post Title: Re: AC Rouge (forge) Tools

Understandable. I guess I'll have to keep editing the compressed files for now.
## Post #61
- Username: fahad00
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 19, 2016 3:36 am
- Post datetime: 2016-11-17T06:49:08+00:00
- Post Title: Re: AC Rouge-Liberation HD (forge) Tools [PC]

can anyone please tell me how to repack assassin creed 3 and black flag please help me
## Post #62
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-11-17T12:21:20+00:00
- Post Title: Re: AC Rouge-Liberation HD (forge) Tools [PC]

To repack Black Flag:

> Reply from SergeantJoe
>
> uncheck Decompress Files, do Unpack All, then do Repack All, and finally replace the original .forge with the .forge.new that is created.
## Post #63
- Username: abrakaddabra
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 23, 2016 9:18 pm
- Post datetime: 2016-12-23T13:26:39+00:00
- Post Title: Re: AC Rouge-Liberation HD (forge) Tools [PC]

> Reply from SergeantJoe
>
> Alright, I figured it out. You need uncheck Decompress Files, do Unpack All, then do Repack All, and finally replace the original .forge with the .forge.new that is created.

Using this method you can now edit forge files! Unfortunately the only way to do so right now is through hex editing. Here's an example of a model replacement I made by swapping two model files and editing the headers.

Hey guys, I'd be interest in a small explanation/tutorial of how to swap models. Is anybody able to describe the procedure to do it correctly, as all the tests I've done so far ended up with either the game crashing after loading the save or being FUBAR?
## Post #64
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2016-12-25T03:46:00+00:00
- Post Title: Re: AC Rouge-Liberation HD (forge) Tools [PC]

Okay, so. Unpack the DataPC_extra_chr.forge (WITHOUT decompressing)

Then find the file you want to replace. You can only replace files that have this exact type of header:




A good trick is to just look for files that end in "_LOD". For example, this is CHR_G_JackdawPirates_Sailors_A_LOD0, one of the allied sailors.

Then look for the file you want to use instead. The new file can have the same header structure as the original, or it can have some extra stuff like this:




Now, from the new file, take everything past the second occurence of "3auWTMu" (hex 33AAFB5799FA), and paste it over everything past the second occurence of 3auWTMu in the original file.




Then repack the forge file and use Archive_next to test if it worked:




If it works there, it has a good chance of working ingame, but not always.



I don't know what do about the materials. Sometimes they work, sometimes they don't. 


It would be revolutionary if someone who knew file formats took a look at this, hopefully it would lead to a real method for editing the files instead of this ridiculousness.
## Post #65
- Username: sniperspy10
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 01, 2018 7:09 am
- Post datetime: 2018-03-31T23:11:21+00:00
- Post Title: Re: AC Rouge-Liberation HD (forge) Tools [PC]

please can you post the download link, they seem not to be working
## Post #66
- Username: Perkele6666
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 22, 2016 4:35 am
- Post datetime: 2018-04-10T11:34:39+00:00
- Post Title: Re: AC Rouge-Liberation HD (forge) Tools [PC]

> Reply from sniperspy10
>
> please can you post the download link, they seem not to be working
zenhax.com/download/file.php?id=2189
