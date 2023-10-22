## Post #1
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-03-20T18:36:22+00:00
- Post Title: Grand Theft Auto III/Vice City/San Andreas *.img

[https://mega.nz/file/oTAFGI5D#21UwEhDbk ... EIkvAwvK30](https://mega.nz/file/oTAFGI5D#21UwEhDbkDxhkEW2wpt3dYEl3O2YPuHZIEIkvAwvK30)
[https://mega.nz/file/kG4zWaBK#G1dFN8hgz ... TWBM_inbHc](https://mega.nz/file/kG4zWaBK#G1dFN8hgzYm_rz65ESY81qkbNHkUc7HACTWBM_inbHc)

GTA Vice City uses the same format.
Though I managed to extract or repack files from gta3.img.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-03-20T20:57:43+00:00
- Post Title: Grand Theft Auto III/Vice City/San Andreas *.img

But what is the issue? You didn't ask any question in your post...

Format is known [https://gta.fandom.com/wiki/IMG_Archive](https://gta.fandom.com/wiki/IMG_Archive)

And you can use IMG Tool for both archives [http://www.thegtaplace.com/downloads/file.php?id=552](http://www.thegtaplace.com/downloads/file.php?id=552)
## Post #3
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-05-20T12:50:00+00:00
- Post Title: Grand Theft Auto III/Vice City/San Andreas *.img

Can you make a QuickBMS script and format documenation on the wiki?
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-20T21:15:26+00:00
- Post Title: Grand Theft Auto III/Vice City/San Andreas *.img

> Reply from mrmaller1905 ↑Fri May 20, 2022 8:50 pm at Fri May 20, 2022 8:50 pm
>
> 
Can you make a QuickBMS script and format documenation on the wiki?

Sure, here is the article [http://wiki.xentax.com/index.php/GTA_Series_IMG_DIR](http://wiki.xentax.com/index.php/GTA_Series_IMG_DIR)

And new quickbms script is not needed, because there are several tools listed on the wiki
that supports this file format [https://imgur.com/a/3Syssvu](https://imgur.com/a/3Syssvu)
Just choose something and test if it works for you.
## Post #5
- Username: grandshot
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 16, 2019 9:43 pm
- Post datetime: 2022-05-23T20:00:43+00:00
- Post Title: Grand Theft Auto III/Vice City/San Andreas *.img

Well, sometime I wrote extract script for GTA 3\VC with support XBOX compression. You can use it if want.

```

open FDDE DIR 0
open FDDE IMG 1

get dirSize asize 0
xmath numFiles "dirSize / 32"

for i = 1 to numFiles
	get offset long 0
	get size long 0
	getDString name 24 0
	
	math offset * 2048
	math size * 2048
	
	goto offset 1 SEEK_SET
	get sign long 1
	if sign == 0x67A3A1CE
		log MEMORY_FILE 0 0
		get checksum long 1
		get sizeOfData long 1
		
		savepos destOffset 1
		math destOffset + sizeOfData
		for
			get dummy long 1
			get size long 1
			get zsize long 1
			
			savepos offset 1
			
			append
			clog MEMORY_FILE offset zsize 256000 1
			append
			
			goto zsize 1 SEEK_CUR
			
			savepos curOffset 1
			if curOffset >= destOffset
				break
			endif
		next
		
		get size asize MEMORY_FILE
		log name 0 size MEMORY_FILE
	else
		log name offset size 1
	endif
next i
```
## Post #6
- Username: grandshot
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Mar 16, 2019 9:43 pm
- Post datetime: 2022-05-24T19:56:59+00:00
- Post Title: Grand Theft Auto III/Vice City/San Andreas *.img

Decide to rewrite a script. Now it support IMGs from all GTA series, include GTA IV but which not encrypted.

```

open FDDE IMG 0
open FDDE DIR 1 DIR_EXISTS
if DIR_EXISTS == 1
    callfunction VER1 # GTA3/Vice City/Bully PC
endif

get SIGNATURE long 0
if SIGNATURE == 0x32524556 # GTA San Andreas (VER2)
    callfunction VER2
elif SIGNATURE == 0xA94E2A52 # GTA IV (R*N)
    callfunction VER3
else
    # TODO decryption of GTA IV IMGs and check signature again
    
endif

startfunction VER1
    get DIR_SIZE asize 1
    xmath ENTRIES "DIR_SIZE / 32"

    for I = 1 to ENTRIES
        get OFFSET long 1
        get SIZE long 1
        getdstring NAME 24 1
        
        math OFFSET * 2048
        math SIZE * 2048

        # Check file compression by signature
        goto OFFSET 0
        get FILE_SIGN long 0
        if FILE_SIGN == 0x67A3A1CE # lzo1x stream magic number
            log MEMORY_FILE OFFSET SIZE 0
            callfunction DECOMPRESS 0 NAME
        else 
            log NAME OFFSET SIZE 0
        endif
    next I

endfunction

startfunction VER2
    get ENTRIES long 0
    for I = 1 to ENTRIES
        get OFFSET long 0
        get SIZE short 0
        get DUMMY short 0 # always 0
        getdstring NAME 24 0
        
        math OFFSET * 2048
        math SIZE * 2048

        log NAME OFFSET SIZE 0
    next I
endfunction

startfunction VER3
    get VERSION long 0
    if VERSION != 3
        print "Unknown GTA IV IMG version: %VERSION%\nOnly version 3 is support.\n"
        cleanexit
    endif

    get ENTRIES long 0
    get TABLE_SIZE long 0
    get TABLE_ITEMS_SIZE short 0
    if TABLE_ITEMS_SIZE != 16
        print "Unknown GTA IV IMG TABLE_ITEMS_SIZE: %TABLE_ITEMS_SIZE%\nIt's should be 16.\n"
        cleanexit
    endif
    get DUMMY short 0

    # Calculate size of Names Table
    xmath NAMES_TABLE_OFFSET "ENTRIES * 16 + 20"
    xmath NAMES_TABLE_SIZE "TABLE_SIZE - ENTRIES * 16"
    # Load Names Table to MEMORY_FILE for usability
    log MEMORY_FILE NAMES_TABLE_OFFSET NAMES_TABLE_SIZE 0

    for I = 1 to ENTRIES
        get SIZE long 0
        get TYPE long 0 # 0x01: Generic, 0x08: Texture archive, 0x20: Bounds, 0x6E: Model file, 0x24: xpfl
        get OFFSET long 0
        get SIZE_IN_BLOCKS short 0
        get ALIGN short 0

        math OFFSET * 2048

        get NAME string MEMORY_FILE

        log NAME OFFSET SIZE 0
    next I
endfunction

startfunction DECOMPRESS 
    get MAGIC long MEMORY_FILE
    get CHECKSUM long MEMORY_FILE
    get ENTIRE_SIZE long MEMORY_FILE # Entire size of all compressed blocks
    math ENTIRE_SIZE + 12

    # lzo1x stream consists of some number of compressed blocks
    # so we need to decompress each one individually

    for
        get DUMMY long MEMORY_FILE
        get SIZE long MEMORY_FILE # suggested decompressed size, often not equal to correct output buffer size
        get ZSIZE long MEMORY_FILE

        savepos OFFSET MEMORY_FILE

        # Append decompressed block data directly to extracted file
        append
        # 256000 bytes is enough buffer for block decompress, because
        # The Rockstar Compressor dividing raw data to 131072 bytes chunks before compression 
        clog DECOMPRESS_ARG1 OFFSET ZSIZE 256000 MEMORY_FILE   
        append

        math OFFSET + ZSIZE
        if OFFSET == ENTIRE_SIZE
            break
        else
            goto OFFSET MEMORY_FILE
        endif 
    next
endfunction


```

[gta_img_universal.zip](https://xentaxbackup.github.io/file/22255_gta_img_universal.zip)
