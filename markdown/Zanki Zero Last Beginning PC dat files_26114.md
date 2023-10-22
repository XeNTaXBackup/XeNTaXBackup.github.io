## Post #1
- Username: GIZZY
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 25, 2020 1:58 am
- Post datetime: 2022-12-23T16:26:23+00:00
- Post Title: Zanki Zero: Last Beginning PC dat files

I'm not sure if this is the right forum to ask this but I'm currently unable to extract the .lgx files from the dat files after using the allzdecoder. I was hoping someone would be able to help me get the model and texture formats. I can provide more samples if needed.
[Dat Sample.rar](https://xentaxbackup.github.io/file/23185_Dat Sample.rar)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-12-23T22:47:45+00:00
- Post Title: Zanki Zero: Last Beginning PC dat files

Allzdecoder works only with files compressed with "Aqualead LZSS" compression. (DAT files with "ALLZ" signature, for example "000.dat").
More info here [http://wiki.xentax.com/index.php/Aqualead_LZSS](http://wiki.xentax.com/index.php/Aqualead_LZSS)

The sample you have posted seems like a file already extracted by allzdecoder from one of the main DAT archives.
If you look at this file in hex editor, you will see "LABM" signature.
It may be some kind of 3d model file (or container for LGX files), but it requires more investigation.
## Post #3
- Username: GIZZY
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 25, 2020 1:58 am
- Post datetime: 2023-02-16T16:37:19+00:00
- Post Title: Zanki Zero: Last Beginning PC dat files

Still unsure how to unpack the files further, if anyone could help investigate this more I'd greatly appreciate it.
