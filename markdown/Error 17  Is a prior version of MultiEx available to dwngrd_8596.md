## Post #1
- Username: badactor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 20, 2012 11:05 am
- Post datetime: 2012-03-20T03:13:02+00:00
- Post Title: Error 17?  Is a prior version of MultiEx available to dwngrd

I'm trying to run a script someone else wrote to extract some sound files, but it will not run.  Bombs out with an Error 17 immediately.  The users using this script from 2011 seem to indicate it works great, but there are problems with the current MultiEx alpha.  Is there an older version available that I can downgrade to?  I'm trying to convert .msf files so I can load them in sound forge.

Her'es the script:

# MSFtoAT3.bms, script 1.2
# written in 2011 by AlphaTwentyThree
# transform PS3 *.msf files into playable Atrac *.at3 files

IDstring MSF
set MEMORY_FILE binary "\x52\x49\x46\x46\x88\xb3\x6d\x0\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x0\x0\x0\x70\x2\x2\x0\x80\xbb\x0\x0\x9a\x40\x0\x0\x80\x1\x0\x0\xe\x0\x1\x0\x0\x10\x0\x0\x0\x0\x0\x0\x1\x0\x0\x0\x66\x61\x63\x74\x8\x0\x0\x0\x91\x81\x24\x1\x1b\x4\x0\x0\x64\x61\x74\x61\x88\xb3\x6d\x0"
endian big
get SIGN byte
get BITSIGN long
get CH long
get SIZE long
get FREQ long
set SKIP 0x40
get SIZE asize
math SIZE -= SKIP
set RIFFSIZE SIZE
math RIFFSIZE += 0x44

endian little
putVarChr MEMORY_FILE 0x04 RIFFSIZE long
putVarChr MEMORY_FILE 0x16 CH byte
putVarChr MEMORY_FILE 0x18 FREQ long
putVarChr MEMORY_FILE 0x48 SIZE long
if BITSIGN == 4 # 66 kbps
        putVarChr MEMORY_FILE 0x1c 0x204d long
        putVarChr MEMORY_FILE 0x20 0xc0 long
    elif BITSIGN == 5 # 105 kbps
        putVarChr MEMORY_FILE 0x1c 0x3324 long
        putVarChr MEMORY_FILE 0x20 0x130 long
    elif BITRSIGN == 6 # 132 kbps
        putVarChr MEMORY_FILE 0x1c 0x409a long
        putVarChr MEMORY_FILE 0x20 0x180 long
endif

append
log MEMORY_FILE SKIP SIZE
append
math SIZE += 0x4c
goto 0x28
getDstring NAME 0x17
string NAME += ".at3"
log NAME 0 SIZE MEMORY_FILE
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-03-23T09:11:14+00:00
- Post Title: Error 17?  Is a prior version of MultiEx available to dwngrd

This is not a MultiEX BMS script, but a Quickbms script. QuickBMS is based on MultiEx BMS, but has added features. Make sure you use the scriptor in MultiEx Commander, and then select to use the QuickBMS script. If that doesn't work, try the QuickBMS tool itself, or QuickBMS GUI.
