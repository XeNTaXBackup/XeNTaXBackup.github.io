## Post #1
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-07-05T01:07:39+00:00
- Post Title: (PC) Aerial Strike: Low Altitude High Stakes *.yrf

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-07-05T04:37:37+00:00
- Post Title: (PC) Aerial Strike: Low Altitude High Stakes *.yrf

This is the structure of the .YRF file:

```
   -> ID : Array[0..4] Of Char; // 'YRSFW'
   -> Unknown1 : Array[0..7] Of Byte;
   -> DirectoryStartPos : DWORD // Points to the end of the file
   -> Unknown2 : Array[0..3] Of Byte // or [0..4] of Byte

 ->File data...

 ->Directory: (recursive)
   -> Flag       : WORD // 0=directory 1=file
   -> NameLength : WORD 
   -> Name : Array[0..NameLength-1] of Chars

     -> if Flag==0 (directory)
         -> NrOfChildItems : DWORD
                 // for each entries in this directory
                 // Repeat from "Flag" 

     -> if Flag==1 (file)
         -> FileSize     : DWORD
         -> FileStartPos : DWORD


```

I created a simple YRF extractor/updater util. It's possible to extract all files form the .YRF archive, or replace only one file inside the .YRF. The "Make .YRF" function not works yet, but I'm working on it.
## Post #3
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-07-06T23:31:01+00:00
- Post Title: (PC) Aerial Strike: Low Altitude High Stakes *.yrf

wow thank you so much for the effort and time helping out a noob like me sir! 

i can confirm that it's working on almost all of the files i've tested on 

thank you sir bacter!
## Post #4
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-07-07T19:15:45+00:00
- Post Title: (PC) Aerial Strike: Low Altitude High Stakes *.yrf

I finished my YRF util, now it can extract, update or create new .YRF files.
## Post #5
- Username: Rion
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Jul 08, 2011 4:14 am
- Post datetime: 2011-07-07T21:17:44+00:00
- Post Title: (PC) Aerial Strike: Low Altitude High Stakes *.yrf

I was just searching all over the web for a YRF packer/unpacker util. Is it still available for download? I'd like to extract Yager's .yrf files for localization.
## Post #6
- Username: prudislav
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 13, 2010 6:48 am
- Post datetime: 2011-07-14T10:00:32+00:00
- Post Title: (PC) Aerial Strike: Low Altitude High Stakes *.yrf

> Reply from Rion
>
> I was just searching all over the web for a YRF packer/unpacker util. Is it still available for download? I'd like to extract Yager's .yrf files for localization.
yep me too
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-07-14T10:31:52+00:00
- Post Title: (PC) Aerial Strike: Low Altitude High Stakes *.yrf

Used to be some way to download it here, dunno what happened, maybe in the process of forum changes it got lost. But here it is for ya. Good thing I got a backup. 
[AerialStrike_Util_V1_00.rar](https://xentaxbackup.github.io/file/4487_AerialStrike_Util_V1_00.rar)
## Post #8
- Username: Notex
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Feb 18, 2017 10:12 pm
- Post datetime: 2019-12-12T09:19:45+00:00
- Post Title: (PC) Aerial Strike: Low Altitude High Stakes *.yrf

> Reply from bacter ↑Thu Jul 08, 2010 3:15 am at Thu Jul 08, 2010 3:15 am
>
> 
I finished my YRF util, now it can extract, update or create new .YRF files.

Any chance you still happen to have the source code for this program? I would like to try adding support for the Xbox version of Yager. Seems your tool is not compatible with the YRF archives from it.
