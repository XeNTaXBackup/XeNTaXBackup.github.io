## Post #1
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-04-02T14:45:47+00:00
- Post Title: Sanitarium audio files (.005 to .017)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-04-16T11:01:10+00:00
- Post Title: Sanitarium audio files (.005 to .017)

You can also use Nova Extractor or my WAVEscan.bms. The below script works for all archives with uncompressed wave files that have a "WAVEfmt" section. Hm, I'm actually thinking about expanding the script with other file formats - isn't too hard and a good exercise in quickBMS 

```
get EXT extension
string BASE += "_"
string BASE += EXT
string BASE += "_"

for i = 1
   FindLoc OFFSET STRING "WAVEfmt" 0 ""
   if OFFSET != ""
      math OFFSET -= 8
      goto OFFSET
      FindLoc DATA STRING "data" 0 ""
      math DATA += 4
      goto DATA
      get SSIZE long
      savepos HEADER
      math HEADER -= OFFSET
      set SIZE HEADER
      math SIZE += SSIZE
      set NAME BASE
      string NAME += i
      string NAME += ".wav"
      log NAME OFFSET SIZE
   else
      cleanexit
   endif
next i
```
## Post #3
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2010-04-19T16:34:11+00:00
- Post Title: Sanitarium audio files (.005 to .017)

I'm not tying to be rude or anything, but isn't your script perhaps a little redundant?
Specifying a filenumber isn't at all necessary unless making use or more than 1 file within the script, as filenumber "0" is associated by default. 
Also, the "else" command isn't necessary here either, given that in the 'else' circumstance; you've told the script to exit, whereas the script will return "0 files found" (end exit) if the "findloc" command cannot locate the particular string in reference (in other words: whether you state "cleanexit", or not you'll obtain precisely the same outcome).

And the efficient thing about the RIFF-container format is the total size (short of 8 bytes) is actually stated in the header. So, you can narrow what would have otherwise been a somewhat overly-complex script down to something along the lines of this:

```
string NAME += ".wav"
findloc OFFSET string "RIFF"
goto OFFSET
idstring "RIFF"
get SIZE long
math SIZE += 8

log NAME OFFSET SIZE

```


I hope this is helpful in some way
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-04-20T14:50:42+00:00
- Post Title: Sanitarium audio files (.005 to .017)

You're not rude but let me in return note the following: 
Your script...
a) only detects the first wave file inside any container (!!!) - my script also numbers single files, but what's more efficient: having all files but one disregarded or a little number to delete manually for those containers that only contain one wave file?
b) will try to extract any data that has a "RIFF" in it, no matter if it's really a WAVE file or not - thus it will probably crash for all files that randomly contain a "RIFF" string (as the next 4 bytes only contain random data but no data size). I've encountered lots of files that contained let's say 15 wave files but showed the "RIFF" string more often.
Re-read my above post and think again. 

P.S.: Tell me which commands are residual so I could slim down the script a bit. Apart from the else and cleanexit.
