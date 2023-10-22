## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-29T20:11:12+00:00
- Post Title: LEGO Indiana Jones 2 [PSP] - *.FIB

Ok, here's another request. The new games have quite a lot to offer for you guys... 
This time it's the PSP version of LEGO Indiana Jones 2. The archive has the suffix .fib and the header starts with FUSE1.00R.......
Although the container seems to be compressed, 7zip compressed the file to 11%!
[http://www.filefront.com/15024957/legoindy2psp.7z](http://www.filefront.com/15024957/legoindy2psp.7z)
Can anyone figure out the compression method and write a bms script? Thanks!
## Post #2
- Username: AlphaTwentyThree
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-11-29T22:12:49+00:00
- Post Title: LEGO Indiana Jones 2 [PSP] - *.FIB

That is bloody awesome. 7z compressed a 360 MB file to 42 MB, while standard zip managed to get it to 280 MB.   The new standard is 7z, people.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-29T23:28:51+00:00
- Post Title: LEGO Indiana Jones 2 [PSP] - *.FIB

> Reply from Mr.Mouse
>
> That is bloody awesome. 7z compressed a 360 MB file to 42 MB, while standard zip managed to get it to 280 MB.   The new standard is 7z, people.
Hehe, I always wonder why nobody understands that I always use 7zip...
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-02T13:37:26+00:00
- Post Title: LEGO Indiana Jones 2 [PSP] - *.FIB

Hm, despite the 7zip compression: Anyone has a clue?
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-08T11:38:43+00:00
- Post Title: LEGO Indiana Jones 2 [PSP] - *.FIB

Really no-one?
## Post #6
- Username: cozy
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Dec 08, 2009 5:18 am
- Post datetime: 2011-04-25T10:12:23+00:00
- Post Title: LEGO Indiana Jones 2 [PSP] - *.FIB

> Reply from AlphaTwentyThree
>
> Really no-one?

I`ve been searching for ages for this,seems all the Lego games use this file system i`ve looked at the psp games and also the NDS games also,so could someone have a look PLEASE....

here is a head and tail [8.1mb]of the lego star wars 3 the clone wars PSP

multi upload:-

[http://www.multiupload.com/6GNAJS4NS7](http://www.multiupload.com/6GNAJS4NS7)

cheers cozy
## Post #7
- Username: reboot31
- Rank: MIT cheater
- Number of posts: 10
- Joined date: Mon Apr 18, 2011 2:41 pm
- Post datetime: 2011-04-29T14:06:42+00:00
- Post Title: LEGO Indiana Jones 2 [PSP] - *.FIB

nice cozy...
## Post #8
- Username: TheMathDoc
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Sep 06, 2013 11:57 pm
- Post datetime: 2015-09-30T19:58:14+00:00
- Post Title: LEGO Indiana Jones 2 [PSP] - *.FIB

So I stumbled upon this about 4 years later when trying to work on Lego Batman 3. I'm putting my findings here in case someone else comes across a .fib file.

FibHeader (20 bytes):

CHAR[4] Header // Should be "FUSE"
CHAR[4] VersionInfo // I saw 1.00
DWORD EntryCount
DWORD Zero // Was always 0 for me
DWORD Unknown

Then there's a table of entries in the fib file starting at offset 
FileSize - 12 * EntryCount

FibTableEntry (12 bytes):
DWORD Hash // Corresponds to a name
DWORD Offset // Offset of the asset in this file
DWORD Flags // Not sure what these control

Lastly, each file in the .fib looks like
DWORD FileSize
BYTE* FileContent // FileSize bytes

For my purposes, a unique hash was all I needed to find, and I was unable to locate any information about how to find the name for that hash. It definitely exists outside of the .fib file.

I hope this helps someone else out someday!
