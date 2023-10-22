## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-02T07:14:04+00:00
- Post Title: Evil 《神雕侠侣》pfs

Hello guys, well a old script made by aluigi, he help me with that, but for some reason it give me this error when unpack files, I got just few files and got this error.



so well maybe somebody can take a look into files? many thanks guys.

BMS Script

> # ZIP files example 0.4.2c
>
> # more info: http://www.pkware.com/documents/casestudies/APPNOTE.TXT
>
> #   note that with some archives like those created by Stuff-it on MacOSX is
>
> #   not possible to use this script because they are wrongly built, practically
>
> #   they set the comp_size and uncomp_size fields of the "Local file header" at
>
> #   0 and they set them only in the relative "Central directory structure" which
>
> #   means that it's necesary to read this one first for extracting the files
>
> #   contained in the local header... senseless and stupid
>
> # script for QuickBMS http://quickbms.aluigi.org
>
> 
>
> get EXE_SIGN long
>
> goto 0
>
> if EXE_SIGN == 0x00905a4d
>
> get EXT extension
>
> if EXT == "exe" || EXT == "dll"
>
>     findloc OFFSET string "PK\x03\x04"
>
>     goto OFFSET
>
> endif
>
> endif
>
> savepos OFFSET
>
> 
>
> set ZIP_PASSWORD string ""  # put the password here (only ZipCrypto supported at the moment)
>
> 
>
> set ZIP_SIGN short 0x0403
>
> goto OFFSET
>
> get DUMMY short
>
> get ZIP_SIGN short
>
> goto OFFSET
>
> get zip_filesize asize
>
> for offset = 0 < zip_filesize
>
>     #idstring "PK\x03\x04"
>
>     get PK_sign short       # so it works also with modified ZIP files!
>
>     get sign short
>
>     if sign == ZIP_SIGN     # Local file header
>
>         get ver             short
>
>         get flag            short
>
>         get method          short
>
>         get modtime         short
>
>         get moddate         short
>
>         get crc             long
>
>         get comp_size       long
>
>         get uncomp_size     long
>
>         get name_len        short
>
>         get extra_len       short
>
>         getdstring name     name_len
>
>         getdstring extra    extra_len
>
>         savepos offset
>
> 
>
>         # zip64
>
>         if extra_len >= 20
>
>             getvarchr extra_id extra 0 short
>
>             if extra_id == 0x0001
>
>             if comp_size == 0xffffffff
>
>                 getvarchr uncomp_size 4 longlong
>
>                 getvarchr comp_size 12 longlong
>
>             endif
>
>             endif
>
>         endif
>
> 
>
>         # possible lame tricks used by games
>
>         if comp_size < 0
>
>         if comp_size u> zip_filesize
>
>             math comp_size ~= comp_size
>
>             math uncomp_size ~= uncomp_size
>
>         endif
>
>         endif
>
>         if name_len < 0
>
>             math name_len ~= name_len
>
>         endif
>
>         if extra_len < 0
>
>             math extra_len ~= extra_len
>
>         endif
>
> 
>
>         if flag & 1
>
>             if ZIP_PASSWORD == ""
>
>                 print "the file is encrypted, you must set ZIP_PASSWORD in the script"
>
>                 #cleanexit
>
>             endif
>
>             encryption zipcrypto ZIP_PASSWORD 1
>
>         endif
>
>         if method == 0
>
>             Log name offset uncomp_size
>
>         else
>
>             if method == 8
>
>                 ComType deflate
>
>             elif method == 1
>
>                 ComType shrink
>
>             elif method == 6
>
>                 ComType explode
>
>             elif method == 9
>
>                 ComType deflate64
>
>             elif method == 12
>
>                 ComType bzip2
>
>             elif method == 13
>
>                 ComType XMemDecompress
>
>             elif method == 14
>
>                 ComType lzmaefs
>
>             elif method == 21
>
>                 ComType XMemDecompress
>
>             elif method == 64
>
>                 ComType darksector
>
>             elif method == 98
>
>                 ComType ppmd
>
>             elif method == 99
>
>                 print "this script doesn't support AES encryption"
>
>                 cleanexit
>
>             else
>
>                 print "unsupported compression method %method%"
>
>                 cleanexit
>
>             endif
>
>             CLog name offset comp_size uncomp_size
>
>         endif
>
>         if flag & 1
>
>             encryption "" ""
>
>         endif
>
> 
>
>         math offset += comp_size
>
>         goto offset
>
> 
>
>     elif sign == 0x0806     # Archive extra data record
>
>         get extra_len       long
>
>         getdstring extra    extra_len
>
> 
>
>     elif sign == 0x0201     # Central directory structure
>
>         get ver_made        short
>
>         get ver_need        short
>
>         get flag            short
>
>         get method          short
>
>         get modtime         short
>
>         get moddate         short
>
>         get crc             long
>
>         get comp_size       long
>
>         get uncomp_size     long
>
>         get name_len        short
>
>         get extra_len       short
>
>         get comm_len        short
>
>         get disknum         short
>
>         get int_attr        short
>
>         get ext_attr        long
>
>         get rel_offset      long
>
>         getdstring name     name_len
>
>         getdstring extra    extra_len
>
>         getdstring comment  comm_len
>
> 
>
>     elif sign == 0x0505     # Digital Signature
>
>         get sign_len        long
>
>         getdstring sign     sign_len
>
> 
>
>     elif sign == 0x0606     # Zip64 end of central directory record
>
>         get dir_record      longlong
>
>         get ver_made        short
>
>         get ver_need        short
>
>         get num_disk        long
>
>         get num_disk2       long
>
>         get tot_entries     longlong
>
>         get tot_entries2    longlong
>
>         get central_size    longlong
>
>         get central_offset  longlong
>
>         print "Error: zip64 extensible data sector not implemented, contact me"
>
>         cleanexit
>
> 
>
>     elif sign == 0x0706     # Zip64 end of central directory locator
>
>         get start_central   long
>
>         get end_central     longlong
>
>         get disks           long
>
> 
>
>     elif sign == 0x0605     # End of central directory record
>
>         get disk_num        short
>
>         get disk_start      short
>
>         get central_entries short
>
>         get central_entries short
>
>         get central_size    long
>
>         get central_offset  long
>
>         get comm_len        short
>
>         getdstring comment  comm_len
>
> 
>
>     elif sign == 0x0807     # Data Descriptor
>
>         get crc             long
>
>         get comp_size       long
>
>         get uncomp_size     long
>
> 
>
>     elif sign == 0x3030     # disk spanning
>
>         # nothing?
>
> 
>
>     else
>
>         print "\nError: unknown ZIP signature %sign% at offset %offset|x%\n       if the other files have been extracted correctly it's all ok, maybe this is just the end of file"
>
>         cleanexit
>
>     endif
>
>     savepos offset
>
> next

Samples

[https://www.mediafire.com/?ed426ljesdbuh2p](https://www.mediafire.com/?ed426ljesdbuh2p)
## Post #2
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-10-02T13:09:09+00:00
- Post Title: Evil 《神雕侠侣》pfs

You could try using a binary search and replace tool to replace "PFSH", "PFSF", "PFSD" with their equivalent "PK" signatures. Then open in an archiver, check integrity, and fix whatever entries that are corrupted by the search and replace.
