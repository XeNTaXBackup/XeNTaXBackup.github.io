## Post #1
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2010-02-05T13:53:12+00:00
- Post Title: need help with writing a extractor with QuickBMS

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-05T15:54:42+00:00
- Post Title: need help with writing a extractor with QuickBMS

uhmmm there are various errors.
I try to list almost all of them so that they could be useful to you and others.

the first errors are in the format because size and frequency are long (32bits) and not short (16bits).
then the part from channels to the data is composed by 6 bytes (for example 2 bytes for channels and 4 for a parameter that I don't know).

instead in the script the problems are that you use variables without initializing them, for example "string NAME += _" but NAME doens't contain a value or "math FILES += 0xFF" instead of "math FILES = 0xFF".

then you specify "endian small" but the parameter "small" doesn't exist (little/intel or big/network) and then the endianess is already in little endian so why respecifying it 2 times?

then you already have 'i' declared so it's useless to use also COUNTER (that is also not initialized).
"string NAME -= 1" removes the last char from NAME that could work for the files from 0 to 9 and then?

findloc uses a threebyte type but you have specified a mix of number plus string, a simple findloc RES_START string "SND " was more than enough (indeed 0x20 is part of the signature).

if you need a cycle without an ending you don't need to specify it so the FILES variable can just be removed completely, example:
for i = 0
...
next i

the following is the script that performs the extraction you needed.
I have also added the automatic creation of the WAV header but if you need this only to learn the usage of the script watch till the commented line and ignore the rest:

```
    findloc SNDFILE string "SND "
    goto SNDFILE
    get SIGN long
    get SIZE long
    get FREQUENCY long
    get CHANNELS short
    get DUMMY long
    savepos OFFSET
    math SIZE -= 18
    #log "" OFFSET SIZE # simple dumping till here, the rest is raw2wav

    set BITS long 16
    set NAME string i
    string NAME += ".wav"
    callfunction raw2wav
next i

startfunction raw2wav
    set MEMORY_FILE binary "\x52\x49\x46\x46\x00\x00\x00\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x64\x61\x74\x61\x00\x00\x00\x00"

    set RIFFSIZE long SIZE
    math RIFFSIZE += 36
    set BLOCKALIGN long BITS
    set AVGBYTES long FREQUENCY
    math BLOCKALIGN /= 8
    math BLOCKALIGN *= CHANNELS
    math AVGBYTES *= BLOCKALIGN

    putvarchr MEMORY_FILE 4 RIFFSIZE long
    putvarchr MEMORY_FILE 20 1 short          # wFormatTag: Microsoft PCM Format (0x0001)
    putvarchr MEMORY_FILE 22 CHANNELS short   # wChannels
    putvarchr MEMORY_FILE 24 FREQUENCY long   # dwSamplesPerSec
    putvarchr MEMORY_FILE 28 AVGBYTES long    # dwAvgBytesPerSec
    putvarchr MEMORY_FILE 32 BLOCKALIGN short # wBlockAlign
    putvarchr MEMORY_FILE 34 BITS short       # wBitsPerSample
    putvarchr MEMORY_FILE 40 SIZE long

    log MEMORY_FILE2 0 44 MEMORY_FILE
    append
    log MEMORY_FILE2 OFFSET SIZE
    append

    math SIZE += 44
    log NAME 0 SIZE MEMORY_FILE2
endfunction
```

well, I hope it helps :)

*edit* little update of the script
## Post #3
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2010-02-05T16:38:12+00:00
- Post Title: need help with writing a extractor with QuickBMS

hm no that doesn't works right.
all files seems to have always the first sample, only some of them are playable, maybe the parameter at offset 15 is somthing different ?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-05T17:15:13+00:00
- Post Title: need help with writing a extractor with QuickBMS

I have only followed what you said using the size field you specified, I have done no further research.

in my opinion findloc should be used only in very very rare cases because the first way to follow is the full implementation of the archive's format from the first byte till the last one.
## Post #5
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2010-02-05T21:21:33+00:00
- Post Title: need help with writing a extractor with QuickBMS

yea but the thing is that the DDB isn't really a common archive.
It seems to have no file allocation/offset tables. There are only SND samples and some data with a "FRM2" signature, which can be frequency modulation infos or something.

don't know why, but "findloc SNDFILE string "SND ""  only finds the FIRST SND file and dumps it multiply.
so its dumping thousands of the first file in a loop, and not the next ones in a row..
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-05T22:26:21+00:00
- Post Title: need help with writing a extractor with QuickBMS

findloc works correctly, indeed the files are all differents and the loop terminates without problem automatically (if findloc got the same value it was an endless loop)
## Post #7
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2010-02-06T15:34:00+00:00
- Post Title: need help with writing a extractor with QuickBMS

ok then i can't tell why its always extracting the same file over and over again.
there must be something that doesn't tell that he should find the next file after the first one.
so file1: offset 526736... extract... next one -> file2: 1052546... extract... next one -> file3: 1607956... extract -> ......
and not: file1: offset 526736... extract... next one -> file2: 526736... extract... next one ->file3: 526736... extract -> ......

you see my problem?
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-06T16:36:06+00:00
- Post Title: need help with writing a extractor with QuickBMS

that problem you say just doesn't exist, for sure not with the script I wrote:

```
------------------------------
  000809a2 27648      00000000.dat
  00100f94 26624      00000001.dat
  00188926 28160      00000002.dat
  00205088 25600      00000003.dat
  002693d2 21504      00000004.dat
  002c62bc 20480      00000005.dat
  0032790e 21504      00000006.dat
  003a91c0 27136      00000007.dat
  00445762 31744      00000008.dat
  004cfc24 28672      00000009.dat
  0051dade 17408      0000000a.dat
  00574ea8 19456      0000000b.dat
  005bad9a 16384      0000000c.dat
  0066c544 35840      0000000d.dat
  006d091e 20992      0000000e.dat
  0072d9c0 20480      0000000f.dat
  0077967a 17408      00000010.dat
```
maybe download the latest version of quickbms in case you have an old one: [http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
## Post #9
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2010-02-07T00:28:37+00:00
- Post Title: need help with writing a extractor with QuickBMS

yes i'm using the latest version.

Here is my log with the sample file and script you gave me:

```
------------------------------
  00000000 27692      0.wav
  00000000 26668      1.wav
  00000000 28204      2.wav
  00000000 25644      3.wav
  00000000 21548      4.wav
  00000000 20524      5.wav
  00000000 21548      6.wav
  00000000 27180      7.wav
  00000000 31788      8.wav
  00000000 28716      9.wav
  00000000 17452      10.wav
  00000000 19500      11.wav
  00000000 16428      12.wav
  00000000 35884      13.wav
  00000000 21036      14.wav
  00000000 20524      15.wav
  00000000 17452      16.wav

- 17 files found in 1 seconds
```


you see, its always offset 00000000
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-02-07T00:30:39+00:00
- Post Title: need help with writing a extractor with QuickBMS

what is your version of quickbms post the output from the dos window.
## Post #11
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2010-02-07T00:55:12+00:00
- Post Title: need help with writing a extractor with QuickBMS

here:

```
act\wav"

QuickBMS generic files extractor 0.3.14b
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- open input file miku_sample.ddb
- open script ddb2wav.bms
- set output folder D:\projekte\DDB_extract\wav

  offset   filesize   filename
------------------------------
  00000000 27692      0.wav
  00000000 26668      1.wav
  00000000 28204      2.wav
  00000000 25644      3.wav
  00000000 21548      4.wav
  00000000 20524      5.wav
  00000000 21548      6.wav
  00000000 27180      7.wav
  00000000 31788      8.wav
  00000000 28716      9.wav
  00000000 17452      10.wav
  00000000 19500      11.wav
  00000000 16428      12.wav
  00000000 35884      13.wav
  00000000 21036      14.wav
  00000000 20524      15.wav
  00000000 17452      16.wav

- 17 files found in 0 seconds
```


quick update:
it seems this is a bug in the raw2wav function, it always takes the FIRST file to create the wav files.
The raw (.dat) files are correct when i uncomment this line:
    
```
log "" OFFSET SIZE # simple dumping till here, the rest is raw2wav
```
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-07T07:45:19+00:00
- Post Title: need help with writing a extractor with QuickBMS

uhmmm, try to move the first "append" command after the log operation (invert their positions).
I have edited the previous script in case of problems

P.S.: the offset 00000000 is correct because it's the offset relative to the memory file where are temporary saved the files before the dumping on the disk
## Post #13
- Username: Haro
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Jul 29, 2009 1:14 am
- Post datetime: 2010-02-07T10:49:12+00:00
- Post Title: need help with writing a extractor with QuickBMS

thank you, now it works as it should!!
