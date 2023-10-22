## Post #1
- Username: Quetzalcoatil
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 02, 2010 10:12 am
- Post datetime: 2010-10-06T03:35:10+00:00
- Post Title: Errors at startup: Incompatible Java and MRF Out of Memory

<EDIT> So as soon as I posted this I got it running using the 'Run MexScript on...' a .txt version of the BOFiv.BMS, and a random .EMI file from BOFV: Dragon Quarter. Now to just figure out what I'm going to have to much with to get the script to extract correctly decrypted data <) Wish me luck!! </EDIT>

Hi all,

So sorry if this is a noob problem, and I found another thread related, but the guy that asked the question was a bit of a hot head resulting in the thread being closed and unanswered(that I could find).
1. So I'm a recent friend and using Win 7 and JRE 6. Do I need an older Java install?
2. I attempted to load a new BMS into the MRF and backed-up the original, but as soon as it finished loading the new BMS, MultiEx Com threw a "MRF load Out of memory!" alert and shut down. Now it does the same everytime I try to run MultiEx Com. The BMS I loaded was the Breath of Fire iv EMI script Mr Mouse wrote a while back. (I found it on the wayback machine because the wiki servers seem to be down atm?)
3. Upon fresh install and attempts to 'load custom script on ...', I select the BOFiv.BMS and then a random .EMI and I get runtime error 7: Out of memory. 

I think the problem is the BMS file, but I'm new to the specs. I did go through it and make sure there was a space before every semi-colon, and none after for every command in the BMS. 

Any help would be greatly appreciated.
-Q13
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-10-06T13:34:12+00:00
- Post Title: Errors at startup: Incompatible Java and MRF Out of Memory

You do not need JAva for MultiEx Commander. Also, a BMS file in terms of MexCom is a compiled file,not a text file. If you import a text file into an MRF, it will crash. That's why something worked when you chose the Run MexScript On... BMSs are compiled by MexScriptor. 

Why not post the script you created. You should not mistake QuickBMS for MultiEx. QuickBMS took MexScript as the base script and then built on it (forked). MexCom using MexScript does not necessarily support the QuickBMS forks.
## Post #3
- Username: Quetzalcoatil
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 02, 2010 10:12 am
- Post datetime: 2010-10-06T15:15:29+00:00
- Post Title: Errors at startup: Incompatible Java and MRF Out of Memory

Mr Mouse,
Thanks for the prompt and helpful response!
I figured it was probably something like that after I got it working (it makes no sense to have two functions that do the exact same thing...). Anyway, I haven't modified the script you wrote a few years ago for Breath of Fire 4's .EMI files. since the wiki seems to be down.  It works for BOFV as well, but I haven't figured out how to load the extracted data files for either game...yet. My plan is to get iv's EMIs into some workable status, then see if that works with v's. When it doesn't, try to figure out why, fix it and then post what I've done. 
Please stop me if someone's beat me to it, as the File Format Depository link in your sig is down.
Thanks,
-Q13

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
# first file. Lets start reading the file info for each file
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
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-10-06T17:54:19+00:00
- Post Title: Errors at startup: Incompatible Java and MRF Out of Memory

We were attacked via some MySQL injection at the wiki, are attempting to restore most of the destroyed database.
## Post #5
- Username: Quetzalcoatil
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Oct 02, 2010 10:12 am
- Post datetime: 2010-10-06T20:27:45+00:00
- Post Title: Errors at startup: Incompatible Java and MRF Out of Memory

Ouch! That sucks, good luck with that!
-Q13
