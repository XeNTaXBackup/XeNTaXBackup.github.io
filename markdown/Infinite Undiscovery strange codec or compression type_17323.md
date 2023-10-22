## Post #1
- Username: Heisenberg1895
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 22, 2017 8:08 pm
- Post datetime: 2017-11-22T18:11:02+00:00
- Post Title: Infinite Undiscovery strange codec or compression type

m attempting to make an UNDUB of Infinite Undiscovery for the 360.
I have managed to extract the first disc, and from that i have extracted a .bin file that has given me tons of folders.
Within these folders are files with extensions such as .MESH and .TEX and im guessing they are fairly self explanatory as to what they contain.

Now the ones im interested are the ones ending .SOND, now im guessing this is the audio.

As you can probably tell, im VERY new to this so any advice you guys could give would be greatly appreciated.

For now I am unsure whether the .SOND files are encrypted audio or another layer of compression 

I have attached on of the files in case anyone wants to take a gander.

Thanks in advance
[2.7z](https://xentaxbackup.github.io/file/13580_2.7z)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-11-22T21:21:01+00:00
- Post Title: Infinite Undiscovery strange codec or compression type

15 min parsing attempt in 010 editor

there are wav chunks in here but they seem to be separate files (with filenames). however they have a "stream" chunk which i don't know anything about

```
//--- 010 Editor v5.0 Binary Template
//--------------------------------------

BigEndian();

struct Block;
struct Block
{
  char ID[4];
  uint Length;
  FSkip(8);

  switch(ID)
  {
    case "AAC ":
      uint SkippedInfo[8];
      Block Child;
    break;

     case "DIR ":
       uint items;
       FSkip(12);
       Block Child[items] <optimize=false>;

       local uint i=0;
       for(i=1;i<items;++i) {
         Printf("%s @ 0x%X - %u bytes\n", Child[i-1].name,
                        Child[i-1].offset,
                        (Child[i].offset-Child[i-1].offset));
       }

       Printf("%s @ 0x%X - %u bytes\n", Child[items-1].name,
                      Child[items-1].offset,
                      (FileSize()-Child[items-1].offset));

       break;
     case "dirn":
       Assert(Length == 160);
       char name[128];
       uint offset;
       FSkip(8);
       uint size; // not size!
       break;
  }
};

Block Root;

```


> ENMA_005_WALK_SOIL_R.wav @ 0xA000 - 8192 bytes
>
> ENMA_006_WALK_SOIL_L.wav @ 0xC000 - 8192 bytes
>
> ENMA_007_WALK_ROCK_R.wav @ 0xE000 - 8192 bytes
>
> ENMA_008_WALK_ROCK_L.wav @ 0x10000 - 8192 bytes
>
> ENMA_009_WALK_GRASS_R.wav @ 0x12000 - 8192 bytes
>
> ENMA_010_WALK_GRASS_L.wav @ 0x14000 - 8192 bytes
>
> ENMA_013_WALK_SNOW_R.wav @ 0x16000 - 12288 bytes
>
> ENMA_014_WALK_SNOW_L.wav @ 0x19000 - 12288 bytes
>
> ENMA_015_WALK_SAND_R.wav @ 0x1C000 - 8192 bytes
>
> ENMA_016_WALK_SAND_L.wav @ 0x1E000 - 12288 bytes
>
> ENMA_017_WALK_CLOTH_R.wav @ 0x21000 - 8192 bytes
>
> ENMA_018_WALK_CLOTH_L.wav @ 0x23000 - 8192 bytes
>
> ENMA_019_WALK_METAL_R.wav @ 0x25000 - 8192 bytes
>
> ENMA_020_WALK_METAL_L.wav @ 0x27000 - 8192 bytes
>
> ENMA_021_WALK_WATER_R.wav @ 0x29000 - 12288 bytes
>
> ENMA_022_WALK_WATER_L.wav @ 0x2C000 - 12288 bytes
>
> ENMA_023_WALK_MUD_R.wav @ 0x2F000 - 12288 bytes
>
> ENMA_024_WALK_MUD_L.wav @ 0x32000 - 12288 bytes
>
> ENMA_025_WALK_WOOD_R.wav @ 0x35000 - 8192 bytes
>
> ENMA_026_WALK_WOOD_L.wav @ 0x37000 - 8192 bytes
>
> ENMA_156_WALK_MOON_R.wav @ 0x39000 - 8192 bytes
>
> ENMA_157_WALK_MOON_L.wav @ 0x3B000 - 12288 bytes
## Post #3
- Username: Heisenberg1895
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 22, 2017 8:08 pm
- Post datetime: 2017-11-22T23:33:19+00:00
- Post Title: Infinite Undiscovery strange codec or compression type

Tried the script you posted and got this error.

Error: invalid command "FSkip" or arguments -1 at line 12.

And BTW, (seeing as you obv know more than me lol) 
My end goal was an UNDUB, so from what you have seen so far would you say its going to be more trouble than its worth?

I was hoping it was going to be a case of extractive the audio from both versions (Jap and Eng) and swapping them over.

Would it be feasible to just extract the other one now and just swap all the SOND files over without further extraction?
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2017-11-23T23:31:24+00:00
- Post Title: Infinite Undiscovery strange codec or compression type

> Reply from Heisenberg1895
>
> Would it be feasible to just extract the other one now and just swap all the SOND files over without further extraction?

as your end goal is just swapping them out, yeah that'd be the way to do it!

and how did you use my script? FSkip is a valid function!
## Post #5
- Username: Heisenberg1895
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 22, 2017 8:08 pm
- Post datetime: 2017-11-24T02:10:31+00:00
- Post Title: Infinite Undiscovery strange codec or compression type

So, let me get this straight.
To complete the undub i just extract the main .bin files on both the USA version and Jap version.
Take all the SOND files from the Jap version and put them in the USA version.
Problem is, then how do i repack the USA version?
I used a standard 360 extractor to get the main files (The XEX and 2 files named ud1.bin and ud2.bin)
I then extracted the .bin files using a script i found somewhere. 

```
#   God among men, Son of the Fifth House,
#   Holder of the Sacred Chalice of Rixx, Heir to the Holy Rings of Betazed    
# http://aluigi.org/papers/bms/xcompress_file.bms

endian big
set INC 0
callfunction MAIN
startfunction MAIN
    For
        findloc START string \x4D\x52\x4F\x4E\x30\x30\x2E\x32    #MRON00.2
        goto START
        get NAME basename
        getdstring SIGN 8
        get numFiles long
        get unk1 long
        if unk1 == 2048
            callfunction MAIN
        else
        endif
        get unk2 long
        get null1 long
        get null2 long
        get null3 long
        string NAME += /
        math INC += 1
        string NAME += INC
        string NAME += /
        for x = 0 < numFiles
            math HELL = START
            math i = x
            math i += 1
            string NAME2 = NAME
            getdstring FTYPE 4
            string FTYPE r FTYPE
            get unk3 long
            get FSIZE long
            get FOFF long
            get null4 long
            get null5 long
            get null6 long
            get null7 long
            savepos headEND
            math HELL += FOFF
            goto HELL
            getdstring EXT 3
            if EXT == "SLZ"
                callfunction DECOM
            else
                goto HELL
                string NAME2 += i
                string NAME2 += "."
                string NAME2 += FTYPE
                log NAME2 HELL FSIZE
            endif
            goto headEND
        next x
    Next
endfunction

startfunction DECOM
    get type byte
    get unkX long
    get slzCsize long
    get slzUsize long
    get null long
    get unkY long
    get studentID long
    get Version short
    get DinnerReservation short
    get ContextFlags long
    get wrinkledFlags long
    get WindowSize long
    get compPartSize long
    get unCompSizeUpper long
    get unCompSizeLower long
    get compSizeUpper long
    get compSizeLower long
    get unCompBLKsize long
    get compBLKsizeMAX long
    comtype XMemDecompress  
    putvarchr MEMORY_FILE unCompSizeLower 0
    log MEMORY_FILE 0 0
    append
    for blackCanary = 0 < unCompSizeLower
        get CompressedBlockSize long
        savepos OFFSET
        clog MEMORY_FILE OFFSET CompressedBlockSize unCompBLKsize
        math OFFSET += CompressedBlockSize
        goto OFFSET
        math blackCanary += unCompBLKsize
    next
    append
    string NAME += i
    string NAME += "."
    string NAME += FTYPE
    get blackCanary asize MEMORY_FILE
    log NAME 0 blackCanary MEMORY_FILE
endfunction
```


Now i dont pretend to understand even 1 word of that script but it worked lol.
That gave me 1367  sequentially numbered folders with various files in each folder.
If i do the same for the USA copy and transfer the Japanese SONDS over, how do i then repack the sequential folders back into a .bin file?

PS: I Tried using the "Reimporter" File using the same script but at the end it just kept saying 0 files reimported etc. so that doesnt work

PPS: Although now i come to think about it i probably need a different script lol
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-26T05:14:23+00:00
- Post Title: Infinite Undiscovery strange codec or compression type

just for kicks a bms script to split the "wav" files from sond sample 

```

endian big
idstring "AAC "
get TOTAL_SIZE long
getdstring SKIP 8
get FILES long //?
get DIR_OFF long
get UNK long
get PLBK_TABLE_OFF long //playback?
get UNK2 short
get UNK3 short
getdstring SKIP 12
get DIR long
get DIR_SZ long //?
getdstring SKIP 8
get FILES2 long
getdstring SKIP 12
for i = 0 < FILES2
	getdstring DIRN 4
	get DIRN_SZ long
	getdstring SKIP 8
	getdstring NAME 128
	get OFFSET long
	getdstring SKIP 8
	get UNK4 long
	savepos TMP
	goto OFFSET
	goto 0x4 0 seek_cur
	get SIZE long
	log NAME OFFSET SIZE
	goto TMP
next i

```
