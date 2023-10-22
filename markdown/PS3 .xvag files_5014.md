## Post #1
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-09-12T10:35:17+00:00
- Post Title: PS3 .xvag files

Header: XVAG

example:


Need decoder or converter.

one .xvag file from uncharted drake`s fortune.
[423_MonasteryCombat1_ENDTAG3.rar](https://xentaxbackup.github.io/file/3435_423_MonasteryCombat1_ENDTAG3.rar)
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-12T11:41:53+00:00
- Post Title: PS3 .xvag files

Try the latest vgmstream.

[http://hcs64.com/files/vgmstream/vgmstr ... 6-test.zip](http://hcs64.com/files/vgmstream/vgmstream-r846-test.zip)
## Post #3
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-09-12T12:21:39+00:00
- Post Title: PS3 .xvag files

Works.
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2011-02-10T09:55:53+00:00
- Post Title: PS3 .xvag files

It's any way/tool to reconvert again the wav to xvag?
## Post #5
- Username: stephanehl
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Dec 20, 2008 2:25 am
- Post datetime: 2011-04-25T15:09:37+00:00
- Post Title: PS3 .xvag files

Please i need help. I want to rip all god of wars 3 movies but it audio is in xvag but i cant use vgmstream. It dont works.

Any Help.
## Post #6
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2011-04-25T18:52:57+00:00
- Post Title: PS3 .xvag files

> Reply from stephanehl
>
> Please i need help. I want to rip all god of wars 3 movies but it audio is in xvag but i cant use vgmstream. It dont works.

Any Help.

vgmstream needs some external .dll files.  Check the readme for download location and installation instructions.
## Post #7
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-09T09:16:21+00:00
- Post Title: PS3 .xvag files

Hi 

it's work's for me with xvag header but i have .dat file get vag header not working 

any idea please thank's

another trouble more important i get multichanel file not readable i can add cmd ligne ? maybie
## Post #8
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-06-08T13:25:52+00:00
- Post Title: PS3 .xvag files

Found a little problem - in some games .xvag is mp3s, but with pieces, which need deinterlave or delete. (but program, which I try, detect 2 channels only, dont know this real 2 channels or not)

I try use AlphaTwentyThree script - [viewtopic.php?f=13&p=39344#p39344](http://forum.xentax.com/viewtopic.php?f=13&p=39344#p39344) - but, I cant set right parameters for it and dont understand how change RES parameter in script.

Files for testing can be send throught PM.
## Post #9
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-06-11T20:39:38+00:00
- Post Title: PS3 .xvag files

Little explanation - I dont know method for deinterlave xvag files, so if anyone knows how it did, will be very thanksful.
## Post #10
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-06-15T18:08:37+00:00
- Post Title: PS3 .xvag files

Found one way to deinterlave .xvag files:
Source - [viewtopic.php?f=17&t=8569](http://forum.xentax.com/viewtopic.php?f=17&t=8569)

> First, you need to find out the distance between each FFFB flag.
>
> Then take that number and just keep multiplying it by 1, 2, 3 in a hex calculator until you find the correct interleave.
>
> For example, let's say the distance between two FFFB flags is 0x300 or 768 bytes
>
> 
>
> 300 x 1 = 300
>
> 300 x 2 = 600
>
> 300 x 3 = 900
About interleave value finding:

> Well, initially I just kept guessing and trying every number by adding or subtracting 0x300 to the number that didn't work (I started at 3000). But I just figured out an easier way. Keep looking at the contents of every frame (what's in between the FFFB values) and notice any patterns (usually, in the beginning, it's one repeated ascii character). Keep counting the frames, and when you see the pattern change, remember the number of that frame. Convert that number to hex, then multiply 0x300 by that number. (Here's a hex calculator: http://www.squarebox.co.uk/hcalc.html) So if the number you counted was 16, the interleave would be 3000. If you get it wrong, try adding 0x300 or subtracting 0x300. If it still doesn't work, look at the patterns more carefully.
>
> 
>
> Oh, and btw, the frame value is the address of the character that's before the first frame (for example, if the first frame starts with 11 00 FF FB D4, the frame value would be the address of the 00)

Works with The Last of Us:
header - 133, interleave - 3000, layers - 2

So as the game has much music files (over 558), audio batch tool which can split two stereo files in one stereo file with saving original audio data(256, 2, 48000) is very actual. I try to find, but without success.
## Post #11
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-06-16T07:09:45+00:00
- Post Title: PS3 .xvag files

You will need:

A hex editor of your choice
[QuickBMS](http://aluigi.altervista.org/quickbms.htm)
[AlphaTwentyThree's Deinterleave Script](http://forum.xentax.com/viewtopic.php?f=13&p=78284#p78284)
[VGMStream](http://hcs64.com/files/vgmstream/)
[VGMStream's External DLLs](http://hcs64.com/files/vgmstream_external_dlls.zip)


Run your hex editor, and open up the XVAG file you wish to deinterleave.

The size of the header can be found at offset 0x06.

 

The picture below shows the header highlighted



In this example shown, the header size is 0x1B4. Not all XVAG files have the same header size. But you can usually work out the header just by looking at it. The header ends when the first MPEG flag (FF FB) is shown.

I think the header size varies depending on how many channels the file has.

Most 4 channel files have a header of 0x134, 6 channel files usually have a header of 0x154, 8 channels usually have a header size of 0x174, 10 channels usually have a header size of 0x194 and 12 channels (like the picture shown above) usually have a header size of 0x1B4. It seems to increment an additional 0x20 bytes for every additional two channels above 4.

After you have identified the size of the header, edit the deinterleave script to match. So in this example from the picture posted above the script would look like:

```
set HEADER 0x1B4 # zero if skip is at end of block, otherwise = first skip at start
```


Now we have to work out the size of a single interleave block.

To work out the size of a single interleave block:

1. Go to the very end of the file in your hex editor. It should be a block of 00s

(NOTE: If there is no block of 00s and just a block of FFs, instead calculate the BLOCKSIZE by working out how many bytes are inbetween each MPEG flag (FF FB) starting just after the header and then keep multiplying it by 1, 2, 3 and adjusting the script until you get the correct interleave. The first two bytes after the header should be FF FB)





2. Select and highlight all of the data from the last 00 in the file all the way up until you reach another block of 00s (Your highlighted data should start with FF FB and end with the last 00 of the file) then copy and paste this into a new file in your hex editor.





3. Scroll down to the bottom of the newly created file and click after the final 00. The offset number given (highlighted in the red box) will represent a single interleave block for that file.



This will give you the INTSIZE for AlphaTwentyThree's script to successfully deinterleave the file.

From the example picture shown above, the INTSIZE is 2700 so now we add that number to the script:

```
set INTSIZE 0x2700 # size of one single interleave block. Set Blocksize to zero to take this value instead.
```


NOTE: If the XVAG file block you have does not end on a round number, then use the exact offset of the single interleave block.


Now we have to work out how many layers the file has. This can be done two different ways. The first is to look at the header of the file and determine how many channels the file uses and then divide that number by two. You can usually find the number of channels at offset 0x2B.



In this example shown above, we’re given the hex number “0C” which when converted from hex to decimal becomes 12. Then we divide 12 by 2 and get 6.

Or you can go to the very end of the file, scroll up and count how many blocks of 00s there are. The number you are given is the number of layers the file has which in this example gives me 6 separate blocks of 00s.

Depending on which method you choose, after you have found the number of layers, edit the script to match it. For this example, I am setting it to 6.

```
set LAYERS 6
```


After all that, this is what the options in the BMS script looks like.

```
set PRESERVE 1
set ADJUST 0
set BLOCKSIZE 0 # size of one complete block
set INTSIZE 0x2700 # size of one single interleave block. Set Blocksize to zero to take this value instead.
set LAYERS 6
set SKIP 0 # area at start of each block to skip
```


Then run QuickBMS, select the file deinterleave script, choose the XVAG file you wish to deinterleave and then select an output directory.

After the script has finished, use VGMStream's test.exe to convert the deinterleaved XVAGs to WAV.
## Post #12
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-06-16T08:59:00+00:00
- Post Title: PS3 .xvag files

I try your method, but I dont understand how need modify AlphaTwentyThree's script for work:
Then I just start it:

```
set PRESERVE 1
set ADJUST 0
set BLOCKSIZE 0 # size of one complete block
set INTSIZE 0x1800 # size of one single interleave block. Set Blocksize to zero to take this value instead.
set LAYERS 2
set SKIP 0 # area at start of each block to skip
```

I get 0 byte files.
I get also with it:

```
set PRESERVE 1
set ADJUST 0
set BLOCKSIZE 0 # size of one complete block
set INTSIZE 0x1800 # size of one single interleave block. Set Blocksize to zero to take this value instead.
set LAYERS 2
set SKIP 0 # area at start of each block to skip
set JUMP INTERL
math JUMP *= LAYERS # JUMP = size of one block
math INTERL -= SKIP
   get TEST asize
   math TEST %= LAYERS
   if TEST != 0
      print "Illegal deinterleave parameters! Aborting..."
      cleanexit
   endif
get CYCLES asize
math CYCLES /= JUMP # number of interleave blocks
get RES asize
math RES %= JUMP # size of last interleave block
#print "residuum: %RES%"
math RES /= LAYERS # size of single last interleave

if RES != 0
   print "Warning: last block is incomplete! Check your parameters!"
endif


for i = 1 <= LAYERS
   log MEMORY_FILE 0 0
   set OFFSET i
   math OFFSET -= 1
   math OFFSET *= INTERL
   math OFFSET += HEADER
   append
   for k = 1 <= CYCLES
      log MEMORY_FILE OFFSET INTERL
      math OFFSET += JUMP
      math OFFET += SKIP
   NEXT k
   if RES != 0 # incomplete but valid last block
      set OFF i
      math OFF -= 1
      math OFF *= RES
      math OFFSET -= JUMP
      math OFFSET -= SKIP
      math OFFSET += OFF
      log MEMORY_FILE OFFSET RES
   endif
   append
   get SIZE asize MEMORY_FILE
   get NAME basename
   if LAYERS != 1
      string NAME += "_"
      string NAME += i
   endif
   log NAME 0 SIZE MEMORY_FILE
next i
```


And then I just put values of header and interleave block(layers I dont change) I got clicks and other undecoded things.
## Post #13
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-06-16T16:09:34+00:00
- Post Title: PS3 .xvag files

Can you upload a sample of the file so I can take a look at it?
## Post #14
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2013-06-17T08:57:32+00:00
- Post Title: PS3 .xvag files

Modified Alpha's deinterlave script, which works without problems(thanks to brendan19):

```
# (c) 2012-09-05 by AlphaTwentyThree of XeNTaX

# notes:
# HEADER - area which is untouched by the deinterleaving
# PRESERVE 0/1   -   set to 1 to write the skipped area from
#                  HEADER to each deinterleaved file
# ADJUST 0/1    -    if the header needs to be adjusted, set
#                    this to 1 and write your code to the function
#                    "adjustheader" at the end of this script
# BLOCKSIZE    -   size of one complete interleave block
# INTSIZE          -       size of a single interleave block (set blocksize to zero to take this value)
# LAYERS      -   the numbers of (equal-sized) files you want
#               to deinterleave to
# SKIP         -   number of bytes to skip at the start of each block
#
# examples:
# split channels of stereo wave file: # HEADER 0x2c, PRESERVE 1, ADJUST 1 (adjust function), BLOCKSIZE 4, LAYERS 2, SKIP 0
# leave out 2 bytes each 0x10 bytes: # BLOCKSIZE 0x10, LAYERS 1, SKIP 2
# split channels of Playstation ADPCM file: # HEADER 0x2c, PRESERVE 1, ADJUST 1 (adjust function), BLOCKSIZE 2*Interleave, SKIP 0

set HEADER 0x1B4 # zero if skip is at end of block, otherwise = first skip at start
set PRESERVE 1
set ADJUST 0
set BLOCKSIZE 0 # size of one complete block
set INTSIZE 0x2700 # size of one single interleave block. Set Blocksize to zero to take this value instead.
set LAYERS 6
set SKIP 0 # area at start of each block to skip

if BLOCKSIZE == 0
   set BLOCKSIZE INTSIZE
   math BLOCKSIZE *= LAYERS
   math BLOCKSIZE += SKIP
endif

callfunction testparameters 1
get EXT extension
set WSIZE BLOCKSIZE
math WSIZE -= SKIP
math WSIZE /= LAYERS # data to write: (BLOCKSIZE - SKIP)/LAYERS
get CYCLES asize
math CYCLES -= HEADER
math CYCLES /= BLOCKSIZE

if LAYERS == 1
   callfunction desingle # for faster running time
else
   callfunction demulti
endif

startfunction testparameters
   # test 1: (BLOCKSIZE-SKIP)/LAYERS must be integer (one block must be dividable into skip and layers)
   set TEST BLOCKSIZE
   math TEST -= SKIP
   math TEST %= LAYERS # single layer -> always ok
   if TEST != 0
      print "Error: blocksize minus skip isn't dividable by layer count! Aborting..."
      cleanexit
   endif
   
   # test 2: (ASIZE-HEADER)/BLOCKSIZE must be integer (no incomplete blocks at end)
   get TEST asize
   math TEST -= HEADER
   math TEST %= BLOCKSIZE
   if TEST != 0
      print "Error: file size minus header isn't dividable by blocksize! Aborting..."
      cleanexit
   endif
   
   # test 3: ASIZE-HEADER-BLOCKSIZE must be greater null (at least one deinterleave cycle)
   get TEST asize
   math TEST -= HEADER
   math TEST -= BLOCKSIZE
   if FSIZE <= 0
      print "Error: file too small to deinterleave! Aborting..."
      cleanexit
   endif
endfunction

      
startfunction desingle
   set PSIZE CYCLES
   math PSIZE *= WSIZE
   get NAME basename
   string NAME += ".stripped"
   if PRESERVE == 1
      math PSIZE += HEADER
      string NAME += "."
      string NAME += EXT
   endif
   putVarChr MEMORY_FILE PSIZE 0
   log MEMORY_FILE 0 0
   if PRESERVE == 1
      goto 0
      getDstring HDATA HEADER
      putDstring HDATA HEADER MEMORY_FILE
   endif
   goto HEADER
   for i = 1 <= CYCLES
      getDstring DUMMY SKIP
      getDstring WDATA WSIZE
      putDstring WDATA WSIZE MEMORY_FILE
      math OFFSET += WSIZE # set OFFSET to current cursor (WDATA + SKIP = BLOCKSIZE)
   next i
   get SIZE asize MEMORY_FILE
   if ADJUST == 1
      callfunction adjustheader 1
   endif
   log NAME 0 SIZE MEMORY_FILE
endfunction
   
startfunction demulti
   set PSIZE CYCLES
   math PSIZE *= WSIZE
   if PRESERVE == 1
      math PSIZE += HEADER
      goto 0
      getDstring HDATA HEADER
   endif
   for i = 1 <= LAYERS
      putVarChr MEMORY_FILE PSIZE 0
      log MEMORY_FILE 0 0
      get NAME basename
      string NAME += "_"
      string NAME += i
      if PRESERVE == 1
         putDstring HDATA HEADER MEMORY_FILE
         string NAME += "."
         string NAME += EXT
      endif
      set BIAS_A i
      math BIAS_A -= 1
      math BIAS_A *= WSIZE
      math BIAS_A += SKIP # bias at start
      set BIAS_B BLOCKSIZE
      math BIAS_B -= BIAS_A
      math BIAS_B -= WSIZE # bias at end
      goto HEADER
      for k = 1 <= CYCLES
         getDstring DUMMY BIAS_A
         getDstring WDATA WSIZE
         putDstring WDATA WSIZE MEMORY_FILE
         getDstring DUMMY BIAS_B
      next k
      get SIZE asize MEMORY_FILE
      if ADJUST == 1
         callfunction adjustheader 1
      endif
      log NAME 0 SIZE MEMORY_FILE
   next i
endfunction

startfunction adjustheader # adjust this according to your needs
   putVarChr MEMORY_FILE 4 1 long
   get SSIZE asize MEMORY_FILE
   math SSIZE -= HEADER
   putVarChr MEMORY_FILE 0x10 SSIZE long
endfunction
```


Batch tool for aumatic splitting two or more WAV\MP3(256, stereo, 48000) into one(explanation - result must have, for example, 3:04 time as two source files, and not 6:08) is actual yet.
## Post #15
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-06-18T10:05:13+00:00
- Post Title: PS3 .xvag files

he say me files size get minus header isn't divisable by blocksize
i must use one another script before
## Post #16
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-06-18T22:43:52+00:00
- Post Title: Re: PS3 .xvag files

Kilik, PM me a file and I'll help you out
## Post #17
- Username: !!!!!
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 22, 2009 8:55 am
- Post datetime: 2013-06-27T10:28:56+00:00
- Post Title: Re: PS3 .xvag files

> Reply from brendan19
>
> tutorial
Very helpful tutorial Brendan. All that's left is to iron out the tedious process of finding the values via hex editor each file and make a bms script out of it.
## Post #18
- Username: clayman
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 27, 2006 7:26 am
- Post datetime: 2013-07-21T20:16:18+00:00
- Post Title: Re: PS3 .xvag files

Does QuickBms even allow being called on singular files instead of directories? I have spent an afternoon/evening today working on a few scripts that would let me automate the conversion process with correctly determining interleave size for each file but when I call quickbms on each file separately, I end up with a bunch of files 308 bytes long.

I might have a bug in the scripts as I have not yet had time to debug them thoroughly but I cannot think of any atm and this looks strange.
## Post #19
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-07-22T00:26:26+00:00
- Post Title: Re: PS3 .xvag files

If you PM aluigi and ask him nicely, he will be able to tell you
## Post #20
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-08-08T00:57:46+00:00
- Post Title: Re: PS3 .xvag files

I slightly tweaked my tutorial on finding the INTSIZE
## Post #21
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-13T06:41:32+00:00
- Post Title: Re: PS3 .xvag files

[https://dl.dropboxusercontent.com/u/107 ... 284%29.dat](https://dl.dropboxusercontent.com/u/10798900/DUMPBOX/streaming_sound%20%284%29.dat)

can someone take a look at this file it has the same structure however couldn't get it to work
## Post #22
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-09-13T19:06:11+00:00
- Post Title: Re: PS3 .xvag files

Rename the extension from .DAT to .xvag and play with VGMStream
## Post #23
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-20T10:40:04+00:00
- Post Title: Re: PS3 .xvag files

> Reply from brendan19
>
> Rename the extension from .DAT to .xvag and play with VGMStream
yeah it fails to open stream
## Post #24
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2013-09-21T01:28:47+00:00
- Post Title: Re: PS3 .xvag files

Are you using the latest version of [vgmstream](http://hcs64.com/files/vgmstream/vgmstream-r1013-test.zip)?

Because all I did was rename the extension and it played it back fine as it is only 2 channels.
## Post #25
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-09-21T09:36:17+00:00
- Post Title: Re: PS3 .xvag files

> Reply from brendan19
>
> Are you using the latest version of vgmstream?

Because all I did was rename the extension and it played it back fine as it is only 2 channels.

ah that did the trick ty
## Post #26
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2013-11-22T10:28:42+00:00
- Post Title: Re: PS3 .xvag files

Someone managed to recreate the xvag with modified files?
