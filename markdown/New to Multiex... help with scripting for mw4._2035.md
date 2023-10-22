## Post #1
- Username: MACK
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 12, 2006 5:06 am
- Post datetime: 2006-08-11T21:10:50+00:00
- Post Title: New to Multiex... help with scripting for mw4.

I recently became a friend... and am trying to access props.mw4 in mechwarrior.

I can open props.mw4 but the files inside (for example .script files) are encrypted/compressed?

I found this>>>>>>>>>>>>>>>>>>>>>>>>
[ ] - Name : Mechwarrior 4 :Mercenaries - MW4 files

Info : Extract only, not complete, does not decompress any files in there that need decompression.
Date : 3-2-2004
SCRIPT:

IDString 0 #VBD ;
Get D Long 0 ;
Get D Long 0 ;
Get START Long 0 ;
Get Item_Count Int 0 ;
Get Item_Count Int 0 ;
For T = 1 To Item_Count ;
GetDString TIME 8 0 ;
Get OS Long 0 ;
Get NS Long 0 ;
Get RO Long 0 ;
Get IC Int 0 ;
Get BS Byte 0 ;
GetDString IN BS 0 ;
Set IO Long RO ;
Math IO += START ;
Log IN IO NS 0 0 ;
Next T ;

>>>>>>>>>>>>>>>>>>>>>>>> 

But, I am not sure how to Enable this script so that it works with Multiex...

Any help or links to a how to use scripts guid would be helpful.

Thanks,

MACK
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-08-11T21:48:29+00:00
- Post Title: New to Multiex... help with scripting for mw4.

That IS probably the script used by MultiEx. Like it said, it does not decompress the files. You can do a search on this forum why we couldn't decompress them.
## Post #3
- Username: MACK
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 12, 2006 5:06 am
- Post datetime: 2008-07-02T00:00:52+00:00
- Post Title: New to Multiex... help with scripting for mw4.

Its been years and I was hoping that you could add extract, replace, and append for the MW4 files in Mechwarrior Mercs.

Is it possible to "hire" someone from Multiex to do this?
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-12T20:55:28+00:00
- Post Title: New to Multiex... help with scripting for mw4.

Not really, we haven't got that kind of money.
## Post #5
- Username: MACK
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 12, 2006 5:06 am
- Post datetime: 2009-07-02T19:14:22+00:00
- Post Title: New to Multiex... help with scripting for mw4.

Well, we finally figured it out.  Special Thanks to Mr. Haisch for his work on compression.
The Mechwarrior .mw4 uses a variant of Limpel Ziv Welch.
Please visit us at [http://www.mechstorm.com/forum](http://www.mechstorm.com/forum) if you are a fan of mechwarrior.
We are always looking for people interested in modding the game.
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-07-02T20:24:36+00:00
- Post Title: New to Multiex... help with scripting for mw4.

> Reply from Mr.Mouse
>
> Not really, we haven't got that kind of money.
He probably meant to pay somebody for figuring out the compression
## Post #7
- Username: MACK
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 12, 2006 5:06 am
- Post datetime: 2009-07-03T01:38:32+00:00
- Post Title: New to Multiex... help with scripting for mw4.

LOL that post is almost a year old... and the original post requesting help is a LONG time ago!
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-03T07:19:30+00:00
- Post Title: New to Multiex... help with scripting for mw4.

Good to see that even after three years, you still posted that you got the solution!  This is excellent!
