## Post #1
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-01-16T08:16:57+00:00
- Post Title: Kingdom hearts 1.5 original audio files

Are the audio files (voice and battle-quotes) of the Final 1.5 Mix different from the original final mix, in terms of quality? if so, how can they be extracted?
## Post #2
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-04-16T21:34:04+00:00
- Post Title: Kingdom hearts 1.5 original audio files

I don't really checked at them but I'm sure I already saw them inside some 1.5 mdls

If u want to extract them, use this script(not made by me, but by Falo)

> Reply from Falo
>
> Really simple format:
Code: Select all# Square Enix - Kingdom Hearts HD 1.5 ReMix *.mdls
# by Falo
# script for QuickBMS http://quickbms.aluigi.org

set MAX_FILES 1024

for x = 0 < MAX_FILES

GetDString Name 0x20
get Offset long
get Size long
get empty long
get empty long

math Offset += 0xC000

if Size == 0
cleanexit
endif

log Name Offset Size

next x
the model is the xa_ew_3020_mdlsc0.cvbb
## Post #3
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-04-20T20:25:28+00:00
- Post Title: Kingdom hearts 1.5 original audio files

thanks! directly on the ISO?
## Post #4
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-04-24T22:12:39+00:00
- Post Title: Kingdom hearts 1.5 original audio files

Sorry for the late reply, not so much on XentaX.
Nope, that's inside the file kingdom.mself which can be extracted w/ this script:

```

idstring "MSF"

goto 0x10
get numFiles long
get ofsTable long
goto ofsTable

for x = 0 < numFiles

GetDString Name 0x20
get Offset LONGLONG
get Size LONGLONG
get empty LONGLONG
get empty LONGLONG

log Name Offset Size

next x
```


Once again, it will require quickbms. Extract the mself, then decrypt the file w/ my toolkit: [http://govanify.x10host.com/_files/SDATA_DEC.exe](http://govanify.x10host.com/_files/SDATA_DEC.exe) (just drag 'n drop the sdat on him) then use the mdls script for extract the files.
Bye and good luck, GovanifY
## Post #5
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-04-25T06:59:09+00:00
- Post Title: Kingdom hearts 1.5 original audio files

oh they changed also that format... thanks
## Post #6
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-04-25T10:37:52+00:00
- Post Title: Kingdom hearts 1.5 original audio files

Well they tipically change practically every format, MIPS isn't used so they needed to recode partly the game. The format is, iirc and afaik, a simple LAME-3 format. Not a big deal. I'm not sure but I think they don't changed the quality. But maybe they did b\c square were sayin' they were registerin' somethin' a while ago, so who knows

Bye, GovanifY
## Post #7
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-04-25T10:40:51+00:00
- Post Title: Kingdom hearts 1.5 original audio files

I meant the archive format
## Post #8
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-04-25T10:43:59+00:00
- Post Title: Kingdom hearts 1.5 original audio files

Ah, ya they changed every format which is like: NAME_SDAT. This pattern means the file is a container like the mdls one. They did that when rewritiung the game. They were unable to make something which looks like KH1/2(IDX who contains the LBA, flags, etc...+IMG who contains the file)b\c they didn't needed any LBA. So they just basically used $0ny formats for pack/encrypt their files, I think b\c they were too lazy for create custom formats for a HD remix

Bye, GovanifY
## Post #9
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-04-28T10:15:46+00:00
- Post Title: Kingdom hearts 1.5 original audio files

thanks again
