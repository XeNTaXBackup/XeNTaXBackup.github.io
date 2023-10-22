## Post #1
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-02T14:18:00+00:00
- Post Title: Error with .EMI script

I only TODAY got the new version of Multi EX and i tried to aff this script.

```
# By Mr.Mouse 
# ---------------------------- 
# First get the Number of files (FN) 
ImpType SFileSize ; 
Get FN Long 0 ; 
Get U1 Long 0 ; 
GetDString ID 8 0 ; 
# The ID string is "MATH_LAB" 
# Very well, now prepare some padding calculations 
# Each data stream (data section) is padded up to 
# 0x800 blocks. 
Set B Long 2048 ; 
Set A Long FN ; 
Math A *= 16 ; 
Math A += 16 ; 
Set C Long A ; 
Math C /= B ; 
Math C *= 2048 ; 
Math C += 2048 ; 
Set Off Long C ; 
# Good, now we have calculated the Offset of the 
# first file. Let's start reading the file info for each file 
# in the archive! 
For T = 1 To FN ; 
SavePos FSO 0 ; 
Get FS Long 0 ; 
Get U2 Long 0 ; 
Get ID2 Long 0 ; 
Get U3 Int 0 ; 
Get END Int 0 ; 
Log "" Off FS 0 FSO ; 
# Need to perform padding calculations to get to the 
# offset of the next file (if any) 
Math FS /= 2048 ; 
Math FS *= 2048 ; 
Math FS += 2048 ; 
Math Off += FS ; 
Next T ; 
# There! That did the trick! 

```


Il now LIST my problems(looked in manual but nothing helped sorry) I dont know HOW to MAKE a BMS file, I simply copied and pasted that lot into a txt file but it didnt work.
Also when i opent he TXT file in Mexbinder it ses there is an error at line 1, Im nto sure WHAT the error is, but i know its goignt o be something OBVIOUS.
I TRIED to follow Mr Mouses tutorial on it but alas I didnt manage anything.
So if anyone could please help me itd be greatly appreciated.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-02T14:50:19+00:00
- Post Title: Error with .EMI script

> Reply from lionheartuk
>
> 
Il now LIST my problems(looked in manual but nothing helped sorry) I dont know HOW to MAKE a BMS file, I simply copied and pasted that lot into a txt file but it didnt work.
Also when i opent he TXT file in Mexbinder it ses there is an error at line 1, Im nto sure WHAT the error is, but i know its goignt o be something OBVIOUS.
I TRIED to follow Mr Mouses tutorial on it but alas I didnt manage anything.
So if anyone could please help me itd be greatly appreciated.

Hmm, should work if you copy it to a text file and then Run MexScript on..  Choose the text file and then the archive. 

Alternatively, why go to Open Archive, select WIKI (Unofficial) and then Breath of Fire 4 EMI files?
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-02T16:39:02+00:00
- Post Title: Error with .EMI script

Hmm, should work if you copy it to a text file and then Run MexScript on..  Choose the text file and then the archive. 

Alternatively, why go to Open Archive, select WIKI (Unofficial) and then Breath of Fire 4 EMI files? [/quote]
It ses if i do the 1st one its out of memory then it closes.
When i CHECK THE TXT file with Binder thingy, it tells me there is an ERROR on line ONE.(I have changed NOTHING its EXACTLY as i posted it).
If i try connect to WIKI unnoficial it ses error recieving some Flac2 file or something like that.
It doesnt ADD anything, Also out of ALL the hundreds of formats in there EMI or Breath Of Fire isnt in there.
Could someone else try this see if its just me or not
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-02T18:24:17+00:00
- Post Title: Error with .EMI script

Ok, the error with the wiki is because for some reason your code was not entered in the database. The other error I do not understand. Please make a screenshot of the Scriptor as you recieve the error with the script after Check Script. I installed MultiEx Commander 4.3 on another computer and it all worked perfectly.
