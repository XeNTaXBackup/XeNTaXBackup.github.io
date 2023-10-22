## Post #1
- Username: Xanax
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 13, 2007 11:32 am
- Post datetime: 2007-01-14T13:39:06+00:00
- Post Title: file open dialog - slow

I downloaded the current version (4.3.0) of MultiEx commander two days ago.  It is unregistered.  When I click on 'Open Archive', it takes nearly two minutes for the File Open Dialog window to appear.  

I did a search and didn't see any reference to this.  Any help would be greatly appreciated.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-01-14T15:49:54+00:00
- Post Title: file open dialog - slow

> Reply from Xanax
>
> I downloaded the current version (4.3.0) of MultiEx commander two days ago.  It is unregistered.  When I click on 'Open Archive', it takes nearly two minutes for the File Open Dialog window to appear.  

I did a search and didn't see any reference to this.  Any help would be greatly appreciated.

Interesting. Does it do this all the time ?
## Post #3
- Username: Xanax
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 13, 2007 11:32 am
- Post datetime: 2007-01-14T16:10:00+00:00
- Post Title: file open dialog - slow

> Reply from Mr.Mouse
>
> Xanax wrote:I downloaded the current version (4.3.0) of MultiEx commander two days ago.  It is unregistered.  When I click on 'Open Archive', it takes nearly two minutes for the File Open Dialog window to appear.  

I did a search and didn't see any reference to this.  Any help would be greatly appreciated.

Interesting. Does it do this all the time ?
Yes, but I think I may have an idea of what the problem is.  This is a computer that I had at work that they let me take home when I got a new one.  It has about a dozen mapped network drives on it that I have never bothered to unmap, and so no longer actually exist.  I notice that the open dialog comes up without plus signs next to those drives, which tells me that it has done enough work to figure out that there is nothing there.  

So I'm guessing that maybe it is the time it is taking to explore those non-existent drives.  Does that make sense?
## Post #4
- Username: Xanax
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 13, 2007 11:32 am
- Post datetime: 2007-01-14T17:10:30+00:00
- Post Title: file open dialog - slow

That was it.  I disconnected those drives and now it pops right up.  

Sorry for the false alarm and that should teach me to stop and think for a few minutes before posting (but it probably won't).
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2007-01-17T16:21:55+00:00
- Post Title: file open dialog - slow

Hey, don't mention it, this way, if someone else asks about a similar problem in the future, we can check and make sure it's not nonexistant network drives.
