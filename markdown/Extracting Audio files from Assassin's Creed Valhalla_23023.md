## Post #1
- Username: Karimmusa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 19, 2020 5:04 am
- Post datetime: 2020-11-18T22:38:43+00:00
- Post Title: Extracting Audio files from Assassin's Creed Valhalla

Hey guys, 
I've been trying for atleast two days with this game and I can't for the life of me convert the files extracted from the pck file
So I extracted the music for Assassin's Creed Origins simply by using WWise unpacker and it worked like a charm.

For this game it's a pck file and when extracting the files I'm met with .WAV files 
so for the music.pck file it gives me 691 file, only 122 get converted by wwise to ogg files.
The rest of the files are simply not convertable WAV files.
I either get 
Parse error: expected 0x42 fmt if vorb Messing
or
parse error: unknown chunk type
Depending on the tool

I tried using a wwise_ima_adpcm tool but I cannot seem to convert the files to wem in the first place
Here are some sample files

[https://mega.nz/fm/R2hTxIBI](https://mega.nz/fm/R2hTxIBI)
Can anyone atleast confirm if they are corrupted files or something? 

Anyone can help with this please? 
Thanks in advance
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2020-11-20T15:30:16+00:00
- Post Title: Extracting Audio files from Assassin's Creed Valhalla

You haven't included the decryption key for the MEGA folder.
## Post #3
- Username: Karimmusa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 19, 2020 5:04 am
- Post datetime: 2020-11-20T15:56:51+00:00
- Post Title: Extracting Audio files from Assassin's Creed Valhalla

Sorry about that
I've uploaded the original PCK file to Gdrive, can you help me with that?
[https://bit.ly/3kQnNQd](https://bit.ly/3kQnNQd)
## Post #4
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2020-11-20T17:24:22+00:00
- Post Title: Extracting Audio files from Assassin's Creed Valhalla

QuickBMS Script:
```
# RIFF and RIFX header supported
# note: There are wave files with a wrong file size after RIFF/RIFX
#       This script takes the stream size, adds the header size and writes the correct size after RIFF/RIFX
# (c) 2012-06-26 by AlphaTwentyThree
#
# future update plans:
# - option to also write data between found wave files to disk
# - option to automatically transform the file to a playable or at least decodable format

for i = 1                        # run through loop with count variable i
   FindLoc OFFSET string "WAVE" 0 ""   # search for "WAVE", save position as variable OFFSET
   if OFFSET == ""                  # when nothing is found
      cleanexit                  # the script exits (e.g. at end of file)
   endif
   math OFFSET -= 8               # jump to possible
   goto OFFSET                     # RIFF/RIFX file start
   getDstring IDENT 4               # read string of 4 bytes, save variable as IDENT
   if IDENT == "RIFX"               # differentiate between header possibilities
      endian big                  # set endianness to big, if file has RIFX identifier
      callfunction write 1         # see function section below
   elif IDENT == "RIFF"            # endianness stays little
      callfunction write 1         # also run function
   else                        # string "WAVE" found, but doesn't belong to wave file
      set SIZE 0xc               # do as if something with 0xc bytes was found to continue search from the right position
   endif
   set SEARCH OFFSET               # set marker to position from where to search next
   math SEARCH += SIZE               # (that would be after the file that was found)
   if SEARCH == FSIZE               # in case the last found file ends with the main file, we exit
      cleanexit
   endif
   goto SEARCH                     # if we haven't exited the script above, we set out cursor to after the last found file
next i

startfunction write                  # function "write" starts here, is called when a wave file is found above
   get NAME basename               # save name without extension under variable NAME
   string NAME += "_"               # add underscore to the name
   string NAME += i               # add the loop variable to the name
   goto OFFSET                     # set cursor to the beginning of the found file
   get DUMMY long                  # RIFF/RIFX identifier, not needed
   get DUMMY long                  # riff size, not needed
   get DUMMY long                  # "WAVE", not needed, we arrive at the "fmt " section
   for                           # loop search for the "data" section at the start of the stream (get the stream size from there)
      getDstring AREA_NAME 4         # name of area in header
      get AREA_SIZE long            # size of area in header
      savepos MYOFF               # save position we are at
      if AREA_NAME == "data"         # when we arrive at the needed "data" area:
         break                  # we exit the loop
      else                     # otherwise:
         if AREA_NAME == "LIST"      # that's the area of the marker names
            callfunction retrievename 1 # see below
         endif
         math MYOFF += AREA_SIZE      # not reached "data" area -> adjust cursor position...
         goto MYOFF               # ... and go there
      endif
   next                        # remember: the cursor is now directly at the stream start
   set STREAMSIZE AREA_SIZE         # the last AREA_SIZE is the size we need (size of the audio stream)
   set HEADERSIZE MYOFF            # 
   math HEADERSIZE -= OFFSET         # calculate the size of the stream header (offset - offset = size)
   set SIZE HEADERSIZE               # 
   math SIZE += STREAMSIZE            # calculate complete file size (header + stream = file)
   log MEMORY_FILE OFFSET SIZE         # write file to memory
   math SIZE -= 8                  # subtract 8 bytes to get the riff size
   putVarChr MEMORY_FILE 4 SIZE long    # write the correct riff size to the header inside the memory
   string NAME += ".wav"            # add extension to the name (the name could contain the name of the first marker if the file has markers)
   math SIZE += 8                  # add the subtracted 8 bytes again
   log NAME 0 SIZE MEMORY_FILE         # write file in memory to disk
endfunction                        # remember that we continue with our next i now!

startfunction retrievename            # get possible file name from first marker name, rmember: our cursor is after the size of the LIST area
   get DUMMY long                   # always "adtl", not needed
   get DUMMY long                  # always "labl", not needed
   get MSIZE long                  # size of the label area for this marker
   math MSIZE -= 4                  # subtracting 4 bytes leaves us with the length of the marker label
   get DUMMY long                  # marker type, not needed
   getDstring MNAME MSIZE            # cursor is at the beginning of the label name, now get the marker name with the desired length MSIZE
   string NAME += "~"
   string NAME += MNAME            # add the marker name to the file name
endfunction

```
## Post #5
- Username: Karimmusa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 19, 2020 5:04 am
- Post datetime: 2020-11-20T19:34:06+00:00
- Post Title: Extracting Audio files from Assassin's Creed Valhalla

I'm not having any problems in extracting the files from the pck, I'm having a problem in converting them into playable files.
When I use your script I get the WAV files but they are simply unplayable and cannot be converted.
## Post #6
- Username: Karimmusa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 19, 2020 5:04 am
- Post datetime: 2020-11-20T20:09:12+00:00
- Post Title: Extracting Audio files from Assassin's Creed Valhalla

Here are some sample .wem files that I managed to extracted, and they are simply not getting converted to any playable form 

[https://drive.google.com/file/d/1e4Zbde ... sp=sharing](https://drive.google.com/file/d/1e4ZbdeL7wID0jTtHJi0MIMAsVEOMrwu9/view?usp=sharing)
## Post #7
- Username: LinkOFF
- Rank: beginner
- Number of posts: 38
- Joined date: Mon Sep 08, 2014 7:32 am
- Post datetime: 2020-11-21T17:10:40+00:00
- Post Title: Extracting Audio files from Assassin's Creed Valhalla

> Reply from Karimmusa ↑Sat Nov 21, 2020 3:34 am at Sat Nov 21, 2020 3:34 am
>
> 
I'm not having any problems in extracting the files from the pck, I'm having a problem in converting them into playable files.
When I use your script I get the WAV files but they are simply unplayable and cannot be converted.

Try this - [https://github.com/Vextil/Wwise-Unpacker](https://github.com/Vextil/Wwise-Unpacker)
Works perfectly for me with your first sample file.
## Post #8
- Username: Karimmusa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 19, 2020 5:04 am
- Post datetime: 2020-11-21T19:24:48+00:00
- Post Title: Extracting Audio files from Assassin's Creed Valhalla

> Reply from LinkOFF ↑Sun Nov 22, 2020 1:10 am at Sun Nov 22, 2020 1:10 am
>
> 
Karimmusa wrote: ↑Sat Nov 21, 2020 3:34 am
I'm not having any problems in extracting the files from the pck, I'm having a problem in converting them into playable files.
When I use your script I get the WAV files but they are simply unplayable and cannot be converted.


Try this - https://github.com/Vextil/Wwise-Unpacker
Works perfectly for me with your first sample file.

I'm sorry can you tell me exactly how were you able to do that? Were you able to convert the 1030365303.wem file in this link ?
[https://drive.google.com/file/d/1e4Zbde ... Mrwu9/view](https://drive.google.com/file/d/1e4ZbdeL7wID0jTtHJi0MIMAsVEOMrwu9/view)
And if so can you share with me how were you able to do that?
Thanks
## Post #9
- Username: Karimmusa
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 19, 2020 5:04 am
- Post datetime: 2020-11-22T22:00:12+00:00
- Post Title: Extracting Audio files from Assassin's Creed Valhalla

Posting this here for anyone trying the same 
I was able to extract everything and play it
here is how 
First thing you need to do is to extract the files usind this tool only!
[https://github.com/bnnm/wwiser-utils/bl](https://github.com/bnnm/wwiser-utils/bl) ... ractor.bms
It will extract everything in .wem format
make sure that you use the latest version of Quick bms from here :
[https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)
Third: install Foobar 2000 from here :
[https://www.foobar2000.org/download](https://www.foobar2000.org/download)
and lastly install this plugin for Foobar 2000 :
[https://vgmstream-builds.s3-us-west-1.a](https://vgmstream-builds.s3-us-west-1.a) ... -component
after installing it and applying it you should be able to play all the files and convert them
## Post #10
- Username: a10303
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 14, 2022 1:26 pm
- Post datetime: 2022-11-15T08:09:44+00:00
- Post Title: Extracting Audio files from Assassin's Creed Valhalla

> Reply from LinkOFF ↑Sun Nov 22, 2020 1:10 am at Sun Nov 22, 2020 1:10 am
>
> 
Karimmusa wrote: ↑Sat Nov 21, 2020 3:34 am
I'm not having any problems in extracting the files from the pck, I'm having a problem in converting them into playable files.
When I use your script I get the WAV files but they are simply unplayable and cannot be converted.


Try this - https://github.com/Vextil/Wwise-Unpacker
Works perfectly for me with your first sample file.

Hi! Can't believe I found your tutorial Thank you so much Thank you for the code it's awesome Have a great day Thank you
