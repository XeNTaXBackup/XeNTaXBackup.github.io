## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-10-13T14:01:41+00:00
- Post Title: Eligium (Magic World 2) (*.MW2)

Again ZipCrypto format. Currently can't decompress some files i dont know why and temporarily set deflate_noerror

```
#
# Based on script Legendary Champions by Aluigi
# Modified by Ekey (h4x0r)
#
# http://forum.xentax.com
#
# script for QuickBMS http://quickbms.aluigi.org

set ZIP_PASSWORD string "Mw2zd198703k%lu"
ComType deflate_noerror

goto -0x16
savepos OFFSET
get MW_sign             long	#2owm
get disk_num            short
get disk_start          short
get central_entries     short
get central_entries     short
get central_offset      long

math OFFSET -= central_offset
goto OFFSET

for i = 0 < central_entries
    get LOC_sign 		long	#looc
    get sign            short
    get ver_made        short
    get ver_need        short
    get flag            short
    get modtime         short
    get moddate         short
    get crc             long
    get comp_size       long
    get uncomp_size     long
    get name_len        short
    get extra_len       short
    get comm_len        short
    get disknum         short
    get int_attr        short
    get ext_attr        long
    get rel_offset      long
    getdstring name     name_len
    getdstring extra    extra_len
    getdstring comment  comm_len

    savepos CENTRAL_OFFSET
    goto rel_offset
        get PK_sign 		    long	#dlog
        get ver             	short
        get flag            	short
        get method          	short
        get modtime         	short
        get moddate         	short
        get crc             	long
        get skip_comp_size	    long
        get skip_uncomp_size	long
        get name_len        	short
        get extra_len       	short
        getdstring name	name_len
        getdstring extra extra_len
        savepos offset
		
        set NEW_CRC = crc
        math NEW_CRC -= 87
        string NEW_PASSWORD p= ZIP_PASSWORD NEW_CRC

        if flag != 0
            if flag & 1
                encryption zipcrypto NEW_PASSWORD 1
            endif
            if method == 0
                log name offset uncomp_size
            else
                clog name offset comp_size uncomp_size
            endif
            if flag & 1
                encryption "" ""
            endif
        endif

    goto CENTRAL_OFFSET
next i

```
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-08-26T06:01:12+00:00
- Post Title: Eligium (Magic World 2) (*.MW2)

the files unpacked very well but a lot files broken, I think 50% of files are broken after all unpack so maybe you can try update script?
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-26T10:12:36+00:00
- Post Title: Eligium (Magic World 2) (*.MW2)

They not broken, they encrypted.
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-08-26T17:49:57+00:00
- Post Title: Eligium (Magic World 2) (*.MW2)

> Reply from Ekey
>
> They not broken, they encrypted.the files have 0kb size so how is possible? in any case they need be have correct size don't think?
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-26T18:44:05+00:00
- Post Title: Eligium (Magic World 2) (*.MW2)

0 kb because can't be decompressed
## Post #6
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-08-26T18:54:47+00:00
- Post Title: Eligium (Magic World 2) (*.MW2)

> Reply from Ekey
>
> 0 kb because can't be decompressedok many thanks for try anyway, take care.
## Post #7
- Username: Milkom
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 28, 2016 6:51 pm
- Post datetime: 2016-09-28T11:49:47+00:00
- Post Title: Eligium (Magic World 2) (*.MW2)

help write a script for importing into Farmat mw2.
