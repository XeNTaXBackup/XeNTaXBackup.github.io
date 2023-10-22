## Post #1
- Username: TruePhil
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 02, 2011 2:32 pm
- Post datetime: 2011-07-29T06:54:12+00:00
- Post Title: Metroid Other M Encrypted .AIX File

I'm fairly certain all of Samus' sound files are kept in one .aix, however when I use the aix2adx01 to convert the file, all I get is one sound file and she has many more sounds in-game than one so it has to be encrypted I believe, unless they keep all her other sounds somewhere else for some strange reason.  At any rate has anyone ever gotten Samus' sound files?  If so how did you break the encryption?  I can upload the file for someone to look at if needed.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-07-31T03:19:52+00:00
- Post Title: Metroid Other M Encrypted .AIX File

If it gives you one sound correctly then it really doesn't have anything to do with encryption, aix2adx is probably just broken somehow.  If you upload the file I can add support.
## Post #3
- Username: TruePhil
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 02, 2011 2:32 pm
- Post datetime: 2011-07-31T07:02:38+00:00
- Post Title: Metroid Other M Encrypted .AIX File

Thank you for your help!  Well aix2adx worked fine, however so I suppose the aix is fine.  I don't see where else on the Iso it would keep her sound effects and voice clips   Is there a way to extract aix files from a memory dump?  I can pull brres packs out of them, however I haven't seen a program that does this.  A QuickBMS script would be the best for this as that's what I use for the brres'.
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-08-01T00:59:08+00:00
- Post Title: Metroid Other M Encrypted .AIX File

What I mean is that aix2adx should probably be extracting more than one sound from that aix, but I may have made some mistake so it is only extracting the first sound. Check the sizes of the aix vs. the adx; aix doesn't have too much overhead, so they should be around the same size. If the aix is a lot bigger then it is probably missing something.
## Post #5
- Username: TruePhil
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 02, 2011 2:32 pm
- Post datetime: 2011-08-01T02:54:48+00:00
- Post Title: Metroid Other M Encrypted .AIX File

Nah the difference was only by 10 bytes or so...

At any rate do you know of any way to extract aix files from a memory dump?  I can get brres packs, but I have yet to find anything that does what I'm looking for.
## Post #6
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-08-01T03:52:10+00:00
- Post Title: Metroid Other M Encrypted .AIX File

No. Have you tried adXtract?
