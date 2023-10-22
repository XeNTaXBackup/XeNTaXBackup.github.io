## Post #1
- Username: nightvison
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 20, 2009 2:35 pm
- Post datetime: 2009-10-24T06:52:02+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

How can I unpack the .arc file? Filename: Data.arc (2,50GB)

TC view: 

[](http://img21.imageshack.us/i/cabal2.png/)

[](http://img190.imageshack.us/i/cabal1.png/)
## Post #2
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-10-24T07:03:44+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

i interested for this game too 
you must cut the head and tail of archive with file cutter and upload them ... [viewtopic.php?f=28&t=1270](http://forum.xentax.com/viewtopic.php?f=28&t=1270)
or copy and paste hex text in code section instead of its image !
## Post #3
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-10-24T08:56:31+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

99% sure it's Zlib'ed.
## Post #4
- Username: nightvison
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 20, 2009 2:35 pm
- Post datetime: 2009-10-24T09:07:12+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

Filecutter doesn't work! I can't upload the file, because my upload speed: 20kb/s
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-24T13:58:36+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

just use offzip
offzip.exe -z c:\file.dat c:\extracted_folder 0x0
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-24T14:41:28+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

the header of the archive is for sure at the end so: no files, no party
## Post #7
- Username: nightvison
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 20, 2009 2:35 pm
- Post datetime: 2009-10-24T16:07:34+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

Offzip:

[](http://img259.imageshack.us/i/cabal3.png/)
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-24T16:11:56+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

the option meant by chrrox in reality was probably -a and not -z
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-24T16:51:33+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

I have found another Cabela game that uses the same file format so I will release a quickbms script later
## Post #10
- Username: nightvison
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 20, 2009 2:35 pm
- Post datetime: 2009-10-24T17:03:48+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

-a unpack lot of  "0901fa58.dat, 09e1fda9.dat, etc.
But their headers different: DDS, FBAF!, 063X, ShaderLib.
Additional ideas?
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-24T17:20:41+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

the following quickbms script is valid for all the games of the Cabela series:

*edit* use the link in my last post
## Post #12
- Username: nightvison
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 20, 2009 2:35 pm
- Post datetime: 2009-10-24T17:33:28+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

[](http://img39.imageshack.us/i/cabal4.png/)
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-24T17:39:15+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

as already said above if you don't provide the files or parts of the file I can't magically guess the differences with the format I reversed.
the only thing you "could" try is to remove the following 2 lines:
math INFO_OFFSET <<= 0xb
    math OFFSET <<= 11
but I'm sure that nothing will change
## Post #14
- Username: nightvison
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 20, 2009 2:35 pm
- Post datetime: 2009-10-24T17:59:28+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

Sorry, I can't upload the file!

Try to download here:

[http://www.storage.to/get/alTcvIze/COA2 ... .part1.rar](http://www.storage.to/get/alTcvIze/COA2010-ADDICTION.part1.rar)
[http://www.storage.to/get/wQTUUGg7/COA2 ... .part2.rar](http://www.storage.to/get/wQTUUGg7/COA2010-ADDICTION.part2.rar)
[http://www.storage.to/get/5soiYTPm/COA2 ... .part3.rar](http://www.storage.to/get/5soiYTPm/COA2010-ADDICTION.part3.rar)
## Post #15
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-29T15:51:20+00:00
- Post Title: Cabela's Outdoor Adventures 2010 .arc files [PC]

new version of quickbms (fixes a bug with files > 2gb): [http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
new script supporting any Cabela's game: [http://aluigi.org/papers/bms/cabela.bms](http://aluigi.org/papers/bms/cabela.bms)

thanx to cleerxer who contacted me via mail and provided all the needed pieces of the file and informations for solving the bug and adapting the script.
## Post #16
- Username: nightvison
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 20, 2009 2:35 pm
- Post datetime: 2009-10-31T11:15:12+00:00
- Post Title: Re: Cabela's Outdoor Adventures 2010 .arc files [PC]

thank you!
