## Post #1
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-10-14T16:47:06+00:00
- Post Title: [Request] World Racing 2 - PS2 / *.nob Files

Here is an new request:

Game: World Racing 2 for PS2. The archive files called *.nob

It's not the newest game, but there are several good modding sides for the PC version.

An example is attached.

Thanks in advance,
Andreas
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-15T06:15:38+00:00
- Post Title: [Request] World Racing 2 - PS2 / *.nob Files

Ok, this one seems pretty straightforward. You already attached the .fat file, which is of course the file allocation table. It holds the information on the files that are in the nob files.
## Post #3
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-10-16T16:41:10+00:00
- Post Title: [Request] World Racing 2 - PS2 / *.nob Files

I have attached another example (HHeim.nob, HHeim.fat) and a snapshot of the folder structure of the game.

Btw, here is a link to the pc-trialversion

[http://www.4players.de/4players.php/dow ... 44700.html](http://www.4players.de/4players.php/download_info/PC-CDROM/Download/44700.html)

It seems that there are not so many differences.

Can anyone create a quickbms script   p l e a s e ?    I'm a newbie, I can't do this by myself.

Thanks, Andreas.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-17T15:45:01+00:00
- Post Title: [Request] World Racing 2 - PS2 / *.nob Files

The PC version does not have these .nob files. Can you cut out a larger part? And upload it somewhere?
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-17T22:03:53+00:00
- Post Title: [Request] World Racing 2 - PS2 / *.nob Files

Never mind, I've got the format figured out. Here's a script you may use in MultiEx Commander:

```
Open FDDE FAT 1 ;
# In the fat, get the archive size
Get ArchiveSize Long 1 ;
# Now get the number of entries 
Get FileNum Long 1 ;
# Calculate offset of file string table 
SavePos Here 1 ;
Math Here += 12 ;
# Jump to start of first resource entry
GoTo Here 1 ;
Set J Long FileNum ;
# One entry is 20 bytes 
Math J *= 24 ;
# Add that to Here to get the offset of the string table
Math Here += J ;
# All set - let us process the information
For T = 1 To FileNum ;
# Get the offset of the resource name in the string table
Get NOff Long 1 ;
# Get the offset of the folder name of the resource in the string table
Get FOff Long 1 ;
# Get the bank number where the resource starts in the NOB file
Get Bank Long 1 ;
# Get the size of the resource
Get Size Long 1 ;
# Get two unknown values 
Get U1 Long 1 ;
Get U2 Long 1 ;
# Save the current position to go back to later
SavePos There 1 ;
# First information gotten - now calculate the offset of the resource
# One bank = 2048 bytes
Math Bank *= 2048 ;
# Get the full path of the resource
Math FOff += Here ;
Math NOff += Here ;
GoTo FOff 1 ;
Get Path String 1 ;
GoTo NOff 1 ;
Get Name String 1 ;
String Path += "\" ;
String Path += Name ;
# Log all information for MultiEx
Log Path Bank Size 0 0 ;
# Jump to get the next 
GoTo There 1;
Next T ;

```


Note that you must open a NOB file, not a FAT file in MultiEx Commander. 

To use the script save it as a txt file and go to BMS->Run MexScript script on. Then first select the txt file and then the nob file. Alternatively, use the .bms file (a pre-compiled script) and add it to the MultiEx Commander BMS file so you can open it normally. To do that go to BMS->Add BMS to MRF and follow the instructions. 


 nob.zip
(384 Bytes) Downloaded 33 times



Using this script I could extract something from the snippets you attached, such as TEX files, textures files. These car logos were 128x128 in resolution and head a specific header. The image data is 8-bit (so 16384 bytes for one logo). I did not have the correct pallette the game uses, but you see it is correct:



VW.png (3.02 KiB) Viewed 257 times



That's the VW logo I cut from the VW.TEX file.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-18T13:58:22+00:00
- Post Title: [Request] World Racing 2 - PS2 / *.nob Files

> Note that you must open a NOB file, not a FAT file in MultiEx Commander.
isn't this limitation bypassed if you add a "Open FDDE NOB 0 ;" at the beginning of the script?
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-18T15:40:30+00:00
- Post Title: [Request] World Racing 2 - PS2 / *.nob Files

No, because the first file that is opened ("targeted") will automatically be file 0. The problem is that the Log command does not take a file number: 0 is assumed. When you choose *.fat as the first file, it will be file 0. MultiEx will then assume it needs the *.fat to find the resources. Which is not the case. 

Though this may be a stupid thing, there is really some logic to it. 
In the past a script was dedicated to a certain file, and you would use the script to open a certain file, and the Log would refer to that file (file 0). However, then there came archives that had external file information tables. In essence, the NOB file is the archive, while the .FAT file is simply that: a FAT. So logically, the NOB is file 0 and the .FAT an external file.
## Post #8
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-10-18T17:26:02+00:00
- Post Title: [Request] World Racing 2 - PS2 / *.nob Files

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-18T18:08:43+00:00
- Post Title: [Request] World Racing 2 - PS2 / *.nob Files

Could you use another upload service perhaps? Rapidshare is difficult nowadays, as they more or less banned the free users.
## Post #10
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-10-19T20:11:03+00:00
- Post Title: [Request] World Racing 2 - PS2 / *.nob Files

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-10-19T20:55:55+00:00
- Post Title: [Request] World Racing 2 - PS2 / *.nob Files

I used Hex Workshop to cut out the image data from the TEX file and then opened it as RAW data in Photoshop.
## Post #12
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-10-22T18:32:20+00:00
- Post Title: [Request] World Racing 2 - PS2 / *.nob Files

Hi all,

here are the detailed feedback: All nob files opened and extracted without any problems.

But is it possible to add an import or replace line to the script, so I can e.g. add or replace any vinyls or cars?

Thanks a lot.
