## Post #1
- Username: biplexive
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 19, 2015 6:40 am
- Post datetime: 2015-05-25T01:38:02+00:00
- Post Title: Unity3d CustomAssetBundle

I have some really unique Unity Custom Asset Bundles, made in the rather exotic custom editor of Unity called 2.5.5b4, and I have had no luck on getting anything from them (except music and a bunch of corrupted/missing header files obtained from alugis QuickBMS) .. I'll include a sample to download.  Also I approached the author of QuickBMS for help, and he managed to extract the files (sort of) but they seem to be unusable and he recommended I contact the developer of Disunity instead. His comments were "The format of these bundles are very similar to the previous one and in the script it's enough to search the "0xe" keyword to spot the differences and update the script to support these files. It's quite easy for the disunity developer in my opinion.".

Here is a sample of the bundles: [https://www.mediafire.com/?cct8539ch9gcell](https://www.mediafire.com/?cct8539ch9gcell)

Thanks!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-25T06:54:04+00:00
- Post Title: Unity3d CustomAssetBundle

I'm missing the link to aluigi's script.

You could determine the files' structure like this (left part of pic):



CustomAssetBundle.JPG (163.11 KiB) Viewed 132 times



I couldn't get a decent point cloud from the none-texture data.
So don't know if it's vertices.

edit: from your other thread I read: "I managed to get these corrupt .dds files to work"
You really shouldn't split your request cross forums.
Just my two cents.
## Post #3
- Username: biplexive
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 19, 2015 6:40 am
- Post datetime: 2015-05-25T12:41:24+00:00
- Post Title: Unity3d CustomAssetBundle

> Reply from shakotay2
>
> I'm missing the link to aluigi's script.

You could determine the files' structure like this (left part of pic):
CustomAssetBundle.JPG

I couldn't get a decent point cloud from the none-texture data.
So don't know if it's vertices.

edit: from your other thread I read: "I managed to get these corrupt .dds files to work"
You really shouldn't split your request cross forums.
Just my two cents.

Oh I'm sorry, my bad. I was just looking for help.. but btw the broken images, it is a very time consuming task, averaging like 15-25 minutes per image (taking,adding hex data) is what you did easier?

also here is the script I used:

```
                        # or if you are sure that there are no names

quickbmsver "0.5.32"

# from my tests:
# - all the mainData are nameless
# - only some *.assets are nameless
# I have not found a point where it's written if a resource is nameless or not
get FULL_NAME filename
if FULL_NAME == "mainData"
    math GUESS_NAMES = 0
endif

get EXT extension
if EXT == "unity3d"
    print "Error: you must use the unity3d_webplayer.bms script for this archive"
    cleanexit
endif

endian big
get HEADER_SIZE long
get FULL_SIZE long
get VERSION long
get BASE_OFF long

math ZERO_GUESS = 0
if VERSION <= 8
    xmath OFFSET "FULL_SIZE - HEADER_SIZE"
    goto OFFSET
    get DUMMY byte
else
    # version 9 tested
    get ZERO_GUESS long
endif

endian little
endian guess ZERO_GUESS
if VERSION >= 8
    get VERSION_STRING string
    print "%VERSION_STRING%"
    get DUMMY long
endif
if VERSION >= 0xe
    get ZERO byte
    get BASES long
    for i = 0 < BASES
        get DUMMY signed_long
        if DUMMY < 0
            getdstring DUMMY 0x20
        else
            getdstring DUMMY 0x10
        endif
    next i
else
    get BASES long
    for BASE = 0 < BASES
        get DUMMY long
        math SUB_ELEMENTS = 1
        callfunction PARSE_TYPES
    next BASE
endif

math ADDITIONAL_FIELD = 0
if VERSION >= 7
if VERSION < 0xe
    get ADDITIONAL_FIELD long
endif
endif
get FILES long

if VERSION >= 0xe
    get ZERO short
endif
for i = 0 < FILES
    if VERSION >= 0xe
        get INDEX long
        get ZERO long
        get OFFSET long
        get SIZE long
        get TYPE long
        get XTYPE short # same as TYPE
        get DUMMY short # -1
    else
        get INDEX long
        if ADDITIONAL_FIELD != 0
            get ZERO long
        endif
        get OFFSET long
        get SIZE long
        get TYPE long
        get XTYPE long  # same as TYPE
    endif

    savepos TMP_OFF
    xmath OFFSET_TMP "OFFSET + BASE_OFF"
    goto OFFSET_TMP

    math GET_FILENAMES = 0
    if GUESS_NAMES != 0
        get NAMESZ long
        if NAMESZ u< 128
            getdstring NAME NAMESZ
            strlen TMP NAME
            if TMP == NAMESZ
                math GET_FILENAMES = 1
            endif
        endif
        goto OFFSET_TMP
    endif

    set NAME string ""
    if GET_FILENAMES != 0
        get NAMESZ long
        getdstring NAME NAMESZ
        padding 4
    endif
    savepos OFFSET
    goto TMP_OFF

    xmath TMP "SIZE - (OFFSET - OFFSET_TMP)"
    if TMP < 0
        math OFFSET = OFFSET_TMP
    else
        math SIZE = TMP
    endif

    getvarchr TMP NAME 0
    if TMP <= 0x20
        set NAME string ""
    endif

    string FNAME p= "TYPE_%d/%s" TYPE NAME

    log FNAME OFFSET SIZE
next i

startfunction PARSE_TYPES
    math ELEMENTS = SUB_ELEMENTS
    for ELEMENT = 0 < ELEMENTS
        get TYPE string
        get NAME string
        get SIZE long
        get INDEX long
        get ZERO long
        get DUMMY long
        get DUMMY long
        get SUB_ELEMENTS long
        if SUB_ELEMENTS != 0
            callfunction PARSE_TYPES
        endif
    next ELEMENT
endfunction
```
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-25T14:30:01+00:00
- Post Title: Unity3d CustomAssetBundle

> Reply from biplexive
>
> but btw the broken images, it is a very time consuming task, averaging like 15-25 minutes per image (taking,adding hex data) is what you did easier?depends on. If you load an extracted file into TexureFinder such as
vehicle_hoverboard (from CustomAssetBundle-CharacterSelection_wear_vehicle) and save it as bmp file it might be faster, but not sure, some scaling/cutting/shifting might be required:



vehicle_hoverboard.JPG (55.34 KiB) Viewed 121 times



> also here is the script I used:thx!
Could you give an example for "to search the "0xe" keyword"?
## Post #5
- Username: biplexive
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 19, 2015 6:40 am
- Post datetime: 2015-05-25T15:51:20+00:00
- Post Title: Unity3d CustomAssetBundle

> Reply from shakotay2
>
> biplexive wrote:but btw the broken images, it is a very time consuming task, averaging like 15-25 minutes per image (taking,adding hex data) is what you did easier?depends on. If you load an extracted file into TexureFinder such as
vehicle_hoverboard (from CustomAssetBundle-CharacterSelection_wear_vehicle) and save it as bmp file it might be faster, but not sure, some scaling/cutting/shifting might be required:
vehicle_hoverboard.JPG
also here is the script I used:thx!
Could you give an example for "to search the "0xe" keyword"?

Honestly, I'm not too sure on what he meant by that as I am quite new to all of this, also do you think It's possible to retrieve models and animations with this? also would It help if i sent you some more bundles? 

Here is another page I posted for help, which includes some more information - [https://github.com/ata4/disunity/issues/95](https://github.com/ata4/disunity/issues/95)

Also, I had never heard of texturefinder before so thank you so much for showing it lol

EDIT - Here is the whole game's bundles : [http://www.mediafire.com/download/6wkrm ... undles.zip](http://www.mediafire.com/download/6wkrmwp81pjxnkj/FusionFallBundles.zip)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-25T20:20:09+00:00
- Post Title: Unity3d CustomAssetBundle

> Reply from biplexive
>
> , also do you think It's possible to retrieve models and animations with this?I've checked the files vehicle_hovercarC and Editable Poly and I can't seem to find a decent point cloud.

> also would It help if i sent you some more bundles?Thx, no. I can't spend more than 5 minutes per model, 15 minutes in sum, and that's what I've done.

> EDIT - Here is the whole game's bundles : xxxx://www.mediafire.com/.../FusionFallBundles.zip
Is it a free game? (If 'no' you should remove the link.  )
## Post #7
- Username: biplexive
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 19, 2015 6:40 am
- Post datetime: 2015-05-25T20:49:58+00:00
- Post Title: Unity3d CustomAssetBundle

> Reply from shakotay2
>
> biplexive wrote:, also do you think It's possible to retrieve models and animations with this?I've checked the files vehicle_hovercarC and Editable Poly and I can't seem to find a decent point cloud.
also would It help if i sent you some more bundles?Thx, no. I can't spend more than 5 minutes per model, 15 minutes in sum, and that's what I've done.
EDIT - Here is the whole game's bundles : xxxx://www.mediafire.com/.../FusionFallBundles.zip
Is it a free game? (If 'no' you should remove the link.  )

Yes, it was a free game. 
Thanks for all the help anyway
