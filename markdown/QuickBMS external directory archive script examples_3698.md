## Post #1
- Username: Loculi
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 15, 2009 10:40 pm
- Post datetime: 2009-09-04T20:06:09+00:00
- Post Title: QuickBMS external directory archive script examples?

Hi,

I was just wondering if anyone has an example on how to setup a script in QuickBMS to extract from an external directory archive.  Is there a way to specify both files, or is it simply a matter of appending the data from the external directory archive into the main resource archive and using goto commands?

Thanks!
## Post #2
- Username: Loculi
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-09-05T00:14:23+00:00
- Post Title: QuickBMS external directory archive script examples?

if you mean read a file table into memory and use that to extract another file yes that is possible.
freejack posted here has a script from bugtest that does exactly what you want to do.
you can also append the file table to the end of the archive in a hex editor and then just go to that position and start extracting from there.
