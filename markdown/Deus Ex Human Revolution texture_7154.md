## Post #1
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2011-08-10T08:07:39+00:00
- Post Title: Deus Ex Human Revolution texture

How can you unpack the textures:
- download the offzip ([http://aluigi.altervista.org/mytoolz.htm](http://aluigi.altervista.org/mytoolz.htm))
- use with these command: offzip.exe -a bigfile.000 unpack 0  (bigfile.000 and bigfile.001)
- find the .pcd files
- use the attached DeusExHRDDS tool to convert them into DDS

DeusExHRDDS(very very simple tool!):
- not supported 8.8.8.8 compressed DDS files (not so many)
- some DDS has wrong size

If anyone find the font files, let me know!!! (I know about the 386511f0.pcd.dds from bigfile.001, but I need another one. There must be a better/bigger font texture.)
[DeusExHRDDS.zip](https://xentaxbackup.github.io/file/4609_DeusExHRDDS.zip)
## Post #2
- Username: lUIGUIPIETRO
- Rank: veteran
- Number of posts: 87
- Joined date: Sat Mar 13, 2010 10:59 pm
- Post datetime: 2011-08-10T19:57:01+00:00
- Post Title: Deus Ex Human Revolution texture

Thx Evin
## Post #3
- Username: Tyiler
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 26, 2011 11:33 am
- Post datetime: 2011-08-26T03:47:16+00:00
- Post Title: Deus Ex Human Revolution texture

I had a few problems with the syntax of the offzip file but I did the following to get it to work

-moved the bigfile.000 to the local directory (for ease of use)
then used the following command

offzip.exe -a bigfile.000 c:\unzip 0 


and it worked
