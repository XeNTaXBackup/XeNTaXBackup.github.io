## Post #1
- Username: biplexive
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 19, 2015 6:40 am
- Post datetime: 2015-05-16T23:43:05+00:00
- Post Title: FusionFall Custom Asset Bundles (Unity 3d)

These are really unique Unity Custom Asset Bundles that I am trying to extract contents of, they are from an old free to play MMO called FusionFall, made in the rather exotic custom editor of Unity called 2.5.5b4, and I have had no luck on getting anything from them (except music and a bunch of corrupted/missing header files obtained from QuickBMS) 

I am trying to do this for a recreation game I'm making, and I have all the custom asset bundles, None of the files are ready to use other than the sound files. I managed to get these corrupt .dds files to work by taking data from them using Notepad ++ and injecting them into blank .dds files. There are plenty of files such as terrains, models, etc but I don't know how to get them to work. also, doing the manual method for fixing the DDS files, takes like 10 minutes for each texture and is very time consuming, for 1000's of images. I will put an example of them in a .zip file. Please help 

Here is a sample of the CustomAssetBundles - [http://www.mediafire.com/download/cct85 ... ported.zip](http://www.mediafire.com/download/cct8539ch9gcell/CustomAssetBundles_Unsupported.zip)
Here is a sample of some corrupted images, and then the same images converted, so you can compare - [http://www.mediafire.com/download/zib1ozj30hmay7h](http://www.mediafire.com/download/zib1ozj30hmay7h)

Here is the QuickBMS Script I used:

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


and finally, here is a post I made to ata4 on disunity, if his reply may help at all - [https://github.com/ata4/disunity/issues/95](https://github.com/ata4/disunity/issues/95)
Thanks a lot, I look forward to reading your responses
## Post #2
- Username: biplexive
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Feb 19, 2015 6:40 am
- Post datetime: 2015-05-22T17:22:24+00:00
- Post Title: FusionFall Custom Asset Bundles (Unity 3d)

Bump... really need help with this
