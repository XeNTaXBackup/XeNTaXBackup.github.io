## Post #1
- Username: ubrax
- Rank: advanced
- Number of posts: 46
- Joined date: Sun Mar 15, 2009 9:16 pm
- Post datetime: 2010-03-26T16:55:22+00:00
- Post Title: Lost Cases of 221B Baker St - Archive(s)

I'll appreciate any help or guidance to unpack the "*.dat"-archives from "The Lost Cases of 221B Baker St". 
The head.bin and tail.bin may be downloaded here: [http://www.motionpress.com/uploads/The_ ... ker_St.rar](http://www.motionpress.com/uploads/The_Lost_Cases_Of_221b_Baker_St.rar)

Thanks in advance!
## Post #2
- Username: ubrax
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-03-26T19:23:16+00:00
- Post Title: Lost Cases of 221B Baker St - Archive(s)

The first couple of zlib compressed files seem to contain some file names.
but you can extract the zlib compressed files with offzip.
use 
offzip.exe -a c:\input.bin c:\output 0x0

they all seem to be picture formats so it is much easier to just extract all the files then mass rename them to .png and put all the files that show a thumbnail image in a folder then rename the rest .jpg and just repeat till no files are left.
[00019111.dat.jpg](https://xentaxbackup.github.io/file/2887_00019111.dat.jpg)
## Post #3
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-04-20T18:41:56+00:00
- Post Title: Lost Cases of 221B Baker St - Archive(s)

I created a simple .dat extractor.

 Usage: baker_extract.exe <DAT_File> <TargetDir>

 example: baker_extract.exe lang_en.dat e:\temp\target

Updated! Now handles the 1st game's dat files too! (Lost Cases of Sherlock Holmes)
