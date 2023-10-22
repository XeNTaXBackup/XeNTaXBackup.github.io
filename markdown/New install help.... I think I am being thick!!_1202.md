## Post #1
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-04-23T23:01:37+00:00
- Post Title: New install help.... I think I am being thick!!

Hi there

Just got the new build of MultiEx and thought I'd register it  (Though not had code yet)... however...

The extension listed for Counterstrike XBox is *.wad, instead of *.sxwad... and I seem to have lost functionality for *.xpr files...

Will this be sorted via web update when I get my code?

Or have I lost it forever? Seeing as I overwrote my old version... 

Cheers for now
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-24T09:06:33+00:00
- Post Title: New install help.... I think I am being thick!!

Just type *.* when you wish to choose the file and select the .sxwad file (it is listed as WAD, but will open .SXWAD). This is due to a structural problem in MexCom that only allows me to have a 3 character extension.  It's on my to-fix list, but not high enough priority apparently. 

 

Anyway,  I will look into the XPR issue.
## Post #3
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-04-24T09:34:34+00:00
- Post Title: New install help.... I think I am being thick!!

Got it thanks 

In the first thread about SXWads you made a new mc.mrf file to enable xpr format.... I guess the work is already done but I don't know if these files can be merged.

Cheers for now
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-04-25T14:44:32+00:00
- Post Title: New install help.... I think I am being thick!!

I don't think they can be merged... unless you want to break out a hex editor, it would require using the MexScriptor program, which does not currently support the new .mrf format, which the latest release of MexCom uses.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-25T14:50:30+00:00
- Post Title: New install help.... I think I am being thick!!

And only yesterday I noticed a bug in the (new) Scriptor which has to be fixed first. However, the XPR bms should still work. (Use custom BMS option).
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-04-25T14:54:23+00:00
- Post Title: New install help.... I think I am being thick!!

What does the bug cause? Bad compilings?
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-25T14:55:37+00:00
- Post Title: New install help.... I think I am being thick!!

Well, I don't know yet. At least the script doesn't run right, and that may also be due to a bug in multiex.dll, however, only in some instances.
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2005-04-25T15:01:51+00:00
- Post Title: New install help.... I think I am being thick!!

Okay. Hope you can fix it soon!
## Post #9
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-04-25T15:22:57+00:00
- Post Title: New install help.... I think I am being thick!!

> Reply from Mr.Mouse
>
> However, the XPR bms should still work. (Use custom BMS option).

Hmm.. now I am being thick... 

Custom BMS option.. enters *.* to be able to select xpr files... nothing 

Can you help an old mind?

Cheers for now
## Post #10
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-25T15:39:28+00:00
- Post Title: New install help.... I think I am being thick!!

Ah yes, no, you should dl the XPR.BMS from the thread here, and use that in the Custom BMS option (CBMSO). 

So dl it, point to it in the CBMSO, and THEN point to a *.XPR file.  

Here's the BMS:
[XPR.zip](https://xentaxbackup.github.io/file/187_XPR.zip)
