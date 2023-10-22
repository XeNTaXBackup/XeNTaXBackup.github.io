## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-16T15:20:58+00:00
- Post Title: A taste of an experimental QuickBMS feature

I have worked on a new feature of QuickBMS that allows to create an automatic visual formatting of the extracted archive like a hex editor with "tags".

The feature is really very cool and at the moment I have worked on a HTML output but unfortunately HTML is not good for this type of job because consumes a lot of resources in the browser.

I have attached a generated html output of the extraction of fsbext.zip with my zip.bms script so let me know what you think.

just some notes:
- the colors are automatically generated
- exist better outputs but this one takes less resources and space and then it's perfectly compatible with any browser

features:
- if you stay with the mouse on one of the coloured blocks it will show the name of the variable that was used or the name of the extracted file
- you will see the offset of the block in the bottom of your browser (like htm:OFFSET)
- it can be applied to any file, MEMORY_FILEs included

I have in mind to create a GUI for this feature but I don't know if and when.
[test.zip](https://xentaxbackup.github.io/file/4340_test.zip)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-16T15:24:58+00:00
- Post Title: A taste of an experimental QuickBMS feature

screenshot:
[](http://img12.imageshack.us/i/testvh.png/)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-06-16T20:24:54+00:00
- Post Title: A taste of an experimental QuickBMS feature

Very cool indeed
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-17T13:24:06+00:00
- Post Title: A taste of an experimental QuickBMS feature

I have seen that implementing the majority of the commands used in WinHEX wasn't a big trouble so I did it and the following is the result obtained using this script with the reimport.lnk file of quickbms:
[http://www.x-ways.net/winhex/templates/ ... Record.tpl](http://www.x-ways.net/winhex/templates/LNK%20FILE%20Record.tpl)

[](http://img829.imageshack.us/i/lnkfiles.png/)

and the following is the debugging output automatically activated when using this type of tpl files:

```
    4c 00 00 00                                       L...
. 00000004 getdstr GUID       "☺¶☻" 16
    01 14 02 00 00 00 00 00 c0 00 00 00 00 00 00 46   ...............F
. 00000014 getdstr display flags "╗" 1
    bb                                                .
. 00000015 getbits D$         0x00000000 1
. 00000015 getbits RP         0x00000001 1
. 00000015 getbits WD         0x00000001 1
. 00000015 getbits CL         0x00000001 1
. 00000015 getbits CI         0x00000000 1
. 00000018 getdstr attributes " " 2
    20 00                                              .
. 0000001c get     Create Time 0xe7efedbb 8
. 00000024 get     Last Modified Time 0x89cffc09 8
. 0000002c get     Last Access Time 0x35fbe322 8
. 00000034 get     File Length 0x0029f600 4
. 00000038 get     Icon number 0x00000000 4
. 0000003c get     ShowWnd value 0x00000001 4
. 00000040 get     Hotkey     0x00000000 4
. 00000044 get     Always zero 0x00000000 8
. 0000004c get     Offset     0x0000007b 2
. 000000c9 get     File locator table length 0x00000045 4
. 000000cd get     Offset to end of table 0x0000001c 4
. 000000d2 getbits Network_flag 0x00000000 1
. 000000d1 getbits Local_flag 0x00000001 1
. 000000d5 get     Offset of local volume table 0x0000001c 4
. 000000d9 get     Offset of local pathname 0x00000034 4
. 000000dd get     Offset of network volume info 0x00000000 4
. 000000e1 get     Offset_extended_pathname 0x00000044 4
. 000000e5 get     Length of local volume table 0x00000018 4
. 000000e9 get     Volume type 0x00000003 4
. 000000ed get     Volume serial number 0x7c281cea 4
. 000000f1 get     Offset to volume label 0x00000010 4
. 000000f5 get     Volume Label "RAMDISK" -1
. 000000fd get     Local path "Z:\quickbms.exe" -1
. 0000010e get     Length_RelPath$ 0x0000000e 2
. 00000110 getdstr Relative Path String "." 28
    2e 00 5c 00 71 00 75 00 69 00 63 00 6b 00 62 00   ..\.q.u.i.c.k.b.
    6d 00 73 00 2e 00 65 00 78 00 65 00               m.s...e.x.e.
. 0000012c get     Length_WDPath$ 0x00000002 2
. 0000012e getdstr Working Directory String "." 4
    2e 00 5c 00                                       ..\.
. 00000132 get     Length_CMDLINE$ 0x00000005 2
. 00000134 getdstr Command Line String "-" 10
    2d 00 72 00 20 00 2d 00 77 00                     -.r. .-.w.
```
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-11T11:24:19+00:00
- Post Title: A taste of an experimental QuickBMS feature

in the recent quickbms version (0.5.4a) I have added a new experimental feature that "should" not affect the normal operations so my target is not introducing new problems.

in short I have added a particular type of memory management feature that adds a PAGE_GUARD memory page at the beginning and the end of each allocated memory:

```
result:
PGPG################PGPG
|   |               |
|   |               aligned 1024
|   buffer
real allocated memory
```
a page guard is like a warning (a crash in this case) happening everytime there is a read/write/execute access to that page guarded memory, so it should be not possible to go over/under the allocated buffer.

the positive effect is that if there is a bug in quickbms or in a script or in one of the various compression libraries used by the tool the user will receive a crash immediately and so it's possible to fix the tool/script without problems.
Indeed I introduced this method mainly to give a minimum of protection versus the external compression libraries used in quickbms, call it a "security" feature although not complete because it protects the contiguous buffer under/overflows in the heap only.
for the stack I use the -fstack-protector-all feature of gcc, but obviously this can't be applied to the dumped raw functions (like lz2k and so on)

anyway there are two downsides:
- will be used a bit more of memory, usually 8 kilobytes for each allocation
- the performances will be a bit lower in some conditions due to the continuous reallocations because it's not easy to reallocate memory, maybe I will improve this in the future

well I hope this sounds interesting and that will help to fix any possible problem in quickbms and the scripts.

ah, this feature works with both windows and linux.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-23T22:12:21+00:00
- Post Title: A taste of an experimental QuickBMS feature

another new feature in version 0.5.5:
possibility of calling external executables.

imagine to have a file compressed with the swizzle algorithm (it's only an example so don't consider this name!) but:
- it's not supported by quickbms
- there are no dll that do the job
- exists only a command-line tool called unswizzle.exe which maybe is only closed source
- you are too lazy to call that tool for each file manually

now for using this type of compression it's enough to specify the following in the script:
comtype EXECUTE "unswizzle.exe #INPUT# #OUTPUT#"

when you will call clog quickbms will automatically launch this unswizzle.exe tool and you see only the uncompressed file as you see normally.

#INPUT# and #OUTPUT# are fixed names that must be used in the place of the input filename requested by the called tool and the "optional" output one.
you can even use the variables:
comtype EXECUTE "mytool.exe -q -d -t %MYVAR% #INPUT# #OUTPUT#"
encryption EXECUTE "crypt.exe -d -k %MYKEY% #INPUT#"

I have already used this feature in a native way for kzip and works perfectly so now you can use it for any other command-line tool you desire.

for example do you want to automatically decompress all the jpg files in bmp?
now you can.

hope you like the idea but keep in mind that it poses some security risks so use ever and only trusted scripts.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-27T16:07:53+00:00
- Post Title: A taste of an experimental QuickBMS feature

released a new version in which I have improved (a lot) the performances of kzip.

instead of creating the input and output files on the disk I have opted for the usage of the named pipes.
named pipes are like fake files that can be read and write only in sequential mode so they don't have a size and a fseek.

anyway I have been able to bypass this limitation by placing the input filesize directly in the executable dumped all the times.

the result is very good and it's unbelievable how much fast it is when compared to the normal version that uses the files.
the reason is located in the fact that kzip.exe re-read the input file and re-create the output one many times because it acts like a brute forcer that stops only when it finds the smallest compressed file size.
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-09T23:28:28+00:00
- Post Title: A taste of an experimental QuickBMS feature

Dude, you totally ROCK!!! That feature with the external exe execution (xxx?  ) is extremely handy and will save me A LOT of time in the future. I'll definitely use this for my XMA script to work together with xma_parse (from HCS). Finally I can do "practically any xma variant" to "decodable xma file" in one swoop by including the parsing into the script!
I see that this XMA conversion is getting quite big considering all the input formats that it can already process (different RIFF and RIFX headers, *.SoundNodewave almost done, automatic cutting to unparsed xma streams for postprocessing etc.)
I have one question though: is it possible to perform the .exe operation "on-the-fly" by setting MEMORY_FILE as #OUTPUT#? It would be great to have that although I guess there could be problem with the memory pre-allocation. Maybe include some estimation variable that can be set to a multiple of the original file size?

Another thing regarding memory pre-allocation: I know that QuickBMS isn't designed for all file operations and it gets very apparent when interleaving files - it's extremely slow. Is that Windows or QuickBMS? For example, it occurs when I need to join channels. Input: two mono files, output: stereo file (in original audio formats of course). In many cases, the interleave is just 4 bytes and even for files with 2MB per channel it takes forever. Very striking: with increasing file size the time needed seems go increase exponentially. 
If you know an answer to this, a little explanation would be great.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-10T01:26:52+00:00
- Post Title: A taste of an experimental QuickBMS feature

the encryption/comtype EXECUTE mode is completely transparent so doesn't matter if you are operating on a real file or on a memory file or even on an input and an output memory file.

the following is an all-in-one example that demonstrates various things:

```
log MEMORY_FILE 0 SIZE
encryption EXECUTE "xmablah.exe -x #INPUT# #OUTPUT#"
log MEMORY_FILE 0 SIZE MEMORY_FILE
encryption "" ""
log "mydump.dat" 0 SIZE MEMORY_FILE
```
as you can see #INPUT# and #OUTPUT# are fixed because it's quickbms that manages them internally.

the EXECUTE command is available with both encryption and comtype for having the wider range of possibility of usage for any occasion.

the slowness of quickbms depends by various factors included also how the script is programmed.
if you have a loop executed tons of times (for example for a one-byte per time operation) obviously it will be very slow and then recently I added a security feature that probably has decreased the performances and introduced a little limitation.
regarding this security feature I would like to improve it in feature because it's technically cool but the continuos reallocations kill the performances... so work-in-progress.

do you have an example of these "join" scripts?
maybe it's possible to adopt an alternative solution to avoid the problem, for example a pre-allocation of the memory_file and the usage of putvarchr or something else.
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-10T03:16:58+00:00
- Post Title: A taste of an experimental QuickBMS feature

> Reply from aluigi
>
> do you have an example of these "join" scripts?
maybe it's possible to adopt an alternative solution to avoid the problem, for example a pre-allocation of the memory_file and the usage of putvarchr or something else.
sure: [viewtopic.php?f=13&p=61876#p61876](http://forum.xentax.com/viewtopic.php?f=13&p=61876#p61876)
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-10T22:09:41+00:00
- Post Title: A taste of an experimental QuickBMS feature

for that example you use a loop of "append/log" which obviously takes tons of resources.
maybe try the following modification of that piece.
from:

```
   append
   log MEMORY_FILE OFFSET 0x4 0
   log MEMORY_FILE OFFSET 0x4 1
   append
   math OFFSET += 0x4
while OFFSET < FSIZE
```
to:

```
math TMP *= 2
putvarchr MEMORY_FILE TMP 0
log MEMORY_FILE 0 0
append
do
   log MEMORY_FILE OFFSET 0x4 0
   log MEMORY_FILE OFFSET 0x4 1
   math OFFSET += 0x4
while OFFSET < FSIZE
append
```
with the previous versions of quickbms (till 0.5.4 included) you must have better performances for sure using this code.

the good news is that I'm working on the new allocation method trying to make it faster like the previous versions of the tool so stay tuned
## Post #12
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-11T12:15:13+00:00
- Post Title: A taste of an experimental QuickBMS feature

hey, thanks, didn't know it was actually that easy to preallocate memory. 
Erm, shouldn't the putVarChr and log command be the other way round, i.e. first clear memory, then put the temp variable there?
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-11T13:57:03+00:00
- Post Title: A taste of an experimental QuickBMS feature

the putvarchr command tells quickbms to pre-allocate memory and so setting the total size of the MEMORY_FILE to that size.
the log one instead reset the status of the MEMORY_FILE leaving its total allocated size intact and so avoiding the continuous reallocations.

the good news is that my work on the optimized memory management is almost finished and so the performances will return to those of the <= 0.5.4 version.
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-11T14:56:08+00:00
- Post Title: A taste of an experimental QuickBMS feature

cool, I have just made a quick test versus version 0.5.4 (the old one without the slow secure allocation method) using the following script:

```
putvarchr MEMORY_FILE SIZE 0
log MEMORY_FILE 0 0
for i = 0 < SIZE
    putvarchr MEMORY_FILE i 0x61
next i
```
and the result is that the new version that I'm going to release today or tomorrow does the job in 5 seconds while quickbms 0.5.4 needs 41 seconds :)

obviously there is no challenge at all with the current quickbms (0.5.6d) which takes minutes and so it's completely out.

good, I think I have nothing else to add so I guess I will release the new version just today.
## Post #15
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-11T22:45:22+00:00
- Post Title: A taste of an experimental QuickBMS feature

sounds really great! =)
looking forward to working with the new release!
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-12T11:00:46+00:00
- Post Title: Re: A taste of an experimental QuickBMS feature

just released.
let me know if now it's a bit faster.
## Post #17
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-15T15:09:19+00:00
- Post Title: Re: A taste of an experimental QuickBMS feature

It's a bit faster, yes.  But it's still really slow and I don't really know why. Could you take a look at my script? Here: [viewtopic.php?f=13&t=4450&p=40773#p40773](http://forum.xentax.com/viewtopic.php?f=13&t=4450&p=40773#p40773)
I tried to pre-allocate the sizes with an array but all I get is an error message that the array is too big:

```
	PutArray 0 i 0
next i
get FSIZE asize
set OFFSET 0
DO
	set IDENT OFFSET
	math IDENT += 0x11
	goto IDENT
	get STREAM byte
	getArray TMP 0 STREAM
	math TMP += 0x930
	putArray 0 STREAM TMP
	math OFFSET += 0x930
WHILE OFFSET < FSIZE
```

I need this complete run-through because there is no way to tell where the layer parts are located. STREAMS has 4 as maximum value, so it should be just a 1x4 matrix.
## Post #18
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-15T16:33:15+00:00
- Post Title: Re: A taste of an experimental QuickBMS feature

UPDATE: the long running time is definitely my script. Just tested the new QuickBMS with my deinterleave script and it really is a lot faster! Thanks for this update Luigi!
## Post #19
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-15T16:47:32+00:00
- Post Title: Re: A taste of an experimental QuickBMS feature

it's enough that you specify only the latest value so the following:

```
   PutArray 0 i 0
next i
```
can be simply replaced by:

```
PutArray 0 STREAMS 0
```
## Post #20
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-15T17:16:30+00:00
- Post Title: Re: A taste of an experimental QuickBMS feature

Apparently there's something wrong with my script. But thanks for the hint.
## Post #21
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-03-02T11:19:35+00:00
- Post Title: Re: A taste of an experimental QuickBMS feature

other improvements and fixes of the secure allocation feature.
it's too cool to abandon it even if there are some limitations that rarely can affect quickbms users.
more info here:
[viewtopic.php?p=68373#p68373](http://forum.xentax.com/viewtopic.php?p=68373#p68373)
