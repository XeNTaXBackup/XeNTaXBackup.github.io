## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-30T20:22:11+00:00
- Post Title: dead rising files .tex .big

hey guys im here to ask for some help i know theres a script for the .big file for dead rising 2 off the record and it does extract the files but it seems it doesn't unpack  some files with-in the arcade versions when i look at the text half of the weapons info isn't there 

for the .tex im looking to edit a dlc called gamebreaker but all the info is in the .tex just like the credits.tex if anyone is willing to help me that would be very helpful 

here are the files 
[http://www.sendspace.com/file/y99lih](http://www.sendspace.com/file/y99lih)
## Post #2
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-30T20:31:17+00:00
- Post Title: dead rising files .tex .big

ok i got some progress on the .tex u used this scripts and it unpacked an .xpr

# Games: Grey Matter (XBOX360)
# TEX to DDS converter
# by Fatduck    Feb2011
# script for QuickBMS    [http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)

endian big
get DDSNAME basename
get DATASIZE asize
set XPRNAME DDSNAME
string XPRNAME += .xpr
putvarchr MEMORY_FILE 0 0
append
putdstring "XPR2" 4 MEMORY_FILE
put 0x64 long MEMORY_FILE
put DATASIZE long MEMORY_FILE
put 1 long MEMORY_FILE
putdstring "TX2D" 4 MEMORY_FILE
put 0x30 long MEMORY_FILE
put 0x34 long MEMORY_FILE
put 0x14 long MEMORY_FILE
putdstring DDSNAME 0x1C MEMORY_FILE
log MEMORY_FILE 0 DATASIZE
append

math DATASIZE += 0x3C
log XPRNAME 0 DATASIZE MEMORY_FILE
## Post #3
- Username: MaddaCheeb
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 13, 2011 12:43 pm
- Post datetime: 2012-09-02T19:03:24+00:00
- Post Title: dead rising files .tex .big

Why does it unpack a .xpr when the script says it outputs it to a DDS?
## Post #4
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-09-02T19:28:21+00:00
- Post Title: dead rising files .tex .big

> Reply from MaddaCheeb
>
> Why does it unpack a .xpr when the script says it outputs it to a DDS?
not sure yet  sorry lol
