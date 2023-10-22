## Post #1
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2011-04-20T02:43:38+00:00
- Post Title: Test Drive 2002 .XDT

Whoever edited this-WHAT THE FUCK?!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-20T06:51:54+00:00
- Post Title: Test Drive 2002 .XDT

are you sure that the file you uploaded is complete?
because it looks that the last 8 files are not available.

the following is the quickbms script that will automatically skip the unexistent files:

```
get DUMMY long
get FILES long
get BASE_OFF long
get DUMMY long
goto 0x40
get LAME asize
for i = 0 < FILES
    getdstring NAME 0x38
    get OFFSET long
    get SIZE long
    math TMP = OFFSET
    math TMP += SIZE
    if TMP <= LAME
        log NAME OFFSET SIZE
    endif
next i
```
## Post #3
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2011-04-20T16:06:47+00:00
- Post Title: Test Drive 2002 .XDT

Very nice, aluigi! Works fine with all the .xdt files. Although.. is there possible way unpacking the unpacked .xdt files? Header on them says 'SNK'. Thanks.

PS
Is it possible to repack the .xdt files back, using quickbms?
## Post #4
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2011-04-20T17:42:19+00:00
- Post Title: Test Drive 2002 .XDT

@aluigi Must have been a screwup on the dev's part.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-20T17:53:18+00:00
- Post Title: Test Drive 2002 .XDT

reimporting the modified files back in the original xdt archive is possible.
you can find a generic step-by-step here:
[viewtopic.php?p=52546#p52546](http://forum.xentax.com/viewtopic.php?p=52546#p52546)
## Post #6
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2011-04-20T17:59:43+00:00
- Post Title: Test Drive 2002 .XDT

Thanks again alugi, and what about the output .xdt files? Is it possible to extract them?
## Post #7
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2011-04-20T18:01:42+00:00
- Post Title: Test Drive 2002 .XDT

Yes, many thanks.
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-20T19:55:02+00:00
- Post Title: Test Drive 2002 .XDT

the extracted xdt are fake xdt.
if you open them with a hex editor you will notice the SNK signature so they are graphic/3d stuff
## Post #9
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2011-04-20T20:11:53+00:00
- Post Title: Test Drive 2002 .XDT

Kinda thought so. Tried extracting an .XDT of a traffic car and the files inside were things like 00000000001.dat 00000000002.dat etc. Wonder if that is Pitbull Syndicate's texture extension for this game.
## Post #10
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2011-04-22T19:13:02+00:00
- Post Title: Test Drive 2002 .XDT

I'm having trouble repacking sanfran.xdt
I've modified the traffic\textures folder (put ones from the XBOX version in) and have nothing else in the sanfran folder except for traffic\textures. I created the shortcut with -r and -w with a space after the last " . However, you are using a Crysis 2 script for importing, while I only have a TD script for extracting. So it will not work.
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-23T10:39:00+00:00
- Post Title: Test Drive 2002 .XDT

I don't understand, what's the exact problem you have during the repacking?

obviously (I guess it was clear) the example in that post used the crysis script but you must use the script for your specific game... that's why it's an example
## Post #12
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2011-04-23T21:51:53+00:00
- Post Title: Test Drive 2002 .XDT

QuickBMS still extracts regardless of the commands added to the shortcut.
Also, the CMD window in the BG throws an error saying that it doesn't recognize the command -r.
EDIT: Error: wrong arguement (-r)
That's what it says.
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-25T10:36:31+00:00
- Post Title: Test Drive 2002 .XDT

you are using a jurassik version, remember to check ever the latest version of quickbms:
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
## Post #14
- Username: 360AMC
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Apr 20, 2011 10:26 am
- Post datetime: 2011-04-25T20:18:15+00:00
- Post Title: Test Drive 2002 .XDT

Got it, but I don't get what it means by type....for a whole folder.
## Post #15
- Username: PermissionToLand
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 15, 2022 10:58 am
- Post datetime: 2022-11-15T03:01:43+00:00
- Post Title: Test Drive 2002 .XDT

I want to edit the vehicle handling in this game. I was able to unpack the Cars_A.xdt, but cannot seem to do that with each individual car's .xdt file. I assume that's where the handling files are.
