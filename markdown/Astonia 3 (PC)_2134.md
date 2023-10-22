## Post #1
- Username: hollinar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 08, 2006 6:33 am
- Post datetime: 2006-10-07T23:01:52+00:00
- Post Title: Astonia 3 (PC)

Hello. Can anyone work on the following?

Astonia 3
[http://www.astonia.com/](http://www.astonia.com/)
Free 30-day trial, no CC info needed
File with info attached as astonia.zip
[Astonia.zip](https://xentaxbackup.github.io/file/895_Astonia.zip)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-10-08T00:48:59+00:00
- Post Title: Astonia 3 (PC)

at 1rst looks zlib packed file
## Post #3
- Username: hollinar
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 08, 2006 6:33 am
- Post datetime: 2006-10-10T07:54:00+00:00
- Post Title: Astonia 3 (PC)

Zlib... Does that mean that there is already a way to extract/inject data from the files?
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-10-10T18:22:01+00:00
- Post Title: Astonia 3 (PC)

i unpacked the exmaple but the files are empty
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-10T19:41:33+00:00
- Post Title: Astonia 3 (PC)

Nope, they are not. The files are indeed Zlib compressed and you can decompress them. 

Use this MexScript :

```
# By Mr.Mouse 
# Files are ZLib compressed
# But no UCSize is saved in here!
# So, I set the max UCSize to 100000
ComType ZLib1 ;
Get Date Long 0 ;
Get FileNum Long 0 ;
For T = 1 To FileNum ;
Get Offset Long 0 ;
Get CSize Long 0 ;
Get UCSize Long 0 ;
Get CType Long 0;
Math Offset += 8 ;
Set FN String ".dec" ;
Set FP String "file" ;
String FP += UCSize ;
String FP += FN ;
Set UCSize Long 1000000 ;
CLog FP Offset CSize 0 0 UCSize 0 ;
Next T ;


```


The problem is that there is no "uncompressed size" variable saved in the pak file. There is some kind of counter that starts at 10000, this may also refer to the 0010000.pak . Anyway, I gave a max decompression size of 1000000. There are no file names in there, but the files will be extracted as fileXXXXX.dec. 

You can copy the script to a text file and then run that as MexScript on a PAK file of your choice. Or, get the attached txt file.
[pak.zip](https://xentaxbackup.github.io/file/906_pak.zip)
## Post #6
- Username: WaynesWorld
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 03, 2008 10:34 pm
- Post datetime: 2008-11-03T21:37:57+00:00
- Post Title: Astonia 3 (PC)

Okay - I'm trying to get to the graphics in Astonia 3 - I've got the MexScript below detecting and extacting individual files from the original .pak files, however, the resulting files are worthless.  The files themselves when you look at them in a hex editor are not anything useful that I can determine.  

So - my questions are:

1) What am I doing wrong that is creating files that are not .bmp files (this game shows everything as a .bmp file in version 2 so I'm assuming that true on version 3 as it appears to be built the same way by the same solo programmer...) The files don't open in any graphical editor (photoshop, paint, gimp, etc).

2) Did the script file have it wrong?

Waynesworld
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-03T22:49:43+00:00
- Post Title: Astonia 3 (PC)

I'd have to have example archives to check.
## Post #8
- Username: WaynesWorld
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 03, 2008 10:34 pm
- Post datetime: 2008-11-03T23:01:31+00:00
- Post Title: Astonia 3 (PC)

You can download the source and the MexScript from here:

Source File: [http://66.28.242.115/00216000.pak](http://66.28.242.115/00216000.pak)

MexScript: [http://66.28.242.115/pak.txt](http://66.28.242.115/pak.txt)

BTW: Hexediting revealed on the main game executable that the graphics are .png - not .bmp after all.

Thx!
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-04T09:49:17+00:00
- Post Title: Astonia 3 (PC)

Ok, thanks. Will take a look.
## Post #10
- Username: asmxtx
- Rank: veteran
- Number of posts: 127
- Joined date: Mon Jun 09, 2008 5:32 am
- Post datetime: 2008-11-04T20:54:13+00:00
- Post Title: Astonia 3 (PC)

> Reply from Mr.Mouse
>
> The problem is that there is no "uncompressed size" variable saved in the pak file.That's not correct. There are gaps between the compressed ZLIB-blocks. The decompressed size is located there.
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-04T23:32:59+00:00
- Post Title: Astonia 3 (PC)

Hmm, indeed huh? I'll take a look. Might be different versions?? Hmmmmm
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-11-06T19:29:45+00:00
- Post Title: Astonia 3 (PC)

```
# By Mr.Mouse 
# Files are ZLib compressed
ComType ZLib1 ;
Get Date Long 0 ;
Get FileNum Long 0 ;
For T = 1 To FileNum ;
Get Offset Long 0 ;
Get CSize Long 0 ;
Get UCSize Long 0 ;
Get CType Long 0;
SavePos CP 0 ;
GoTo Offset 0 ;
Get CSize Long 0 ;
Get UCSize Long 0 ;
SavePos Offset 0 ;
Set FN String ".dec" ;
Set FP String "file" ;
String FP += UCSize ;
String FP += T ;
String FP += FN ;
CLog FP Offset CSize 0 0 UCSize 0 ;
GoTo CP 0 ;
Next T ;

```


There, updated. However, the original script did extract the files in the .PAK file correctly. They are raw bitmaps, with no palette or compression.

See below for examples.



file1040.jpg (3.07 KiB) Viewed 506 times




file2544.jpg (3.63 KiB) Viewed 507 times




File 216000.jpg (3.91 KiB) Viewed 508 times


[pak.zip](https://xentaxbackup.github.io/file/1724_pak.zip)
## Post #13
- Username: WaynesWorld
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 03, 2008 10:34 pm
- Post datetime: 2008-11-06T20:01:50+00:00
- Post Title: Astonia 3 (PC)

Thank you!  That's perfect!
