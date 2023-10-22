## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-12-11T14:22:15+00:00
- Post Title: [Wii] Epic Mickey - pak files

Can you help unpack [this files](http://www.mediafire.com/?bu11rpns276om6t)? I want try to convert 3d models from game.
## Post #2
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2010-12-12T07:16:10+00:00
- Post Title: [Wii] Epic Mickey - pak files

Man, this game is filled to the brim with goodies huh? The video files are in easily convertable .bik files, some of the images are in .dds and .bmp files, and the audio is in .wav files XD .
In those .pak files, there's mention of .hkx, .nif_wii (retitled from .nif,) and .ma files.
The .nif files use the "Gamebryo File Format, Version 20.6.5.0." This version of the Gamebryo File Format can be bought by game companies, and cannot be opened by NifTools currently...
Though, you already knew all that. I just thought I'd put the information here in case anyone has a brain spark.
I'm interested in the apparently unreadable .obj files in the 'sectors' folder. I wonder if those are even 3D objects?
## Post #3
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-15T03:22:03+00:00
- Post Title: [Wii] Epic Mickey - pak files

I am baffled. How do you extract the files from the paks? And if your disk drive can't read your Wii Disc, do you need to download it online to view the files?
## Post #4
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2010-12-15T09:37:04+00:00
- Post Title: [Wii] Epic Mickey - pak files

> Reply from Tosyk
>
> Can you help unpack this files? I want try to convert 3d models from game.
Hi! 
It's great to see you again!

KAP(.pak) file is the same format used in NFS Shift X360.
Did you try Quickbms?
[http://aluigi.org/papers/bms/nfsshift.bms](http://aluigi.org/papers/bms/nfsshift.bms)
[viewtopic.php?f=10&t=3717](http://forum.xentax.com/viewtopic.php?f=10&t=3717)
or
[viewtopic.php?f=10&t=4155&start=0&st=0&sk=t&sd=a](http://forum.xentax.com/viewtopic.php?f=10&t=4155&start=0&st=0&sk=t&sd=a)
## Post #5
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-17T02:03:14+00:00
- Post Title: [Wii] Epic Mickey - pak files

I tried those codes, and they don't work.
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-12-17T17:39:54+00:00
- Post Title: [Wii] Epic Mickey - pak files

Seems to something wrong with my subscription on xentax.

Thanks for clearing up Friedslick6 all about this game and like you said
> Reply from Friedslick6
>
> already knew all that

Thanks for trying youngmark, but all the methods that you have mentioned don't work with the researched files.

We need someone who know how to work with zlibed files.
## Post #7
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2010-12-28T23:49:37+00:00
- Post Title: [Wii] Epic Mickey - pak files

Does anyone know how to actually view the nif files? I believe the current version of NIF only goes up to 20.5.0.0, and the version Epic Mickey uses is 20.6.5.0. So unless someone knows how to update the XML as dictated at [http://niftools.sourceforge.net/forum/v ... =10&t=2810](http://niftools.sourceforge.net/forum/viewtopic.php?f=10&t=2810) , the nif files are of little use to anyone. And if there are other useful files in there, we don't have a working extractor for them, and without one this is an exercise in futility.
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-19T12:06:54+00:00
- Post Title: [Wii] Epic Mickey - pak files

i got pm'd   

should be a solid script - nothing was unknown!

```
# WRS (xentax.com)
endian big
comtype zlib

## header
get H_SIGNATURE long # probally not written as string
get H_VERSION long   # assumed
get H_ZERO    long
get H_SIZE    long
get H_DATAPTR long

math H_DATAPTR += H_SIZE
goto H_SIZE

## file info
get FILES long

math STRPTR = FILES     # calculate string table pos
math STRPTR *= 24       #
savepos FILEDATA        # or += H_SIZE
math STRPTR += FILEDATA #    += 4 (for FILES)

math TOTPOS = H_DATAPTR # sum of aligned size

for f = 0 < FILES

  # record header
  get UNSIZE long # real size
  get PKSIZE long # compressed size
  get ALSIZE long # aligned size

  get FOLDERNM long # string table pointer
  getdstring FILETYPE 4
  get FILENM long # string table pointer

  # get whole filename
  savepos POS

  math FOLDERNM += STRPTR
  math FILENM += STRPTR

  goto FOLDERNM
  get FOLDERSTR string
  goto FILENM
  get FILESTR string

  string FOLDERSTR += "/"
  string FOLDERSTR += FILESTR

  if UNSIZE == PKSIZE
    log FOLDERSTR TOTPOS PKSIZE
  else
    clog FOLDERSTR TOTPOS PKSIZE UNSIZE
  endif

  goto POS
  math TOTPOS += ALSIZE

next f

```

format highlights (new thing i'm trying)

file path is stored in a string table, split by filename and folder path
file positions can only be read by parsing all previous file headers
and the rest: big endian, structure alignment, zlib, header size flag
## Post #9
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-01-20T00:02:34+00:00
- Post Title: [Wii] Epic Mickey - pak files

Awesome! All of the files are extractable now! Now if we could only view bsq, or Gamebryo 20.6.5.0 nif, or lua, or KFM, or HKX, or KF, or lit_cooked, or HKW files. Fortunately, we have them now. I think lua files can be viewed.
## Post #10
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-20T11:36:30+00:00
- Post Title: [Wii] Epic Mickey - pak files

> Reply from Mirrorman95
>
> Awesome! All of the files are extractable now! Now if we could only view bsq, or Gamebryo 20.6.5.0 nif, or lua, or KFM, or HKX, or KF, or lit_cooked, or HKW files. Fortunately, we have them now. I think lua files can be viewed.

the nif tools wiki has so much info on adding new formats - why not give that a shot? compare what's been updated between versions and see what this new one has done differently. these are the models you're after
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-02-18T22:09:45+00:00
- Post Title: [Wii] Epic Mickey - pak files

Opens fine using the QuickBMS option in MultiEx Commander's script window as well! 



pack.JPG (144.12 KiB) Viewed 347 times
## Post #12
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-02-20T18:43:55+00:00
- Post Title: [Wii] Epic Mickey - pak files

How do we get MultiEx?
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2011-02-20T21:26:55+00:00
- Post Title: [Wii] Epic Mickey - pak files

[http://multiex.xentax.com/](http://multiex.xentax.com/)
## Post #14
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2011-03-29T04:11:53+00:00
- Post Title: [Wii] Epic Mickey - pak files

How do you unpack a Wii disk image?

EDIT: Never mind. I just used Noesis.

However, I'm using the beta of NifSkope updated on March 19th, and it still can't load Epic Mickey files. Why is this?
