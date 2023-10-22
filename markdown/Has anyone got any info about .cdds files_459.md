## Post #1
- Username: mattski
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 17, 2003 6:16 pm
- Post datetime: 2003-10-17T10:19:00+00:00
- Post Title: Has anyone got any info about .cdds files?

Hi, 

I am currently interested in making use of .cdds files that titles such as Lock On and Midtown Madness 3 use. From what I can gather, they appear to be a derivative of .dds files. Certainly, when viewed with a hex editor, they appear to be some kind of archive of .dds's - referencing a number of Target (tga) files.

Any advice or information would be most appreciated.

/m
## Post #2
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2003-10-17T17:39:18+00:00
- Post Title: Has anyone got any info about .cdds files?

Could you link us to a small .cdds file for us to examine?
## Post #3
- Username: mattski
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 17, 2003 6:16 pm
- Post datetime: 2003-10-20T06:53:44+00:00
- Post Title: Has anyone got any info about .cdds files?

Hi, 

Thanks for the reply, I have placed a file, 'cdds.zip' at the following location:

Edit : [link removed]

This file contains two cdds files from the Lock On demo, they are 'WorldTexturesTGA.cdds' and 'CockpitsTexturesTGA.cdds'

thanks,
Matt.

Thanx, I have the files now, and removed the link to them. 
 - Mr.Mouse
## Post #4
- Username: Captain
- Rank: Site Admin
- Number of posts: 248
- Joined date: Thu Jan 16, 2003 1:25 am
- Post datetime: 2003-10-20T07:05:31+00:00
- Post Title: Has anyone got any info about .cdds files?

Thx, we'll try to take a look at it for the next release.
## Post #5
- Username: mattski
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 17, 2003 6:16 pm
- Post datetime: 2003-10-21T13:41:45+00:00
- Post Title: Has anyone got any info about .cdds files?

Thankyou guys, it'll be fantastic if you can crack that one - thanks for all of your hard work.

ta,
Matt.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-10-27T22:43:24+00:00
- Post Title: Has anyone got any info about .cdds files?

I think I cracked it, let's say 90%.    The .cdds files are indeed some sort of collection of .dds files, files that are readable with DirectX Texture Tool. In a way, for each texture is a MIP map present in the archive. This is just pre-resized texturing for any given texture, starting from original size to a 1 by 1 format, in size-halfing steps. I have written a small app that can handle the .cdds files and extract the files in .dds format, although the original filenames, the starting point of the authors, were .tga files. I will create an entry in the XeNTaX' [OpenGRAF](http://www.xentax.com/opengraf/index.html) database, Open Game Resource Archive Formats, which I intend to fill with all my and others' cracked formats. Captain Corny will work on an implementation of .cdds files in OpenMex.  

Here's some proof:
## Post #7
- Username: mattski
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 17, 2003 6:16 pm
- Post datetime: 2003-10-28T15:43:19+00:00
- Post Title: Has anyone got any info about .cdds files?

_fantastic_!!!!  Sir, I owe you many of your favourite [_____] fill in as applicable!!!

/m
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-11-02T21:37:14+00:00
- Post Title: Has anyone got any info about .cdds files?

In addition to the cdds2dds tool, the new release of OpenMex (0.2) includes .cdds support!!
## Post #9
- Username: Yallis
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 09, 2004 4:46 pm
- Post datetime: 2004-01-09T08:51:31+00:00
- Post Title: Has anyone got any info about .cdds files?

Have you actually seen some Midtown Madness 3 .cdds's, are you just assuming that Eagle Dynamics and Dice made the exact same format just because they share the same .cdds-extension? Your specs don't match the Midtown Madness 3 textures at all. Or am I maybe completely wrong?
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-01-11T12:12:22+00:00
- Post Title: Has anyone got any info about .cdds files?

You are right, I did not check, but was told that they matched. Apparently they don't. Oops.
## Post #11
- Username: MachinimaMan
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-06-22T01:47:07+00:00
- Post Title: Has anyone got any info about .cdds files?

Hey, I've got a couple of Midtown Madness 3 CDDS files, do you want me to give you one to examine?
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-22T06:46:14+00:00
- Post Title: Has anyone got any info about .cdds files?

Sure! Send 'em up!
## Post #13
- Username: MachinimaMan
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-06-22T20:23:16+00:00
- Post Title: Has anyone got any info about .cdds files?

Here's 5 of 'em  
[http://midtown.byethost11.com/junkpile/cdds.zip](http://midtown.byethost11.com/junkpile/cdds.zip) - (416kb zip file)
Reply to tell me if the link works or not
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-23T08:17:59+00:00
- Post Title: Has anyone got any info about .cdds files?

The link works. The cdds files are compressed/encrypted. Can't do anything without further information.
## Post #15
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-08-17T21:08:10+00:00
- Post Title: Has anyone got any info about .cdds files?

Well i found a program to reconvert the .CDDS, try and enjoy if works 
[http://loacs.free.fr/BibliothequeC6/LoT ... _Setup.zip](http://loacs.free.fr/BibliothequeC6/LoTextureTool_Setup.zip)
