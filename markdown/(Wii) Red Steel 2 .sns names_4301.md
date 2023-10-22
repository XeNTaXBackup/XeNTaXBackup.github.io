## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-04-05T19:42:48+00:00
- Post Title: (Wii) Red Steel 2 .sns names

Hello again guys, below i have two samples in a rar file, one of them is the actual audio sns file with the music, the other is the filename that came in a seperate archive. By looking at the ID in the filename in hex plain ascii i can determine the id name for the track, i find the track in another archive that i have extracted with the music and rename them. but for thousand of files its become a quite tedious job, can someone write a bms script that automates this for these two files, then i can maybe write a batch file.

[http://www.filefront.com/16036487/red%2 ... 0names.rar](http://www.filefront.com/16036487/red%20steel%202%20names.rar)
## Post #2
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-04-07T18:26:20+00:00
- Post Title: (Wii) Red Steel 2 .sns names

Are those the same .sns files which are also used in EA games like Burnout?
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-04-07T20:37:54+00:00
- Post Title: (Wii) Red Steel 2 .sns names

These are dsp.
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-04-07T23:19:24+00:00
- Post Title: (Wii) Red Steel 2 .sns names

```
#    xentax.com

goto 4
get SNSSIZE long

findloc EOFN string ".sns"
set SOFN long EOFN

for

	math EOFN -= 1
	goto EOFN

	get CHR char

	if CHR = 0x2f # ASCII /
		break
	elif CHR = 0x2e # ASCII .
		set SOFN long EOFN
		math SOFN -= 1
	endif

next

math SOFN -= EOFN

getdstring NAME SOFN

print "filename: %NAME%.sns size: %SNSSIZE%"

```


hope this helps
if not, could you post the filename table? quickbms can work with multiple files at once - it could do the whole process for you
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-04-07T23:27:59+00:00
- Post Title: (Wii) Red Steel 2 .sns names

[http://www.filefront.com/16057665/file%20names.rar](http://www.filefront.com/16057665/file%20names.rar)

Here

I got quite a few done therefore i removed them but here are the rest.

EDIT: Didn't work, which input file was i suppose to choose?
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-04-07T23:33:12+00:00
- Post Title: (Wii) Red Steel 2 .sns names

so you have these filename files and incorrectly named SNS data file you want renamed?
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-04-07T23:35:38+00:00
- Post Title: (Wii) Red Steel 2 .sns names

yes.

The filename files have the link to the music file in with the number name.
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-04-07T23:40:03+00:00
- Post Title: (Wii) Red Steel 2 .sns names

well at best you can only rename them using the file size.. which is hardly ideal

edit

scandir isn't up to recursive calling
you can still use my script on the filename files with a combination of the DIR command prompt command to manually finish the job
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-04-08T00:07:59+00:00
- Post Title: (Wii) Red Steel 2 .sns names

okay thx, if it works right i can still probably write me a batch for it.
