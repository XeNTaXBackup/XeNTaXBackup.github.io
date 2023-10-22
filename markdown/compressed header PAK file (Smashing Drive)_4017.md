## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-06T12:26:12+00:00
- Post Title: compressed header PAK file (Smashing Drive)

Hi everyone,

can someone take a look at this archive here? [http://www.sendspace.com/file/7k6j60](http://www.sendspace.com/file/7k6j60)
It seems to have a compressed header and maybe compressed files. It's big endian and from the game "Smashing Drive". Thanks for you help!

Regards, Timo
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-10T14:18:11+00:00
- Post Title: compressed header PAK file (Smashing Drive)

*update* use the hcs script
## Post #3
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-10T19:31:44+00:00
- Post Title: compressed header PAK file (Smashing Drive)

```

endian big
get FILES long
for i = 0 < FILES
    set HEADER_POS i
    math HEADER_POS * 0x70
    math HEADER_POS + 4

    goto HEADER_POS
    get OFFSET long
    get SIZE long
    savepos HEADER_POS
    log MEMORY_FILE HEADER_POS 0x60
    math HEADER_POS + 0x60
    goto HEADER_POS
    getdstring NAME 8

    string NAME += "_"
    string NAME += i    # avoids duplicates!
    string NAME += ".dsp"

    append
    log MEMORY_FILE OFFSET SIZE
    append

    math SIZE + 0x60
    log NAME 0 SIZE MEMORY_FILE 
next i

```


The headers are standard DSP, just need to append them onto the data and vgmstream handles it fine.  Some of the files that are the same size should be renamed to play as stereo,  for instance:
MUSIC3_L_6.dsp and MUSIC3_R_7.dsp to MUSIC3_L.dsp and MUSIC3_R.dsp
or
MCONTINU_10.dsp and MCONTINU_11.dsp to MCONTINU_L.dsp MCONTINU_R.dsp
Rule of thumb is files with names ending in _L and _R will be played together as stereo.

As for GENH, it's kind of a mess, so I'm not going to touch it unless I have to.
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-10T22:51:13+00:00
- Post Title: compressed header PAK file (Smashing Drive)

That's what I was looking for, HCS, thanks a lot! 
Already did this manually as I understood the structure but this script could come in handy with other GameCube games!
