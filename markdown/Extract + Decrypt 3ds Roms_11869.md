## Post #1
- Username: EcheloCross
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-08-30T23:25:39+00:00
- Post Title: Extract + Decrypt 3ds Roms

Your 3ds needs to be on 4.5 or lower firmware.

Step 1.
Download these tools
[https://www.sendspace.com/file/icnkiz](https://www.sendspace.com/file/icnkiz)
[https://www.sendspace.com/file/4azlvg](https://www.sendspace.com/file/4azlvg)

Step 2.
on your pc drag the 3ds rom you want to decrypt onto ctrKeyGen.exe
this will generate
ncchinfo.bin

Step 3.
Copy Launcher.dat and ncchinfo.bin onto the 3ds internal sd card. (not the gateway micro sd card)

Step 4.
Launch the gateway exploit as you normally would by going into ds profile settings.

Step 5.
Wait while it generates a file on the 3ds
CTR-P-AKHP0.romfs.xorpad

step 6.
drag your 3ds rom onto getromfs.exe and it will create  EncryptedRomFS.bin
copy CTR-P-AKHP0.romfs.xorpad to this directory also

Step 6-a.
if EncryptedRomFS.bin and your xorpad are not th esame size
you need to trim the xorpad to match its size using a hex editor.

Step 7.
hold shift in the folder containing these tools and the 3ds rom and right click and choose open command prompt here.
type in the command prompt
xor.exe CTR-P-AKHP0.romfs.xorpad EncryptedRomFS.bin
and it will generate
DecryptedRomFS.bin

Step 8.
Now run from the same command prompt
ctrtool.exe -x DecryptedRomFS.bin --romfsdir=My_Extraction_Folder

Step 9.
Profit ???
example folder structure.
[http://pastebin.com/raw.php?i=XdghCm54](http://pastebin.com/raw.php?i=XdghCm54)
## Post #2
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-08-30T23:54:29+00:00
- Post Title: Extract + Decrypt 3ds Roms

And here I am with a 3DS at firmware 8.1.0-19U, way too late for any of this (and no funds to obtain an earlier one). So much for me making any use of this.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-08-30T23:56:48+00:00
- Post Title: Extract + Decrypt 3ds Roms

you can find them at a lot of un popular local stores still.
just look at the serial numbers or ask if you can try them before you buy it if its like a used store.
or find a friend who has one and trade him.
you can get non xl ones for not too bad a price.
## Post #4
- Username: GovanifY
- Rank: advanced
- Number of posts: 59
- Joined date: Thu Apr 17, 2014 4:25 am
- Post datetime: 2014-08-31T12:13:53+00:00
- Post Title: Extract + Decrypt 3ds Roms

Happy to see that this tools helped some people! =D (I worked on it)
Also @chrrox thx for sharing it there! could help some peoples
Now let's get to work into 3d models ;3
## Post #5
- Username: clang7775
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Sep 29, 2014 2:31 am
- Post datetime: 2014-09-28T18:44:24+00:00
- Post Title: Extract + Decrypt 3ds Roms

Thanks! I have a 3ds with older firmware so gonna try this out...
## Post #6
- Username: Gerte
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 04, 2014 2:04 am
- Post datetime: 2014-10-11T13:32:21+00:00
- Post Title: Extract + Decrypt 3ds Roms

im not understand. does it mean i should have nitendo first not an simulator on pc?
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-10-11T13:49:34+00:00
- Post Title: Extract + Decrypt 3ds Roms

yes you need a 3ds with old firmware to do this.
there is no 3ds emulator.
