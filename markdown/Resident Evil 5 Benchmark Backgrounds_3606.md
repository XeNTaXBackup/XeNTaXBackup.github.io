## Post #1
- Username: Lev
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jul 23, 2009 8:28 pm
- Post datetime: 2009-07-23T13:56:48+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

I apologise in advance if this isn't the right place to post this request, but I thought it'd be best if I post it here.

Now I have absolutely zero extraction experiences so my question is, would it be remotely possible to extract the backgrounds from the Resident Evil 5 benchmark? I'm referring to the ones that you get once the benchmark process has been completed and gives you a rank for how well your PC handles Resident Evil 5. I'll include a screenshot.

The benchmark tool can be found here: [http://www.nzone.com/object/nzone_re5_downloads.html](http://www.nzone.com/object/nzone_re5_downloads.html)

I realise that it might be better to wait for the PC version to be released on Sept 15 but figured I should try anyhow.

Many thanks.

EDIT: Darn it! I meant to post this in Games Archive Research...Crap.
[re5dx102009071623222511.jpg](https://xentaxbackup.github.io/file/2223_re5dx102009071623222511.jpg)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-25T17:01:43+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

you can just use 3dripperdx or texmod to capture the textures from the game.
## Post #3
- Username: Darkfox
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-25T23:07:14+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

True, but that's not neat. And generic extraction won't work here, as the textures have been modified. Here's BMS for MultiEx Commander that will extract everything from any *.arc file. You should check the BenchResource.arc, that has the images you want. 

```
ImpType Standard ;
IDString 0 ARC ;
Get Null Byte 0 ;
Get Version Int 0 ;
Get FN Int 0 ;
For T = 1 to FN ;
SavePos H 0 ;
Get Name String 0 ;
Math H += 64 ;
GoTo H 0 ;
Get U1 Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get U2 Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
Set U2 Long FS ;
Math U2 *= 16 ;
CLog Name FO FS FOO FSO U2 0 ;
Next T ;

```


Use this arc.bms file in MultiEx Commander to open them. 
Go to Tools-->Ad BMS to MRF and then add the file, and name the game (like 'Resident Evil 5-Benchmark'). Now open those *.arc files with MultiEx Commander, you can even replace stuff in the archives. 


 arc.zip
(313 Bytes) Downloaded 54 times



Now, you will extract DDS textures stripped off their header, and replaced with a new header that starts with "TEX" and has Width stored at byte 12 (a 16-bit value) and Heigth at byte 14, the image data starts at byte 44 up to the end of the file. 

By reconstructing the DDS file (type DXt1 or DXT5) you get this, for example , with 'cap_end00_360_NOMIP_BM'



cap_end00_360_NOMIP_BM_s.jpg (446.66 KiB) Viewed 784 times



The reconstructed original DXT1 .DDS file:


 cap_end00_360_NOMIP_BM.zip
(311.25 KiB) Downloaded 77 times



That's it, really. Nothing more to it.
## Post #4
- Username: Lev
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jul 23, 2009 8:28 pm
- Post datetime: 2009-07-26T14:50:06+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

You rock Mr. Mouse. Thanks for the explanation as well, very helpful.
## Post #5
- Username: Lev
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jul 23, 2009 8:28 pm
- Post datetime: 2009-07-26T19:07:32+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

I came as far as opening the .arc files and have them displayed in MultiEx Commander. However, I'm not sure what to do after that. I tried extracting the said files, but they don't show up in my map.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-26T19:23:50+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

I suggest you also take a peek here, there's some more info: [viewtopic.php?f=10&t=3589](http://forum.xentax.com/viewtopic.php?f=10&t=3589)

As for the files, can you post a screenshot of MultiEx Commander? You have to construct the dds file yourself. But, first take a look at the above thread.
## Post #7
- Username: Lev
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jul 23, 2009 8:28 pm
- Post datetime: 2009-07-26T19:55:45+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

I read the thread though I'm not sure what I'm looking for over there. How do I construct the dds file myself?

I'm including a screenshot of what I'm seeing.
[Untitled.jpg](https://xentaxbackup.github.io/file/2233_Untitled.jpg)
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-26T20:11:27+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

Okay, get the example dds file I attached and open it using a hex editor. The first 128 bytes is the DDS header. Replace all data that comes after this with the uncompressed file you extract using MultiEx Commander and update the width and height in the header. Google for the DDS header format. I've told you the header format of the files you extract.
## Post #9
- Username: Lev
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jul 23, 2009 8:28 pm
- Post datetime: 2009-07-26T20:43:02+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

The problem is, how do I extract the files from Multi Ex Commander? I tried extracting some files and they just didn't show up.

The files I'm looking at in Multi Ex are files with the TEX format, right? And why should I google the dds header format? So I can find a program that can be associated with it?

Yeah, this is complicated stuff for me, I guess. Sorry to be such a pain. I'm still a noob regarding this.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-26T21:13:22+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

Well, after opening the file, immediately click the large extract button and point to a directory. It should extract. After that, please get the debug.log file in MultiEx Commander's main folder and attach it here.
## Post #11
- Username: Lev
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jul 23, 2009 8:28 pm
- Post datetime: 2009-07-26T21:31:23+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

```
23:26:15[i]- Archive process format  MEX3
23:26:15[i]- Calling Multiex with  C:\Program Files\MultiEx Commander\data\multiex.lst
23:26:15[i]- Evaluating archive contents 
23:26:15[i]- MEX Open list file  C:\Program Files\MultiEx Commander\data\multiex.lst
23:26:15[i]- MEX Number of list entries  8
23:26:22[i]- Starting Extraction 
23:26:22[i]- Extracting file  d:\id\jpn\benchmark\cap_end05_360_NOMIP_BM
23:26:22[i]- Decompressing d:\id\jpn\benchmark\cap_end05_360_NOMIP_BM
23:26:22[i]- Extraction done 
23:26:32[i]- Starting Extraction 
23:26:32[i]- Extracting file  d:\id\jpn\benchmark\cap_end05_360_NOMIP_BM
23:26:32[i]- Decompressing d:\id\jpn\benchmark\cap_end05_360_NOMIP_BM
23:26:32[i]- Extraction done 
23:27:15[i]- MEX Load language:  C:\Program Files\MultiEx Commander\data\languages\English.txt
23:27:18[i]- MEX Load language:  C:\Program Files\MultiEx Commander\data\languages\English.txt
23:27:18[i]- MEX Set language 
23:27:21[i]- Starting Extraction 
23:27:21[i]- Extracting file  d:\id\jpn\benchmark\cap_end04_360_NOMIP_BM
23:27:21[i]- Decompressing d:\id\jpn\benchmark\cap_end04_360_NOMIP_BM
23:27:21[i]- Extraction done 
23:28:28[i]- Starting Extraction 
23:28:28[i]- Extracting file  d:\Downloads\id\jpn\benchmark\cap_end03_360_NOMIP_BM
23:28:28[i]- Decompressing d:\Downloads\id\jpn\benchmark\cap_end03_360_NOMIP_BM
23:28:28[i]- Extraction done 
23:28:38[i]- Starting Extraction 
23:28:38[i]- Extracting file  d:\Downloads\id\jpn\benchmark\cap_end05_360_NOMIP_BM
23:28:38[i]- Decompressing d:\Downloads\id\jpn\benchmark\cap_end05_360_NOMIP_BM
23:28:38[i]- Extracting file  d:\Downloads\id\jpn\benchmark\cap_end04_360_NOMIP_BM
23:28:38[i]- Decompressing d:\Downloads\id\jpn\benchmark\cap_end04_360_NOMIP_BM
23:28:38[i]- Extracting file  d:\Downloads\id\jpn\benchmark\cap_end02_360_NOMIP_BM
23:28:38[i]- Decompressing d:\Downloads\id\jpn\benchmark\cap_end02_360_NOMIP_BM
23:28:38[i]- Extracting file  d:\Downloads\id\jpn\benchmark\cap_end03_360_NOMIP_BM
23:28:38[i]- Decompressing d:\Downloads\id\jpn\benchmark\cap_end03_360_NOMIP_BM
23:28:38[i]- Extraction done 
```


Just copy pasting this because I'm not allowed to upload the file. It does say "exctracting done" but my file is nowhere to be found. I've tried multiple folders.
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-27T01:29:49+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

Here is a quick bms script to convert and extract those textures.

```
idstring "ARC\0"
get VERSION short
get FILES short

 set MEMORY_FILE2 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x04\x00\x00\x00\x04\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE3 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x02\x00\x00\x00\x02\x00\x00\x00\x00\x04\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE4 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x02\x00\x00\x00\x04\x00\x00\x00\x00\x04\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE5 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x02\x00\x00\x00\x02\x00\x00\x00\x00\x04\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE6 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x01\x00\x00\x00\x02\x00\x00\x00\x00\x02\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE7 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x02\x00\x00\x00\x02\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE8 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x01\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x09\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
 set MEMORY_FILE9 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x01\x00\x00\x00\x02\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE10 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x01\x00\x00\x00\x01\x00\x00\x00\x80\x00\x00\x00\x00\x00\x00\x09\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE11 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x80\x00\x00\x00\x00\x02\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE12 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x80\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x09\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE13 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x02\x00\x00\x00\x04\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE14 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x04\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0C\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE15 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x02\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE16 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x40\x00\x00\x00\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x07\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE17 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x40\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x09\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE18 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x01\x00\x00\x00\x04\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE19 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x80\x00\x00\x00\x00\x02\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE20 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x04\x00\x00\x80\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0B\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE21 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x00\x02\x00\x00\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE22 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x02\x00\x80\x00\x00\x00\x80\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE23 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x00\x00\x00\x04\x00\x00\x00\x04\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE24 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x00\x00\x00\x04\x00\x00\x00\x04\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE25 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x02\x00\x00\x00\x02\x00\x00\x00\x00\x04\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set MEMORY_FILE26 binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\xD0\x02\x00\x00\x00\x05\x00\x00\x00\x10\x0E\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
#set MEMORY_FILE27 binary ""
#set MEMORY_FILE28 binary ""
#set MEMORY_FILE29 binary ""
#set MEMORY_FILE30 binary ""


for i = 0 < FILES

    getdstring NAME 0x40
    get TYPE1 long
    get ZSIZE long
    get SIZE 3
    get NSIZE byte
    get OFFSET long
    math COUNTER += 1

    clog MEMORY_FILE OFFSET ZSIZE SIZE

    getdstring TYPE 4 MEMORY_FILE
print "%SIZE%"

    if TYPE == "MOD"
       string NAME += ".mod"
else if TYPE == "RTX"
       string NAME += ".rtx"
else if TYPE == "WààW"
       string NAME += ".waaw"
else if TYPE == "XFS"
       string NAME += ".lsp"
else if TYPE == "SDL"
       string NAME += ".sdl"
else if TYPE == "SREQ"
       string NAME += ".sreq"
else if TYPE == "SBC1"
       string NAME += ".sbc1"
else if TYPE == "NAV"
       string NAME += ".nav"
else if TYPE == "WAY"
       string NAME += ".way"
else if TYPE == "STRQ"
       string NAME += ".strq"
else if TYPE == "SPAC"
       string NAME += ".spac"
else if TYPE == "DNRS"
       string NAME += ".dnrs"
else if TYPE == "LCM"
       string NAME += ".lcm"
else if TYPE == "LMT"
       string NAME += ".lmt"
else if TYPE == "EFL"
       string NAME += ".efl"
else if TYPE == "CHN"
       string NAME += ".chn"
else if TYPE == "MTG"
       string NAME += ".mtg"
else if TYPE == "EFS"
       string NAME += ".efs"
else if TYPE == "EAN"
       string NAME += ".ean"
else if TYPE == "E2D"
       string NAME += ".e2d"
else if TYPE == "HIT"
       string NAME += ".hit"
else if TYPE == "CCL"
       string NAME += ".ccl"
else if TYPE == "CHN"
       string NAME += ".chn"
else if TYPE == "SDST"
       string NAME += ".sdst"
else if TYPE == "EQU"
       string NAME += ".equ"
else if TYPE == "CHN"
       string NAME += ".chn"
#else if TYPE == "CHN"
#       string NAME += ".chn"
#else if TYPE == "CHN"
#       string NAME += ".chn"
	endif
    if SIZE == "699148"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE2
        math SIZE -= 0x54
        log NAME 0x54 SIZE MEMORY_FILE
        append

       else if SIZE == "349632"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE3
        math SIZE -= 0x50
        log NAME 0x50 SIZE MEMORY_FILE
        append

       else if SIZE == "0x555BC"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE4
        math SIZE -= 0x54
        log NAME 0x54 SIZE MEMORY_FILE
        append

       else if SIZE == "0x555E4"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE5
        math SIZE -= 0x54
        log NAME 0x54 SIZE MEMORY_FILE
        append

       else if SIZE == "0x2AB20"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE6
        math SIZE -= 0x40
        log NAME 0x40 SIZE MEMORY_FILE
        append


       else if SIZE == "0x2AB08"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE7
        math SIZE -= 0x40
        log NAME 0x40 SIZE MEMORY_FILE
        append

       else if SIZE == "0x155BC"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE8
        math SIZE -= 0x4C
        log NAME 0x4C SIZE MEMORY_FILE
        append

       else if SIZE == "0x155B8"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE9
        math SIZE -= 0x40
        log NAME 0x40 SIZE MEMORY_FILE
        append

       else if SIZE == "0xAB04"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE10
        math SIZE -= 0x4C
        log NAME 0x4C SIZE MEMORY_FILE
        append


       else if SIZE == "0xAB18"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE11
        math SIZE -= 0x40
        log NAME 0x40 SIZE MEMORY_FILE
        append


       else if SIZE == "0xAB1C"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE12
        math SIZE -= 0x4C
        log NAME 0x4C SIZE MEMORY_FILE
        append


       else if SIZE == "0xAAB24"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE13
        math SIZE -= 0x54
        log NAME 0x54 SIZE MEMORY_FILE
        append

       else if SIZE == "0x1555C0"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE14
        math SIZE -= 0x58
        log NAME 0x58 SIZE MEMORY_FILE
        append

       else if SIZE == "0x2AB64"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE15
        math SIZE -= 0x54
        log NAME 0x54 SIZE MEMORY_FILE
        append

       else if SIZE == "0xAFC"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE16
        math SIZE -= 0x44
        log NAME 0x44 SIZE MEMORY_FILE
        append

       else if SIZE == "0x55DC"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE17
        math SIZE -= 0x4C
        log NAME 0x4C SIZE MEMORY_FILE
        append

       else if SIZE == "0x2AB1C"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE18
        math SIZE -= 0x44
        log NAME 0x44 SIZE MEMORY_FILE
        append

       else if SIZE == "0x155E0"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE19
        math SIZE -= 0x50
        log NAME 0x50 SIZE MEMORY_FILE
        append

       else if SIZE == "0x155DC"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE20
        math SIZE -= 0x54
        log NAME 0x54 SIZE MEMORY_FILE
        append

       else if SIZE == "0x55D8"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE21
        math SIZE -= 0x50
        log NAME 0x50 SIZE MEMORY_FILE
        append

       else if SIZE == "0x55B8"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE22
        math SIZE -= 0x48
        log NAME 0x48 SIZE MEMORY_FILE
        append

       else if SIZE == "0x10002B"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE23
        math SIZE -= 0x2c
        log NAME 0x2c SIZE MEMORY_FILE
        append

       else if SIZE == "0x10002C"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE24
        math SIZE -= 0x2c
        log NAME 0x2c SIZE MEMORY_FILE
        append

       else if SIZE == "0x4002C"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE25
        math SIZE -= 0x2c
        log NAME 0x2c SIZE MEMORY_FILE
        append

       else if SIZE == "0xE102C"
        append
        string NAME += ".dds"
        log NAME 0 128 MEMORY_FILE26
        math SIZE -= 0x2c
        log NAME 0x2c SIZE MEMORY_FILE
        append

#       else if SIZE == "0x"
#        append
#        string NAME += ".dds"
#        log NAME 0 128 MEMORY_FILE27
#        math SIZE -= 0x40
#        log NAME 0x40 SIZE MEMORY_FILE
#        append

#       else if SIZE == "0x"
#        append
#        string NAME += ".dds"
#        log NAME 0 128 MEMORY_FILE28
#        math SIZE -= 0x40
#        log NAME 0x40 SIZE MEMORY_FILE
#        append

#       else if SIZE == "0x"
#        append
#        string NAME += ".dds"
#        log NAME 0 128 MEMORY_FILE29
#        math SIZE -= 0x40
#        log NAME 0x40 SIZE MEMORY_FILE
#        append

#       else if SIZE == "0x"
#        append
#        string NAME += ".dds"
#        log NAME 0 128 MEMORY_FILE30
#        math SIZE -= 0x40
#        log NAME 0x40 SIZE MEMORY_FILE
#        append

    else
        log NAME 0 SIZE MEMORY_FILE
    endif
next i


```


just save as .bms and use quickbms and you have the textures.
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-27T05:34:03+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

> Reply from Lev
>
> 

Just copy pasting this because I'm not allowed to upload the file. It does say "exctracting done" but my file is nowhere to be found. I've tried multiple folders.

Well, MexCom says it put it here:
d:\Downloads\id\jpn\benchmark\

Are you running Vista by chance? Vista has the standard setting of intercepting saves and store it somewhere else to be approved later...
## Post #14
- Username: Lev
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jul 23, 2009 8:28 pm
- Post datetime: 2009-07-29T10:34:55+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

I'm running Windows 7.

But I managed to extract the files with both methods (thanks chroxx as well), but I'm stuck with the hex editing part. I have no experience in this, either. What's a good hex editing program to begin with? *puzzled*
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-29T11:17:27+00:00
- Post Title: Resident Evil 5 Benchmark Backgrounds

Hex Workshop or 010 Editor
## Post #16
- Username: Lev
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jul 23, 2009 8:28 pm
- Post datetime: 2009-07-29T12:37:45+00:00
- Post Title: Re: Resident Evil 5 Benchmark Backgrounds

I opened your DDS file using Hex Workshop. And I opened an uncompressed file as well.

I can't seem to figure out where the DDS header ends (it ends at 128 bytes, right? Which one is that?) I don't see any information regarding width and height either, but that's probably I can't figure out where byte 12 and 14 are either...Grasping in the dark here.
[Untitled.jpg](https://xentaxbackup.github.io/file/2234_Untitled.jpg)
## Post #17
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-07-29T13:33:28+00:00
- Post Title: Re: Resident Evil 5 Benchmark Backgrounds

Use normal view, like from 0 to F, not 0-20, and then you can see the header.
The size of header is fixed, 128byte (80h).
## Post #18
- Username: Lev
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jul 23, 2009 8:28 pm
- Post datetime: 2009-07-29T14:53:34+00:00
- Post Title: Re: Resident Evil 5 Benchmark Backgrounds

Thanks evin.

Okay, so I did a few attempts at replacing the uncompressed stuff after the DDS header and was able to get the image Mr. Mouse also produced except with a weird line through it. Also, I tried the same thing for the other images but that didn't work out too well. I have to say that I haven't figured out how to edit width and height yet but I don't think that's the problem.

[](http://img166.imageshack.us/i/capend02360nomipbm.jpg/)
[cap_end00_360_NOMIP2_BM.jpg](https://xentaxbackup.github.io/file/2236_cap_end00_360_NOMIP2_BM.jpg)
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-29T15:19:48+00:00
- Post Title: Re: Resident Evil 5 Benchmark Backgrounds

Please upload the second file you did that didn't work out that well. The first (that I also did) is simply a matter of wrong offset of the image data in the dds you created. You should have saved the dat starting from 80 hexadecimal (128 decimal, or the 129th byte)) 

You should familiarize yourself with hexadecimal numbers (0-f): [http://wiki.xentax.com/index.php/DGTEFF ... _Numbering](http://wiki.xentax.com/index.php/DGTEFF#Hexadecimal_Numbering)

Files are bytes stored sequentially, starting with byte 0 (the first byte). Hexadecimal numbers go from 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, a, b, c, d, e, f.  After f comes 10, 11, 12 ,13, 14, 15, 16, 17, 18 , 19, 1a etc. If you count them a = 10 decimal, b = 11, c = 12 , d = 13, e = 14 and f = 15. 10 = 16, 11 = 17 etc. 
So byte 12 is the byte at position 12 (c)  (or the 13th byte!).
## Post #20
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2009-07-29T17:01:55+00:00
- Post Title: Re: Resident Evil 5 Benchmark Backgrounds

I think, the first image is compressed with DXT1-3-5, but the header is bad. The size of the second image is incorrect, maybe.
Why don't you try out the DMC4 text2dds converter? Maybe works.
[viewtopic.php?f=10&t=3057&st=0&sk=t&sd=a&start=30](http://forum.xentax.com/viewtopic.php?f=10&t=3057&st=0&sk=t&sd=a&start=30)
## Post #21
- Username: Lev
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jul 23, 2009 8:28 pm
- Post datetime: 2009-07-30T21:18:00+00:00
- Post Title: Re: Resident Evil 5 Benchmark Backgrounds

Thanks evin, that worked.

And thanks for that link Mr. Mouse. I'll take my time and try things out for a while.
