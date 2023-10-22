## Post #1
- Username: Zazz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 25, 2010 2:39 pm
- Post datetime: 2010-05-26T02:51:37+00:00
- Post Title: Vexx archives - A return to .TRE files (Turok Evolution)

Hello everyone,

Just found this site today, and it's been quite a fruitful day!

I am currently working on the Acclaim game Vexx on the GameCube system. Its disc architecture is very similar to that of Turok Evolution (based upon what was reported here last year: [viewtopic.php?f=10&t=3881&p=33441](http://forum.xentax.com/viewtopic.php?f=10&t=3881&p=33441) ), in that almost all of the game's data is locked up in one Supertree0.tre cabinet file.

Not surprisingly, the .tre file follows the same protocol with regards to its header:

[NUM_FILES long] [offset long, size long, unk long, unk long] x 4213 total files

So the script documented in the Turok Evolution thread worked and was able to extract all 4213 files. The two unknown longs do not confer any information regarding file names, which is a pain in the rear across 4200-some files.

However, the second file in the .tre archive after the header, called tempfiles.txt, contains a list of every filename in the archive, and, surprisingly, in the order of appearance! But the offset/size pairs in the header are in a seemingly random order. This calls for a sort operation if we are to have properly named/placed files be output. Since the files are ordered in tempfiles.txt, as a temporary solution I chose to name the files by their offset, let Windows sort them by name and establish the name correlation. But manually changing 4213 file names isn't fun!

```

Get NUM_FILES long

For I = 0 < NUM_FILES
   # File info
   Get OFFSET long
   Get SIZE long
   Get UNK long
   Get UNK long

   # Extract file
   Log OFFSET OFFSET SIZE
Next I

```


Now, my question to you guys is, how would I optimize the code so that the sort process is incorporated into the BMS script (running on quickbms)? The problem I encounter is the lack of versatility in both reading and appending secondary files using BMS scripts (granted, their primary role is to dump files from the file 0 archive, not manipulate temp files). Can the Log function output just variables into a temp file, instead of chunks of file 0? Or would it be better to break the script action into an offset script, a .BAT sort, then a dump script? It'd be nice to get the whole thing to work in one double-click though.

Here is some pseudocode:

```

Log TEMPORARY_FILE 0 0
Append
#append on

Get NUM_FILES long 0

For I = 0 < NUM_FILES
   # Walk through all 4213 files' offsets and save them to temp
   SavePos CurrentOffset 0
   Get OFFSET long 0
   Get SIZE long 0
   Get UNK long 0
   Get UNK long 0

   # Save the two OFFSET/SIZE longs to temp file for later sorting
   Log TEMPORARY_FILE CurrentOffset 0x8
Next I

Open "." TEMPORARY_FILE 1
# sort offsets/sizes so lowest offset appears first, corresponding to the correct order of files in the .tre archive
# sort code goes here

Append
#append off

#with the offsets sorted, dump files in order appearing in TEMPORARY_FILE, using the filenames after finding the tempfiles.txt offset
#locate tempfiles.txt offset

GoTo 0x0 0
FindLoc nameOffset string "C:\VexxDataGC_TreFiles" 0 ""
If nameOffset == ""
   Clean Exit
EndIf
GoTo nameOffset 0
#nameOffset should be 0x00012473, the start of the tempfiles.txt file

GoTo 0x0 1
For I = 0 < NUM_FILES
   Get OFFSET long 1
   Get SIZE long 1
#step through the tempfiles.txt file, extracting the string for the folder\file.ext structure
#not a null-terminated string, will need a bit of coding and an iterative step to cleave off C:\VexxDataGC_TreFiles which precedes every file
   GetDString NAME NAME_LENGTH 0
   Log NAME OFFSET SIZE 0
Next I
```


PS. As a side note, there seems to be some encryption of various texture files, most of appear to be in the targa format .TGAX and some modified bitmap files .BMPX... Also there are other .tre files within the Supertree0.tre file, most notably containing the (playable!) .DSP music files, but no helpful tempfiles.txt file (and there's >10000 files in that secondary music .tre file!).
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-26T10:15:09+00:00
- Post Title: Vexx archives - A return to .TRE files (Turok Evolution)

it's necessary the upload of at least the first megabyte of the archive for having more info about this listfile.
the following is an idea of the script that probably doesn't work due to the missing info:

*edit* the script is in my next post
## Post #3
- Username: Zazz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 25, 2010 2:39 pm
- Post datetime: 2010-05-26T14:21:29+00:00
- Post Title: Vexx archives - A return to .TRE files (Turok Evolution)

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-26T18:24:46+00:00
- Post Title: Vexx archives - A return to .TRE files (Turok Evolution)

ah ok, the following script seems to do the job correctly, moreover because there was a bug in the previous one:

```
get FILES long
for i = 0 < FILES
   get OFFSET long
   get SIZE long
   get DUMMY long
   get DUMMY long
   putarray 0 i OFFSET
   putarray 1 i SIZE
next i

print "please wait, sorting in progress..."
for i = 0 < FILES
   getarray OFFSET1 0 i
   getarray SIZE1   1 i
   for j = i < FILES
      getarray OFFSET2 0 j
      if OFFSET2 < OFFSET1
         getarray SIZE2 1 j
         putarray 0 i OFFSET2
         putarray 1 i SIZE2
         putarray 0 j OFFSET1
         putarray 1 j SIZE1
         getarray OFFSET1 0 i
         getarray SIZE1   1 i
      endif
   next j
next i

findloc TEMPFILES string "C:\\VexxData" 0
for i = 0 < FILES
   getarray OFFSET 0 i
   if OFFSET == TEMPFILES
      getarray SIZE 1 i
      break
   endif
next i
if i >= FILES
   getarray OFFSET 0 1
   getarray SIZE 1 1
endif
log MEMORY_FILE OFFSET SIZE

for i = 0 < FILES
   get NAME line MEMORY_FILE
   getarray OFFSET 0 i
   getarray SIZE   1 i
   log NAME OFFSET SIZE
next i
```
## Post #5
- Username: Zazz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 25, 2010 2:39 pm
- Post datetime: 2010-05-26T19:56:40+00:00
- Post Title: Vexx archives - A return to .TRE files (Turok Evolution)

Yep, the final script works AOK, all of the file architecture is preserved. Great!
## Post #6
- Username: RinMaru
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 15, 2020 10:18 pm
- Post datetime: 2020-07-15T14:24:11+00:00
- Post Title: Vexx archives - A return to .TRE files (Turok Evolution)

Im currently working on the Xbox version to do a HD texture mod for Dolphin. Im pretty new to this but the file architecture in xbox is a little different then Gamecube because there is not 1 tre file but 3 of them. the first file "supertree0.tre extracts fine but supertree1 & supertree2 do not extract infact they just throw errors in BMS some help on this would be greatly appreciated
