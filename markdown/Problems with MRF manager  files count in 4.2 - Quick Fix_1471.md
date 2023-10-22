## Post #1
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-29T20:58:15+00:00
- Post Title: Problems with MRF manager / files count in 4.2 - Quick Fix

There seemed to have slipped some bugs in the new version. 

First, in the MRF manager at first start (and no MRF files in the database yet) the program will give a "Subscript out of range error" when you click 'Add BMS'). Fixed in the setup available from the main site when you read this text.

Second, the main window failed to show the actual number of files in an archive when opened using Multiex.dll / MexCom Plugin. Fixed. 

Also, missing from the first setup was a file called base_mc.mrf in the data/config dir. Fixed. To correct this yourself, simple copy the mc.mrf in that directory to another file (so you have two copies in there) and rename the copy to base_mc.mrf. 

You could download the whole setup again and install it in the directory you installed it previously. Or get the new exe and fix the base_mc.mrf problem yourself. This will obviously only work if you have version 4.2 installed already. Simply overwrite the mc32.exe file with the new one.
[mc32.zip](https://xentaxbackup.github.io/file/414_mc32.zip)
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-08-31T02:24:05+00:00
- Post Title: Problems with MRF manager / files count in 4.2 - Quick Fix

When was the download updated with that fix? For those too lazy to check ourselves, it would tell us if we need to update with the fix or not.
## Post #3
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-31T07:09:22+00:00
- Post Title: Problems with MRF manager / files count in 4.2 - Quick Fix

Yes, but I reserve creating a new version exe when a little more has changed. The bugs were not major, just nusances.  The fix totals just a couple of lines of code. To me, that's not a minor update (which would grant it access to the sacred Online Update catacombs).  
I'm sure a lot of hardcore coders would disagree wholeheartedly, and then I will tell them: BLAAH.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-09-03T01:49:03+00:00
- Post Title: Problems with MRF manager / files count in 4.2 - Quick Fix

LOL, I'm sure I may one day be one of those 'hardcore coders'...
