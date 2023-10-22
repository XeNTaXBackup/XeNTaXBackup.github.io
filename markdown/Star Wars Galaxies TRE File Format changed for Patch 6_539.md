## Post #1
- Username: MashRinx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 03, 2004 9:14 am
- Post datetime: 2004-02-03T01:19:39+00:00
- Post Title: Star Wars Galaxies TRE File Format changed for "Patch 6

Hi All,
I have been able to use the TRE viewer to extract all of the SWG files to date, but it appears that the format for "patch 6" which was released sometime over the last 24 hours (file create date is today, 4:04pm) will no longer work.  When I try to open patch_6.tre, I get the error:  "Decompression of tail failed".

Here is the contents of the log file.  I hope this helps.
PS REALLY nice work, Mr. Mouse...  Thank you!!


[x] Ok - *** XENTAX TRECLASS New Debug Log *** > 2/2/2004 8:13:58 PM
[x] Ok - Clear->Clearing TRE
[x] Ok - [!] Ok 0
[x] Ok - OpenTRE->Opening C:\Games\StarWarsGalaxies\patch_05.tre, 1
[x] Ok - OpenTRE->Loading Header of C:\Games\StarWarsGalaxies\patch_05.tre, 1
[x] Ok - OpenTRE->Header ID =EERT5000
[x] Ok - OpenTRE->Header variables : 2193,25737445,2,35204,2,20037,116338
[x] Ok - OpenTRE->Reading tail data at : 25737445
[x] Ok - OpenTRE->Tails read (in bytes) : 35203, 20036
[x] Ok - OpenTRE->Decompression if necessary
[x] Ok - DecompressData>Decompression Result: 0
[x] Ok - OpenTRE->Decompression Result: 0
[x] Ok - DecompressData>Decompression Result: 0
[x] Ok - OpenTRE->Creating temporary tailfiles : 
C:\Documents and Settings\Administrator\Desktop\XeNTaX_TRE_Archiver\t1.tmp
C:\Documents and Settings\Administrator\Desktop\XeNTaX_TRE_Archiver\t2.tmp
[x] Ok - OpenTRE->Temporary tailfiles created
[x] Ok - OpenTRE->Opening Temporary Tails
[x] Ok - OpenTRE->Reading tails
[x] Ok - OpenTRE->Temporary tails read, closed and destroyed.
[x] Ok - [!] Ok 0
[x] Ok - *** XENTAX TRECLASS New Debug Log *** > 2/2/2004 8:14:02 PM
[x] Ok - Clear->Clearing TRE
[x] Ok - [!] Ok 0
[x] Ok - OpenTRE->Opening C:\Games\StarWarsGalaxies\patch_06.tre, 1
[x] Ok - OpenTRE->Loading Header of C:\Games\StarWarsGalaxies\patch_06.tre, 1
[x] Ok - OpenTRE->Header ID =EERT5000
[x] Ok - OpenTRE->Header variables : 2774,40610155,2,44594,2,25593,141039
[x] Ok - OpenTRE->Reading tail data at : 40610155
[x] Ok - OpenTRE->Tails read (in bytes) : 44593, 25592
[x] Ok - OpenTRE->Decompression if necessary
[x] Ok - DecompressData>Decompression Result: -3
[x] Ok - OpenTRE->Decompression Result: -3
[x] Decompression of tail Failed - [!] Decompression of tail Failed 12
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-02-03T11:11:03+00:00
- Post Title: Star Wars Galaxies TRE File Format changed for "Patch 6

Interesting. Could they have altered the compression method? Is that a big patch file, or sendable via email?
## Post #3
- Username: MashRinx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 03, 2004 9:14 am
- Post datetime: 2004-02-03T15:40:40+00:00
- Post Title: Star Wars Galaxies TRE File Format changed for "Patch 6

The patch file is 25.8 megs.  Since it's already compressed, Zipping it only saved .2 megs.  I'm thinking that's going to be too large to e-mail.... Let me know if you have another way of receiving the file?  FTP, etc?

Otherwise, is there any information I might be able to capture in a Hex Editor or something like that that would be beneficial?  I can get around in a hex editor, but beyond that would get over my head pretty quickly  

Mash
## Post #4
- Username: MashRinx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 03, 2004 9:14 am
- Post datetime: 2004-02-05T20:15:28+00:00
- Post Title: Star Wars Galaxies TRE File Format changed for "Patch 6

Update:  The patch_6.tre file IS still readable.  What it looks like happened is SOE pushed the patch out in pieces.  Originally, when I tried to extract, the final piece of the file must not have been there, so TRE Archiver could not find the tail (which makes sense).  Now that the patch files is complete (a couple days later), it opens fine...

Sorry for the confusion...

Mash
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-02-06T07:35:58+00:00
- Post Title: Star Wars Galaxies TRE File Format changed for "Patch 6

Ah, that's good news then.
## Post #6
- Username: theonlyfox
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 09, 2004 1:36 am
- Post datetime: 2004-02-08T17:44:14+00:00
- Post Title: Star Wars Galaxies TRE File Format changed for "Patch 6

I just downloaded the .tre archiver and Im unable to open any .tre file.  The message given is simply "error opening tre file".  Here are the details of the log file:

[x] Ok - *** New Debug Log *** > 2/8/2004
[x] Ok - OpenTRE->Opening C:\Program Files\StarWarsGalaxies\data_music_00.tre, 1
[x] Ok - OpenTRE->Loading Header of C:\Program Files\StarWarsGalaxies\data_music_00.tre, 1
[x] Ok - OpenTRE->Header ID =EERT5000
[x] Ok - OpenTRE->Header variables : 144,77317568,2,2154,2,868,4404
[x] Ok - OpenTRE->Reading tail data at : 77317568
[x] Ok - OpenTRE->Tails read (in bytes) : 2153, 867
[x] Ok - OpenTRE->Decompression if necessary
[x] Error opening TRE file - [!] Error opening TRE file 4
[x] Ok - *** New Debug Log *** > 2/8/2004
[x] Ok - OpenTRE->Opening C:\Program Files\StarWarsGalaxies\data_music_00.tre, 1
[x] Ok - OpenTRE->Loading Header of C:\Program Files\StarWarsGalaxies\data_music_00.tre, 1
[x] Ok - OpenTRE->Header ID =EERT5000
[x] Ok - OpenTRE->Header variables : 144,77317568,2,2154,2,868,4404
[x] Ok - OpenTRE->Reading tail data at : 77317568
[x] Ok - OpenTRE->Tails read (in bytes) : 2153, 867
[x] Ok - OpenTRE->Decompression if necessary
[x] Error opening TRE file - [!] Error opening TRE file 4


Has something changed?  I cant imagine that its a permission issue, Im logged on as admistrator on XP.   Any Ideas.
## Post #7
- Username: theonlyfox
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 09, 2004 1:36 am
- Post datetime: 2004-02-08T18:57:43+00:00
- Post Title: Star Wars Galaxies TRE File Format changed for "Patch 6

Ok, disregard previous message.  I got it to work, but I had to download the OpenMex commander.  I guess the Xentax tre archiver is missing a dll that the OpenMex commander places in the system, but the tre archiver will not work independantly without the commander.

One question, is there away to incorporate the tre archiver into the commander?
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-02-08T19:12:52+00:00
- Post Title: Star Wars Galaxies TRE File Format changed for "Patch 6

Yes, you need some dll's to get it to uncompress/compress. You're mixing MultiEx Commander and OpenMex I think. You probably mean the first. 
Implementation may be possible when I get around to it, to create it as a plugin for MultiEx Commander. Good idea, I already have the code!
## Post #9
- Username: Mertiliano
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 25, 2005 3:44 am
- Post datetime: 2005-06-24T19:47:07+00:00
- Post Title: Star Wars Galaxies TRE File Format changed for "Patch 6

Hm.. maybe it's just me but looks like they changed them this time no programs I normally have been using are opening them. Log trying to open a patch 19 file:

[x] Ok - OpenTRE->Opening C:\Documents and Settings\Admin\Desktop\setup files\swgfiles\hotfix_19_shared_00.tre, 1
[x] Ok - OpenTRE->Loading Header of C:\Documents and Settings\Admin\Desktop\setup files\swgfiles\hotfix_19_shared_00.tre, 1
[x] Ok - OpenTRE->Header ID =EERT6000
[x] Not a valid TRE file - [!] Not a valid TRE file 5
## Post #10
- Username: Karyfars
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Jul 15, 2005 7:20 pm
- Post datetime: 2005-07-16T17:33:04+00:00
- Post Title: Star Wars Galaxies TRE File Format changed for "Patch 6

[Tree v6 discussion](http://forum.xentax.com/viewtopic.php?t=1361)
