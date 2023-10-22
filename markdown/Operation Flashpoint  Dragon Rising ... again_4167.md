## Post #1
- Username: templargfx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2009 4:46 pm
- Post datetime: 2010-02-23T07:12:13+00:00
- Post Title: Operation Flashpoint : Dragon Rising ... again

Hi Everyone,

I was wondering if it is possible to get you genius' to take another look at Dragon Rising?

With the latest news from Codemasters that they have completely dropped support for the game, it comes down to the community to try and make improvements to the game, but with the entire game files hidden away in those 523 8mb pack files, we cant really do anything!


For those who arent aware, here is the old XentaX thread : [viewtopic.php?f=10&t=3763&st=0&sk=t&sd=a](http://forum.xentax.com/viewtopic.php?f=10&t=3763&st=0&sk=t&sd=a)

the test unpacker created by aluigi successfully unpacked around 210meg of data before killing itself when attempting to unpack the file 2dmap.asset.xml

using the merging script in that thread, and then using quickbms to list the contents of the nfs file I noticed this :

  05659cf2 4928       asset_maps\tree.asset.xml
  73ec648c 4928       asset_maps\tree.asset.xml
  0565a0a9 9041       asset_maps\vehicle.asset.xml
  73ec6843 9041       asset_maps\vehicle.asset.xml
  0565a700 29062      asset_maps\weapon.asset.xml
  73ec6e9a 29062      asset_maps\weapon.asset.xml
  0565b895 5676       trees\billboard.xml
  0565bf73 1400176    textures\billboard.stf
  0570cec5 176824     textures\billboard_nrm.stf
  057245c2 2296       lakes\asset_list.txt
  73ec802f 2296       lakes\asset_list.txt
  057249c1 1444       lakes\xall_yall_lakewater01.ib
  73ec842e 1444       lakes\xall_yall_lakewater01.ib
  05724d77 352        lakes\xall_yall_lakewater01.met
  73ec87e4 352        lakes\xall_yall_lakewater01.met
....... ***removed the large number of lakes\* entries in between
  0572c650 1000       lakes\xall_yall_lakewater20.vb
  73ed00bd 1000       lakes\xall_yall_lakewater20.vb
  0572c7dd 1218       terrain\surface_types.xml
  0572c94f 1868026669 terrain\hi_lod.tpk
  4c0afef3 354496060  terrain\mid_lod.tpk
  55c00c8a 230        terrain\terrain.xml
  55c00d29 12539      terrain\uber_lod.tpk
  55c01435 149086     uberlod\uberlod.ib
  55c24510 312        uberlod\uberlod.met
  55c24575 211696     uberlod\uberlod.vb
  55c52eda 5594472    diffusemap\dif_uberlod.stf
  55f72952 2798288    normalmap\nrm_uberlod.stf
  5614bd24 907127     buildings\assetlist.xml


all of the files under asset_maps and lakes folders are listed twice. if you look at the offsets, the second entry for each is WAY off. the 05xxxxxxxx offsets are obviosuly the correct offsets for the files, as they are continued logically through out the remainder of the listing of files. however these 73xxxxxxxx offsets are completely out of place. 

any files past this point, if extracted with the -f "filename" command, are full of gibberish. so 

just out of curiousity, here is the part of the listing where thes rogue offsets would sit :

  73ec3009 384        nv\weapon_shadow_low_static.vpo
  73ec3125 348        nv\weapon_shadow_low_static_pos_only.vpo
**  73ec322c 518        asset_maps\2dmap.asset.xml **first rogue offset
**  73ed00bd 1000       lakes\xall_yall_lakewater20.vb **last rogue offset
  73ed024a 23920      nv\bullet_wake.stf
  73ed2690 2099200    nv\clouds.stf

so my first and most obvious question is, can the extractor script be modified to ignore these majorly out of sequence offsets (and the seemingly phantom file entry in the NFS)?

```
# note: you MUST run opflash2_create.bms first!
# note: all this script is a complete horrible work-around... but it seems to work
# note: the folders are not handled correctly so there will be not sub-sub folders
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

comtype lzss

get SIZE asize
encryption aes "\xAC\x22\x11\x23\x44\x95\xAC\xA2\x7E\x80\x59\x86\x10\x8B\xEE\xDD\x4D\x01\xD3\x97\x0B\x9D\x4C\xA9\x3D\x7B\xE1\xBB\xED\xDA\x84\x58"
log MEMORY_FILE 0 SIZE
encryption "" ""

findloc NAMEOFF string "system" MEMORY_FILE # lame solution
goto NAMEOFF MEMORY_FILE
for i = 0
    get NAME string MEMORY_FILE
    if NAME == ""
        break
    endif
    putarray 0 i NAME
next i

open FDSE "win_000.full"

set FOLDER string ""
set PREV_OFFSET long 0
set DATAOFF long 0x7e
set OFFSET_SEEK 0x2c0000

for i = 0
    goto DATAOFF MEMORY_FILE
    get NAMENUM long MEMORY_FILE
    get DUMMY3 long MEMORY_FILE
    get SIZE long MEMORY_FILE
    get FILENUM long MEMORY_FILE
    get DUMMY4 long MEMORY_FILE
    get TYPE long MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get DUMMY1 long MEMORY_FILE
    savepos DATAOFF MEMORY_FILE

    if OFFSET == 0
    if SIZE == 0
    if FILENUM == 0
        cleanexit
    endif
    endif
    endif

    if i == 0
        set OFFSET_SEEK long OFFSET
    endif

    math OFFSET -= OFFSET_SEEK
    math ZSIZE = OFFSET
    math ZSIZE -= PREV_OFFSET

    math NAMENUM >>= 4
    if i == 0   # work-around
        set NAMENUM long 0
    endif
    getarray NAME 0 NAMENUM

    set FULLNAME string FOLDER
    string FULLNAME += \
    string FULLNAME += NAME

    if SIZE == 0    # should check TYPE but this one is better
        set FOLDER string NAME
    elif SIZE == ZSIZE
        log FULLNAME PREV_OFFSET SIZE
    else
        clog FULLNAME PREV_OFFSET ZSIZE SIZE
    endif

    math PREV_OFFSET = OFFSET
next i
```

*I have reposted this script, as it is permenantly stickied at the DR forum, so no use hiding it   *

anyway, I really have absolutely no idea what I am talking about   

the entire DR PC community would be eternally greatful is someone is able to figure this out!
## Post #2
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-02-23T14:41:32+00:00
- Post Title: Operation Flashpoint : Dragon Rising ... again

Sry 4 Off Topic but they Encrypted the Files after a Patch ....

And anyone playing this? I think DR is already dead?
## Post #3
- Username: templargfx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2009 4:46 pm
- Post datetime: 2010-02-23T15:05:39+00:00
- Post Title: Operation Flashpoint : Dragon Rising ... again

you can still uncompress the first 210 meg as in version 1.0 in version 1.02 so Im sure they did not change the encryption.

the 100+ downloads per week of my missions (each) begs to differ
## Post #4
- Username: Maddog
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Oct 11, 2009 4:59 am
- Post datetime: 2010-02-23T18:51:36+00:00
- Post Title: Operation Flashpoint : Dragon Rising ... again

Hey Templar

I understand your concern about this title, since CM latest statement about dropping  support for their overhyped lie.
Also I know your contribution to DR community is awesome. Unfortunately I personally wasted lot of time trying to extract uncorrupted pieces without success.
As Aluigi said, that format is mess and in time with their future titles, maybe we will be able to encrypt that format fine.
I would like to get more people interested in this, since CM doesn't deserve nothing more than breaking their Ego.
You know that involving you in this will ban you from CM as of my understandings, you apparently have some eula signed with them.
After patch 1.01 game doesn't read extracted data in folders so I see no use of doing this unless hacking .exes and that pretty much is beyond legal boundaries.

Anyway I will keep you posted if I find anything knew.

Regards.
## Post #5
- Username: templargfx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Oct 20, 2009 4:46 pm
- Post datetime: 2010-03-17T07:28:53+00:00
- Post Title: Operation Flashpoint : Dragon Rising ... again

I am hoping someone can figure this one out. I have worked out that the models for the game are stored within the havok files, and easily removable (and theoretically replacable) which means, should I be able to extract the unit HVK files I will be able to fix the problem of the 2 teams using the exact same model at a distance (theres more to it than simple model replacement, but I wont go into that here)

The majority of the DR community has already reverted back to 1.00 of the game thanks to the fact that not only does the game generally work better without the patches, but you can use the modified files (its the only game in history where people prefer NOT patching a game because the patches make it worse)

I signed a non-disclosure agreement with CM which has absolutely nothing to do with what I do with the game, just with anything they tell me. and Helios (forum manager) knows all to well I mess with the original files, and I havent been banned.


I beg anyone to help this dying community!
## Post #6
- Username: djoscar
- Rank: beginner
- Number of posts: 30
- Joined date: Thu Dec 17, 2009 4:59 pm
- Post datetime: 2010-07-05T17:05:08+00:00
- Post Title: Operation Flashpoint : Dragon Rising ... again

errr, you know that you don't need any scripts for merging all those .000, .001 etc files together.
Find the file with extension .001, and use 7zip to extract it. It will then extract all of those .xxx files into one 4.2GB file.
The script you provided above doesn't work at all with this 4.2gb archive, says 0 files found, so you guys were probably doing it wrong by trying to merge the files together manually and then writing bms exporter for that merged archive which may have lead you to that error in the middle of extraction.

I would have given writing a bms script for this archive a shot, how ever considering the fact that it is one 4.2gb file i am unable to open it up in Hex editor because it says "Not enough memory" 

I know for sure that this archive is right and that it contains the assets because I opened it up in Notepad++ and I saw a lot of strings like /media/models/ leading to files with extensions .hkx etc., although some of them looked kinda weird like "mßedia/" etc...

Could someone please try to write a BMS script to export this archive?
## Post #7
- Username: masterX244
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 17, 2010 12:48 am
- Post datetime: 2010-08-24T11:17:53+00:00
- Post Title: Operation Flashpoint : Dragon Rising ... again

> Reply from djoscar
>
> errr, you know that you don't need any scripts for merging all those .000, .001 etc files together.
Find the file with extension .001, and use 7zip to extract it. It will then extract all of those .xxx files into one 4.2GB file.
The script you provided above doesn't work at all with this 4.2gb archive, says 0 files found, so you guys were probably doing it wrong by trying to merge the files together manually and then writing bms exporter for that merged archive which may have lead you to that error in the middle of extraction.

I would have given writing a bms script for this archive a shot, how ever considering the fact that it is one 4.2gb file i am unable to open it up in Hex editor because it says "Not enough memory" 

I know for sure that this archive is right and that it contains the assets because I opened it up in Notepad++ and I saw a lot of strings like /media/models/ leading to files with extensions .hkx etc., although some of them looked kinda weird like "mßedia/" etc...

Could someone please try to write a BMS script to export this archive?
Try to open the file with universal viewer! It has a hex viewer built in and didnt load the complete file in Memory!
It loads only the viewed part and a bit more in the memory.That means that the file can be as big as the hard disk hold and no trouble!
