## Post #1
- Username: Zentax
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 30, 2010 4:40 pm
- Post datetime: 2011-01-28T14:18:50+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

Im just curious about this game to extract the game script,
so in the folder "pack" i think there is all we need.

There are 3 file: "eventpacks" "filesystem" and "levels" 

but everyone have a .pfs, .pk, .pkh (i dont know why)

and the bigger one is alway the .pk file

so someone know if is possible to make a .pk pack\unpaker?
## Post #2
- Username: surakichi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 29, 2011 7:10 am
- Post datetime: 2011-01-28T23:49:26+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

pks

0h~:header (size:16bytes)
    8bytes always 0x00
    4bytes number of directories
    4bytes number of files

10h~:Attribute of directory (size:24bytes * num of directories)
    4bytes directory No.
    4bytes parent directory No.
    4bytes unknown
    4bytes unknown
    4bytes cumulative files?
    4bytes number of files in directory?

~:offset directory or file name (size:4byte * number of directories + files)

~:directory & file name (variable-length. delimiteｒ '00')

pkh
0h~3h: (size:4bytes number of files)

4h~:file header? (size:16bytes * number of files)
    4bytes unknown
    4bytes data start address in .pk
    4bytes unknown
    4bytes size of data?

pk
compressed though the file can be separated. 
decompress method is not understood.
## Post #3
- Username: Zentax
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 30, 2010 4:40 pm
- Post datetime: 2011-01-29T16:27:43+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

thanks! so .pk it's to hard to decompress?
## Post #4
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2011-01-29T16:37:22+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

The compression is just a normal 0x11 type lzss one, but the problem I'm having is getting the decompressed file size. (lzss normally seem to store it in byte 2-4, but that's not the case here)

Edit: Now I see, the size is indeed stored in bytes 2-4 (little endian), but each file in the pk is compressed individually, not as a single archive.

Example: game_start_db.pk
first file start: 0
first file size (decompressed): 0x9A92 (byte 2-4)
second file start*: 0x18A0
second file size: 0x2A38
third file start*: 0x2D20
...

*When you fully decompress a file from the pk with the given size, that's the next byte your file pointer will point to, which is incidentally a new file.
## Post #5
- Username: raistlin77it
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 07, 2010 5:07 am
- Post datetime: 2011-01-30T13:40:08+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

i'm a little newbe with quickbms , so maybe u can help.

first byte = header =11

first long = decompressed size = 0x9A92

how can i obtain the compressed size to pass to the clog function?

here my broken script  


////////////
endian little

get head BYTE        

get decompressed LONG    

ComType lz77wii_raw11

Clog "a" 0 ZSIZE decompressed
## Post #6
- Username: DRayX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 11, 2010 11:39 am
- Post datetime: 2011-01-30T22:30:37+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

Ok I have been working on this independently and the only piece I was missing was was the compression algorithm, so thanks Forte.  Do you know of a good library that implements LZSS compression/decompression?  I'm not sure that is actually correct since QuickBMS is failing to decrypt the extracted files using lzss 0x11 (lz77wii_raw11).  Here are some quick file specifications:


PFS:

Header
0x0 0x8 0x0
0x8 0x4 directory count
0xb 0x4 file count

Directory Table (1 entry per directory)
0x0  0x4 directory number
0x4  0x4 parent directory
0x8  0x4 start child directory
0xb  0x4 child directory count
0x10 0x4 start child file
0x14 0x4 child file count

String Offset Table (1 entry per directory or file)
0x0 0x4 offset in string table

String Table (1 entry per directory or file)
0x0 0x? name (null terminated)


PKH:

Header
0x0 0x4 file count

File Table (1 entry per file)
0x0 0x4 unknown (I think this is a CRC hash of the decoded file)
0x4 0x4 offset in pk (aligned to 0x20 bytes)
0x8 0x4 decompressed size
0xb 0x4 compressed length
## Post #7
- Username: Forte
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Aug 07, 2007 4:51 am
- Post datetime: 2011-01-30T22:39:28+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

I only tried [dsdecmp](http://code.google.com/p/dsdecmp/) and it worked like a charm. There's no compressor, though. (do tell if you find a decent one)
## Post #8
- Username: DRayX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 11, 2010 11:39 am
- Post datetime: 2011-01-30T22:47:50+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

Cool DSDecomp did it just fine and the output file was the expected length (and it was LZSS 0x11 as you expected).  I don't know why QuickBMS failed to do it, if it hadn't I would have had this all figured out 2 days ago (spent forever trying to figure out which compression it was using since QuickBMS was failing).  Thanks again for all your help Forte.  My unpacking tool will be done as soon as I find or create a good LZSS library (I will probably just write one since I can't find a good one) and finish my CMAKE script.  The packing tool will take another day or so.
## Post #9
- Username: raistlin77it
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 07, 2010 5:07 am
- Post datetime: 2011-01-31T02:12:05+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

yes, DSDecomp  work, and puyotools also, but sadly they only decompress the first archive of the joined group
## Post #10
- Username: DRayX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 11, 2010 11:39 am
- Post datetime: 2011-01-31T05:13:47+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

Ya, I have everything working now on the decompression side, but there is still that one number in the PKH file that I'm not using, and I haven't written the compression algorithm yet.  If you want to know how to pull all the files apart, read the above post.  Once I have everything working, and no unused mystery numbers, I will post my source.  The unknown number is not a hash, I somehow missed that they are monotonically increasing (by file number, not by offset) the first time.  I also can't figure out why the files are out of order in the pk file, the order seems almost random.  Any ideas would be greatly appreciated.

Edit:
Ok mystery one solved.  The files are not in the pk file in a random order, to the contrary the order in the PK file matches the sane file order listed in the PFS file.  The order in the PKH file is now what makes very little sense.  It would appear they are sorted by whatever that first number is, which I am back to thinking is some sort of hash due to the distribution, but I still don't know what the hash is of, or what type of hash it is (still guessing CRC-32).

Edit2:
Ok a little more figured out since the last edit.  It turns out that the main.dol doesn't look at the PFS files at all (which makes sense since finding a given file by path using the PFS files would be a major pain).  Thus, the logical conclusion is that the unknown number is used to look up the file (and thus sorting by them would make sense as it would allow you to binary search for the file).  However, it appears that these "IDs" aren't stored anywhere in the dol or otherwise, but the file paths are.  My conclusion is that the unknown number is actually a hash of the file name or path, and they are operating under the assumption that there will be no collisions (seems like a bad assumption).  Unfortunately, I have been unable to figure out what type of hash, and of what format of the file path these hashes are of.  My guess on format is CRC-32-IEEE (cksum) since it is the most common 32 bit hash format and is apparently included in the Wii SDK, and I assumed that the strings being hashed would match the ones in the dol (found with 'strings'), but no luck.  Any insight, ideas, or assistance would be awesome, otherwise my next step is to start reading through PPC ASM (rally don't want to do that).
## Post #11
- Username: Zentax
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 30, 2010 4:40 pm
- Post datetime: 2011-01-31T12:43:49+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

great great! so cool guys! this really help a lot!   
*__*
## Post #12
- Username: surakichi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 29, 2011 7:10 am
- Post datetime: 2011-01-31T21:22:29+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

>PKH:
>File Table (1 entry per file)
>0x0 0x4 unknown (I think this is a CRC hash of the decoded file)

The file with the same value in another PKH file exists.
Those files are the same at the binary level in the PK file.

Most English of me is a machine translation. (I'm japanese)

>PFS:
>Directory Table (1 entry per directory)
>0x10 0x4 start child file
The child file number used here is a number of the result of sorting the ascending order in the address in PK as for the file table in PKH file.
## Post #13
- Username: DRayX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 11, 2010 11:39 am
- Post datetime: 2011-02-01T02:05:45+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

> Reply from surakichi
>
> >PKH:
>File Table (1 entry per file)
>0x0 0x4 unknown (I think this is a CRC hash of the decoded file)

The file with the same value in another PKH file exists.
Those files are the same at the binary level in the PK file.

Can you give an example of two such files?


On another note, the unpacker is now done and working 100%.  I want to clean up the code a little bit, and maybe try and speed it up (large pk files take forever), and then I will post it.  The one unknown number is still unused, but like I said, I am fairly certain (99.9%) that it is only used for finding the files efficiently.  On the packing side, I am still too lazy to write the compression algorithm, and I wont be able to make valid pkh files until the mystery number gets figured out, but replacing existing files in the archive with uncompressed modified versions of the same file should be possible, which would be good enough for a translation.  I still really want to figure out the unknown number, and writing a LZ77 compression algorithm would be an interesting exercise.
## Post #14
- Username: surakichi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 29, 2011 7:10 am
- Post datetime: 2011-02-01T04:49:29+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

same unknown value in file table
for example

unknown | offset in PK | decompSize | compSize | PKH File | unpacked filename(not certain)
----------------------------------------------------------------------------------------------------------
03665F27 | 00026140 | 00000671 | 00000285 | preload\change_dg_cache.pkh (ADDRESS:0x0084) | \data\efp\ef_sp009a.efp
03665F27 | 0001F7A0 | 00000671 | 00000285 | preload\change_dg.pkh (ADDRESS:0x0064) | \data\efp\ef_ms101e.efp
03665F27 | 00062CA0 | 00000671 | 00000285 | preload\game_start_dg.pkh (ADDRESS:0x0154) | \data\d2anime\ui_steal.d2b
03665F27 | 249E2640 | 00000671 | 00000285 | pack\filesystem.pkh (ADDRESS:0x21A4) | \event2\dungeon\dg055\ev5585.event

On another note,
Some data that exists in the file table in PKH, the compressed size is 0. 
If decompressed size is not 0, decompressed size data exists in PK.

If compressed size and decompressed size is 0, I do not understand how to process those files.
(As for all those files, the offset in PK overlaps with other files. )
for example
unknown | offset in PK | decompSize | compSize | PKH File | unpacked filename(not certain)
----------------------------------------------------------------------------------------------------------
1D823470 | 000282E0 | 0000049C | 00000223 | preload\boot.pkh (ADDRESS:0x0194) | \boot\hate_param.csv
C11B19A2 | 000282E0 | 00000000 | 00000000 | preload\boot.pkh (ADDRESS:0x0984) | \boot\hair_back_control.csv

332AE0BD | 001591E0 | 0002DD0C | 00007DE8 | pack\filesystem.pkh (ADDRESS:0x01F594) | \event2\custom_effect_list.csv
C11B19A2 | 001591E0 | 00000000 | 00000000 | pack\filesystem.pkh (ADDRESS:0x077E54) | \boot\weapon_param_text_jp.u16

Moreover, it is a file where most of the decompressed file has the header named ”chnkdata wii”.
## Post #15
- Username: DRayX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jan 11, 2010 11:39 am
- Post datetime: 2011-02-01T05:12:24+00:00
- Post Title: [Wii] The Last Story - .pfs .pk .pkh

Ya the ones with a decompressed size of 0 are not LZ77 compressed in the pk file.  When both are 0, it means that it is actually a zero length file (there are only a few).
## Post #16
- Username: Zentax
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 30, 2010 4:40 pm
- Post datetime: 2011-02-02T16:08:00+00:00
- Post Title: Re: [Wii] The Last Story - .pfs .pk .pkh

so what we have to use to extract the .pk files?
DSDecomp dont extract nothing
## Post #17
- Username: surakichi
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 29, 2011 7:10 am
- Post datetime: 2011-02-03T05:47:05+00:00
- Post Title: Re: [Wii] The Last Story - .pfs .pk .pkh

> Reply from Zentax
>
> so what we have to use to extract the .pk files?
DSDecomp dont extract nothing

The pk file is separated by using the data of the file table that exists in the pkh file.
About the separated file...
header[0x11]:wii lz77 0x11 compressed. DSDecmp can decompress these files.

After decompression or other files.
header[0x55AA382D]:WiiArcData(U8 Archive)
header[0x63686E6B...]:WiiChunkData
header[0xFEFF](footer[0x000D000A]):UTF16-BigEndian text
footer[0x0D0A]:text

other header: unknown.
## Post #18
- Username: quantico
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Sep 19, 2010 6:19 pm
- Post datetime: 2011-02-06T19:31:48+00:00
- Post Title: Re: [Wii] The Last Story - .pfs .pk .pkh

DRayX will you still release your tools ? I am just interested in taking a look at the unpacked files .
## Post #19
- Username: Zentax
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 30, 2010 4:40 pm
- Post datetime: 2011-02-07T17:37:09+00:00
- Post Title: Re: [Wii] The Last Story - .pfs .pk .pkh

> Reply from quantico
>
> DRayX will you still release your tools ? I am just interested in taking a look at the unpacked files .

that's right, just to see how unpack the strange .pk files.
maybe we can see 3d model too ^^
## Post #20
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-04-03T17:31:22+00:00
- Post Title: Re: [Wii] The Last Story - .pfs .pk .pkh

Any progress about these file formats?
## Post #21
- Username: StoneOcean
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 07, 2011 8:45 am
- Post datetime: 2011-04-08T13:55:16+00:00
- Post Title: Re: [Wii] The Last Story - .pfs .pk .pkh

I am also interested in these file types, has there been any more progress on this or plans to release the tools.  It would be greatly appreciated.
## Post #22
- Username: alanmugiwara
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Mar 07, 2018 10:22 am
- Post datetime: 2021-02-22T13:30:34+00:00
- Post Title: Re: [Wii] The Last Story - .pfs .pk .pkh

Guys. I use LSPK-Extracter by RGBA_CRT ([https://github.com/RGBA-CRT/LSPK-Extracter](https://github.com/RGBA-CRT/LSPK-Extracter)), and can be able extract .pk files from TLS. I hope help you. But I do't know about recompress it. If anyone knows, please talk here.
