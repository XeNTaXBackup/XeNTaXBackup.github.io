## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-10-06T17:11:11+00:00
- Post Title: Ubisoft multilayer XMA

Hello folks!

I guess this needs its own topic now. 
No words to waste: I have written a QuickBMS script that lets you extract decodable XMA files out of Ubisoft multilayer XMA packs. 
Works with the  MAKI-extracted files (Common_BAO_0x_______) as well as the native Ubisoft multichannel files (ident 0x02290106). The latter feature is brand new and has just been added.

This is the first time that the music from Ubisoft games on X360 can be extracted and decoded!
If you experience any files where this tool doesn't work with, post here.
You will need [http://www.hcs64.com/files/xma_parse011.zip](http://www.hcs64.com/files/xma_parse011.zip) in the same directory as the script (rename it to xma_parse.exe).

Have fun with all the new stuff to explore! 
[ubi_xma_2013-10-06.zip](https://xentaxbackup.github.io/file/6679_ubi_xma_2013-10-06.zip)
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-10-06T17:52:51+00:00
- Post Title: Ubisoft multilayer XMA

Whoops, last script had problems with mono files - uploaded a corrected one.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-10-07T14:45:07+00:00
- Post Title: Ubisoft multilayer XMA

I found a variant that isn't supported yet: headerless multilayer. Like the headerless single layer variant, these files don't hold any frequency or channel information. The latter can be retrieved but the former has to be guessed and will produce wrong files in some cases. As far as I know there's no possibility to overcome this problem (if you know otherwise, let me know).

Anyway, 90% of the files work fine with the guessed frequency. The "errornous" files have to be changed to 48000 Hz manually.
